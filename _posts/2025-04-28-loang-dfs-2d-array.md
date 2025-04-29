---
layout: post
title: "Chuyên đề: Kỹ thuật duyệt DFS trên mảng hai chiều (Loang trên ma trận)"
subtitle: "Tìm hiểu mô hình loang cơ bản bằng DFS và bài toán mẫu ứng dụng"
tags: [DFS]
author: Hoàng Hà
---

# Giới thiệu về kỹ thuật DFS trên mảng hai chiều

Kỹ thuật **DFS (Depth-First Search) trên mảng hai chiều**, còn gọi là **loang trên ma trận**, là một phương pháp phổ biến trong lập trình thuật toán để khám phá hoặc đánh dấu các vùng liên thông trong một lưới (grid). Đây là kỹ thuật cơ bản và rất quan trọng khi xử lý các bài toán liên quan đến:
- Đếm số lượng vùng (islands, components).
- Tìm diện tích vùng lớn nhất.
- Kiểm tra tính liên thông.
- Các bài toán mô phỏng lan truyền (như nước lũ, lửa cháy,...).

# Mô hình loang bằng DFS

Giả sử bạn có một lưới 2D kích thước $N \times M$, bạn cần duyệt từ một ô $(i, j)$ và loang ra tất cả các ô lân cận thỏa mãn điều kiện (ví dụ cùng màu, hoặc có giá trị 1).

Các bước cơ bản của DFS trên ma trận:
1. Đánh dấu ô $(i, j)$ đã được thăm.
2. Duyệt 4 hướng (hoặc 8 hướng nếu bài yêu cầu): lên, xuống, trái, phải.
3. Với mỗi hướng, nếu ô kế bên hợp lệ và chưa thăm, tiếp tục gọi đệ quy DFS.

# Bài toán mẫu: **Number of Islands** ([LeetCode 200](https://leetcode.com/problems/number-of-islands/))

## Đề bài

Cho một lưới nhị phân 2D 'grid' gồm '1' (đất) và '0' (nước). Một hòn đảo được tạo bởi các vùng đất ('1') nối với nhau theo chiều ngang hoặc dọc.  
Hãy trả về số lượng đảo có trong lưới.

**Ví dụ**:

Input:
```
grid = [
  ["1","1","0","0","0"],
  ["1","1","0","0","0"],
  ["0","0","1","0","0"],
  ["0","0","0","1","1"]
]
```

Output:
```
3
```

Giải thích:
- Có 3 hòn đảo: góc trên trái, giữa và góc dưới phải.

## Mô phỏng thuật toán

- Duyệt từng ô trong ma trận.
- Khi gặp ô đất ('1') chưa được thăm:
  - Tăng biến đếm đảo lên.
  - Gọi DFS để đánh dấu tất cả các ô đất nối liền với ô hiện tại.
- DFS sẽ đi tới các ô liền kề theo 4 hướng và "làm chìm" (đánh dấu) chúng để không tính lại.

## Giả mã (Pseudocode)

```text
function numIslands(grid):
    count = 0
    for i from 0 to rows-1:
        for j from 0 to cols-1:
            if grid[i][j] == '1':
                DFS(i, j)
                count += 1
    return count

function DFS(i, j):
    if i < 0 or j < 0 or i >= rows or j >= cols or grid[i][j] != '1':
        return
    grid[i][j] = '0'  // đánh dấu đã thăm
    for mỗi hướng (trái, phải, lên, xuống):
        DFS(i+dx, j+dy)
```

## Code mẫu C++

```cpp
#include <vector>
using namespace std;

class Solution {
public:
    void dfs(vector<vector<char>>& grid, int i, int j) {
        int rows = grid.size();
        int cols = grid[0].size();
        if (i < 0 || j < 0 || i >= rows || j >= cols || grid[i][j] != '1')
            return;
        grid[i][j] = '0';
        dfs(grid, i + 1, j);
        dfs(grid, i - 1, j);
        dfs(grid, i, j + 1);
        dfs(grid, i, j - 1);
    }

    int numIslands(vector<vector<char>>& grid) {
        if (grid.empty()) return 0;
        int count = 0;
        int rows = grid.size();
        int cols = grid[0].size();
        for (int i = 0; i < rows; ++i) {
            for (int j = 0; j < cols; ++j) {
                if (grid[i][j] == '1') {
                    dfs(grid, i, j);
                    count++;
                }
            }
        }
        return count;
    }
};
```

# Kết luận

Kỹ thuật DFS trên mảng 2D (loang ma trận) là công cụ cơ bản nhưng cực kỳ mạnh mẽ trong lập trình thi đấu. Thành thạo cách cài đặt DFS sẽ giúp bạn giải quyết được hàng loạt bài toán về đếm vùng, tìm diện tích lớn nhất, xác định tính liên thông,...

Hãy luyện tập thêm với các bài tương tự như:
- [Max Area of Island (LeetCode 695)](https://leetcode.com/problems/max-area-of-island/)
- [Flood Fill (LeetCode 733)](https://leetcode.com/problems/flood-fill/)
- [Surrounded Regions (LeetCode 130)](https://leetcode.com/problems/surrounded-regions/)
- [Count Sub Islands (LeetCode 1905)](https://leetcode.com/problems/count-sub-islands/)
- [Number of Distinct Islands (LeetCode 694)](https://leetcode.com/problems/number-of-distinct-islands/)
- [Closed Island (LeetCode 1254)](https://leetcode.com/problems/closed-island/)

Chúc bạn học tập vui vẻ và thành công!
