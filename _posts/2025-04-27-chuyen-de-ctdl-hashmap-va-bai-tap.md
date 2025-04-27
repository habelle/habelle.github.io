---
layout: post
title: Chuyên đề Cấu trúc dữ liệu HashMap trong C++
subtitle: Làm chủ HashMap để giải quyết các bài toán tối ưu trong lập trình thuật toán
tags: [HashMap, Data Structures]
author: Hoàng Hà
---

HashMap là một trong những cấu trúc dữ liệu quan trọng và được sử dụng rộng rãi nhất trong lập trình thi đấu. Với khả năng lưu trữ và truy xuất dữ liệu theo cặp khóa-giá trị trong thời gian trung bình O(1), HashMap giúp giải quyết nhanh chóng các bài toán kiểm tra sự tồn tại, đếm tần suất, ghép cặp, nhóm dữ liệu, và tối ưu hóa thuật toán từ O(n²) xuống O(n). Việc thuần thục sử dụng HashMap sẽ mở ra khả năng tiếp cận các bài toán kỹ thuật cao hơn, đồng thời nâng cao tốc độ và hiệu quả giải quyết bài thi trong môi trường giới hạn thời gian.


# 🧩 Giới thiệu chuyên đề: HashMap

## 1. HashMap là gì?

- HashMap (bản đồ băm) là một cấu trúc dữ liệu ánh xạ (key → value) cho phép **tìm kiếm**, **thêm**, **xoá** phần tử trung bình với độ phức tạp **O(1)**.
- Trong C++, có thể sử dụng `unordered_map`, `map` hoặc `set`, tuỳ mục đích bài toán.

## 2. Khi nào nên dùng HashMap?

- Cần kiểm tra sự tồn tại nhanh.
- Cần đếm tần suất phần tử.
- Cần nhóm dữ liệu dựa trên đặc trưng (grouping).
- Cần theo dõi trạng thái động của một tập dữ liệu.

## 3. Độ phức tạp
| Thao tác | Độ phức tạp trung bình |
|:---|:---|
| Thêm (Insert) | O(1) |
| Tìm kiếm (Find) | O(1) |
| Xoá (Erase) | O(1) |

> ⚡ Tuy nhiên trong trường hợp xấu (collision nặng), độ phức tạp có thể lên tới O(n).

---

# 📚 Danh sách bài tập từ dễ đến khó



---

# 📘 Bài 1: Two Sum

**Link bài gốc:** [LeetCode 1. Two Sum](https://leetcode.com/problems/two-sum/)

---

## Đề bài (dịch tiếng Việt)

Cho một mảng các số nguyên `nums` và một số nguyên `target`, hãy tìm **hai chỉ số** `i` và `j` (i < j) sao cho `nums[i] + nums[j] == target`.

Trả về mảng chứa hai chỉ số đó. Nếu có nhiều cặp thỏa mãn, trả về một cặp bất kỳ.

---

## Input

- Một mảng số nguyên `nums` (1 <= nums.length <= 10⁴)
- Một số nguyên `target` (-10⁹ <= target <= 10⁹)

## Output

- Mảng gồm hai số nguyên: `[i, j]`

---

## Ví dụ

### Ví dụ 1:

**Input:**
```
nums = [2,7,11,15]
target = 9
```

**Output:**
```
[0,1]
```
**Giải thích:** nums[0] + nums[1] = 2 + 7 = 9.

---

### Ví dụ 2:

**Input:**
```
nums = [3,2,4]
target = 6
```

**Output:**
```
[1,2]
```

---

## Ràng buộc (Constraints)

- Mỗi input có đúng một cặp đáp án.
- Không sử dụng lại cùng một phần tử hai lần.

---

# 🧠 Phân tích tư duy thuật toán

### Brute-force (cách đơn giản)

- Duyệt tất cả các cặp `(i, j)`.
- Kiểm tra `nums[i] + nums[j] == target`.
- Độ phức tạp: **O(n²)**.

### HashMap (cách tối ưu)

- Duyệt qua từng phần tử:
  - Với mỗi `nums[i]`, kiểm tra xem `target - nums[i]` đã tồn tại trong map chưa.
- Nếu có, ta đã tìm được cặp.
- Độ phức tạp: **O(n)** thời gian và **O(n)** bộ nhớ.

---

# 💻 Code mẫu C++

```cpp
#include <vector>
#include <unordered_map>
using namespace std;

vector<int> twoSum(vector<int>& nums, int target) {
    unordered_map<int, int> mp; // value -> index
    for (int i = 0; i < nums.size(); ++i) {
        int complement = target - nums[i];
        if (mp.count(complement)) {
            return {mp[complement], i};
        }
        mp[nums[i]] = i;
    }
    return {}; // không tìm thấy
}
```

---


---

# 📘 Bài 2: Contains Duplicate

**Link bài gốc:** [LeetCode 217. Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

---

## Đề bài (dịch tiếng Việt)

Cho một mảng số nguyên `nums`, hãy kiểm tra xem mảng đó có phần tử nào xuất hiện **nhiều hơn một lần** hay không.

Trả về `true` nếu tồn tại phần tử trùng, ngược lại trả về `false`.

---

## Input

- Một mảng số nguyên `nums` (1 <= nums.length <= 10⁵)
- -10⁹ <= nums[i] <= 10⁹

## Output

- Một giá trị `true` hoặc `false`.

---

## Ví dụ

### Ví dụ 1:

**Input:**
```
nums = [1,2,3,1]
```

**Output:**
```
true
```

### Ví dụ 2:

**Input:**
```
nums = [1,2,3,4]
```

**Output:**
```
false
```

---

## Ràng buộc (Constraints)

- 1 <= nums.length <= 10⁵
- -10⁹ <= nums[i] <= 10⁹

---

# 🧠 Phân tích tư duy thuật toán

### Brute-force

- Duyệt mọi cặp `(i, j)` kiểm tra `nums[i] == nums[j]`.
- Độ phức tạp **O(n²)** → Không chấp nhận với `n` lớn.

### HashMap (hoặc HashSet)

- Dùng `unordered_set`.
- Duyệt mảng:
  - Nếu phần tử đã tồn tại trong set → trả về `true`.
  - Nếu chưa → thêm vào set.
- Độ phức tạp trung bình: **O(n)**.

---

# 💻 Code mẫu C++

```cpp
#include <vector>
#include <unordered_set>
using namespace std;

bool containsDuplicate(vector<int>& nums) {
    unordered_set<int> seen;
    for (int num : nums) {
        if (seen.count(num)) return true;
        seen.insert(num);
    }
    return false;
}
```


---

# 📘 Bài 3: Intersection of Two Arrays

**Link bài gốc:** [LeetCode 349. Intersection of Two Arrays](https://leetcode.com/problems/intersection-of-two-arrays/)

---

## Đề bài (dịch tiếng Việt)

Cho hai mảng `nums1` và `nums2`, hãy trả về **mảng giao** của hai mảng (không chứa phần tử trùng lặp, thứ tự bất kỳ).

---

## Input

- Hai mảng số nguyên `nums1`, `nums2` (1 <= nums.length <= 10³)
- 0 <= nums[i] <= 10⁹

## Output

- Một mảng số nguyên chứa các phần tử giao nhau giữa `nums1` và `nums2`.

---

## Ví dụ

### Ví dụ 1:

**Input:**
```
nums1 = [1,2,2,1]
nums2 = [2,2]
```

**Output:**
```
[2]
```

### Ví dụ 2:

**Input:**
```
nums1 = [4,9,5]
nums2 = [9,4,9,8,4]
```

**Output:**
```
[9,4]
```

---

## Ràng buộc (Constraints)

- Các phần tử trong đầu ra không trùng lặp.

---

# 🧠 Phân tích tư duy thuật toán

### Brute-force

- Duyệt mỗi phần tử của `nums1`, kiểm tra có tồn tại trong `nums2` hay không.
- Độ phức tạp: **O(n*m)**.

### HashSet (Tối ưu)

- Đưa `nums1` vào set `s1`.
- Duyệt `nums2`:
  - Nếu `nums2[i]` tồn tại trong `s1`, thêm vào kết quả (dùng thêm set để tránh trùng lặp).
- Độ phức tạp trung bình: **O(n+m)**.

---

# 💻 Code mẫu C++

```cpp
#include <vector>
#include <unordered_set>
using namespace std;

vector<int> intersection(vector<int>& nums1, vector<int>& nums2) {
    unordered_set<int> s1(nums1.begin(), nums1.end());
    unordered_set<int> result;
    
    for (int num : nums2) {
        if (s1.count(num)) {
            result.insert(num);
        }
    }
    
    return vector<int>(result.begin(), result.end());
}
```


---

# 📘 Bài 4: Valid Anagram

**Link bài gốc:** [LeetCode 242. Valid Anagram](https://leetcode.com/problems/valid-anagram/)

## Đề bài (dịch tiếng Việt)

Cho hai chuỗi `s` và `t`, hãy kiểm tra xem chúng có phải là hoán vị (anagram) của nhau không.

## Input
- Hai chuỗi `s` và `t` (1 <= s.length, t.length <= 5*10⁴)
- Chuỗi chỉ chứa chữ cái thường.

## Output
- `true` nếu là hoán vị, `false` nếu không.

## Ví dụ

**Input:**
```
s = "anagram", t = "nagaram"
```

**Output:**
```
true
```

**Input:**
```
s = "rat", t = "car"
```

**Output:**
```
false
```

## Constraints
- Chỉ bao gồm chữ cái thường a-z.

## 🧠 Phân tích tư duy

- Đếm tần suất ký tự bằng HashMap.
- So sánh hai map.

## 💻 Code mẫu C++

```cpp
#include <unordered_map>
using namespace std;

bool isAnagram(string s, string t) {
    if (s.length() != t.length()) return false;
    unordered_map<char, int> count;
    for (char c : s) count[c]++;
    for (char c : t) {
        if (--count[c] < 0) return false;
    }
    return true;
}
```

---

# 📘 Bài 5: Subarray Sum Equals K

**Link bài gốc:** [LeetCode 560. Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/)

## Đề bài (dịch tiếng Việt)

Cho một mảng `nums` và một số nguyên `k`, đếm số đoạn con có tổng bằng `k`.

## Input
- Mảng `nums` (1 <= nums.length <= 2*10⁴)
- -1000 <= nums[i] <= 1000
- -10⁷ <= k <= 10⁷

## Output
- Số lượng đoạn con tổng đúng bằng k.

## Ví dụ

**Input:**
```
nums = [1,1,1]
k = 2
```

**Output:**
```
2
```

## 🧠 Phân tích tư duy

- Prefix Sum + HashMap lưu số lượng tổng phụ đã gặp.

## 💻 Code mẫu C++

```cpp
#include <unordered_map>
using namespace std;

int subarraySum(vector<int>& nums, int k) {
    unordered_map<int, int> mp;
    mp[0] = 1;
    int sum = 0, count = 0;
    for (int num : nums) {
        sum += num;
        count += mp[sum - k];
        mp[sum]++;
    }
    return count;
}
```

---

# 📘 Bài 6: Longest Consecutive Sequence

**Link bài gốc:** [LeetCode 128. Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)

## Đề bài (dịch tiếng Việt)

Tìm dãy con các số liên tiếp dài nhất.

## Input
- Mảng `nums` (0 <= nums.length <= 10⁵)

## Output
- Độ dài của dãy liên tiếp dài nhất.

## Ví dụ

**Input:**
```
nums = [100, 4, 200, 1, 3, 2]
```

**Output:**
```
4
```

## 🧠 Phân tích tư duy

- HashSet kiểm tra tồn tại số liên tiếp.
- Bắt đầu đếm khi gặp số không có tiền tố `x-1`.

## 💻 Code mẫu C++

```cpp
#include <unordered_set>
using namespace std;

int longestConsecutive(vector<int>& nums) {
    unordered_set<int> numSet(nums.begin(), nums.end());
    int longest = 0;
    for (int num : numSet) {
        if (!numSet.count(num - 1)) {
            int current = num;
            int streak = 1;
            while (numSet.count(current + 1)) {
                current++;
                streak++;
            }
            longest = max(longest, streak);
        }
    }
    return longest;
}
```

---

# 📘 Bài 7: Group Anagrams

**Link bài gốc:** [LeetCode 49. Group Anagrams](https://leetcode.com/problems/group-anagrams/)

## Đề bài (dịch tiếng Việt)

Nhóm các chuỗi hoán vị với nhau.

## Input
- Một mảng chuỗi (1 <= strs.length <= 10⁴)

## Output
- Mảng nhóm các hoán vị.

## Ví dụ

**Input:**
```
["eat","tea","tan","ate","nat","bat"]
```

**Output:**
```
[["bat"],["nat","tan"],["ate","eat","tea"]]
```

## 🧠 Phân tích tư duy

- Dùng HashMap với key là chuỗi đã sắp xếp ký tự.

## 💻 Code mẫu C++

```cpp
#include <vector>
#include <string>
#include <unordered_map>
#include <algorithm>
using namespace std;

vector<vector<string>> groupAnagrams(vector<string>& strs) {
    unordered_map<string, vector<string>> mp;
    for (string s : strs) {
        string key = s;
        sort(key.begin(), key.end());
        mp[key].push_back(s);
    }
    vector<vector<string>> result;
    for (auto& p : mp) result.push_back(p.second);
    return result;
}
```

---

# 📘 Bài 8: Count Number of Nice Subarrays

**Link bài gốc:** [LeetCode 1248. Count Number of Nice Subarrays](https://leetcode.com/problems/count-number-of-nice-subarrays/)

## Đề bài (dịch tiếng Việt)

Đếm số đoạn con có đúng `k` số lẻ.

## Input
- Mảng `nums` (1 <= nums.length <= 5*10⁴)

## Output
- Số lượng đoạn thỏa mãn.

## Ví dụ

**Input:**
```
nums = [1,1,2,1,1], k = 3
```

**Output:**
```
2
```

## 🧠 Phân tích tư duy

- Prefix sum trên số lượng số lẻ + HashMap.

## 💻 Code mẫu C++

```cpp
#include <unordered_map>
using namespace std;

int numberOfSubarrays(vector<int>& nums, int k) {
    unordered_map<int, int> count;
    count[0] = 1;
    int odd = 0, res = 0;
    for (int num : nums) {
        odd += num % 2;
        res += count[odd - k];
        count[odd]++;
    }
    return res;
}
```

---

# 📘 Bài 9: Longest Substring Without Repeating Characters

**Link bài gốc:** [LeetCode 3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

## Đề bài (dịch tiếng Việt)

Tìm chuỗi con dài nhất không chứa ký tự trùng.

## Input
- Chuỗi `s` (0 <= s.length <= 5*10⁴)

## Output
- Độ dài chuỗi con dài nhất.

## Ví dụ

**Input:**
```
s = "abcabcbb"
```

**Output:**
```
3
```

## 🧠 Phân tích tư duy

- Sliding Window + HashSet lưu ký tự.

## 💻 Code mẫu C++

```cpp
#include <unordered_set>
using namespace std;

int lengthOfLongestSubstring(string s) {
    unordered_set<char> seen;
    int left = 0, res = 0;
    for (int right = 0; right < s.size(); ++right) {
        while (seen.count(s[right])) {
            seen.erase(s[left++]);
        }
        seen.insert(s[right]);
        res = max(res, right - left + 1);
    }
    return res;
}
```

---

# 📘 Bài 10: Minimum Window Substring

**Link bài gốc:** [LeetCode 76. Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring/)

## Đề bài (dịch tiếng Việt)

Tìm cửa sổ nhỏ nhất trong `s` chứa đủ các ký tự trong `t`.

## Input
- Hai chuỗi `s` và `t`

## Output
- Chuỗi con nhỏ nhất.

## Ví dụ

**Input:**
```
s = "ADOBECODEBANC", t = "ABC"
```

**Output:**
```
"BANC"
```

## 🧠 Phân tích tư duy

- Sliding Window + HashMap đếm tần suất.

## 💻 Code mẫu C++

```cpp
#include <unordered_map>
using namespace std;

string minWindow(string s, string t) {
    unordered_map<char, int> need, window;
    for (char c : t) need[c]++;
    int left = 0, right = 0, valid = 0;
    int start = 0, len = INT_MAX;
    while (right < s.size()) {
        char c = s[right++];
        if (need.count(c)) {
            window[c]++;
            if (window[c] == need[c]) valid++;
        }
        while (valid == need.size()) {
            if (right - left < len) {
                start = left;
                len = right - left;
            }
            char d = s[left++];
            if (need.count(d)) {
                if (window[d] == need[d]) valid--;
                window[d]--;
            }
        }
    }
    return len == INT_MAX ? "" : s.substr(start, len);
}
```

