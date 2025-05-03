---
layout: post
title: "Chuyên đề Tìm kiếm nhị phân: 10 bài có phân tích thuật toán"
subtitle: "Cách áp dụng kĩ thuật tối ưu từ duyệt -> Tìm kiếm nhị phân"
tags: [Phương pháp dạy học, Binary Search]
author: Hoàng Hà
---

Tìm kiếm nhị phân (Binary Search) là một trong những thuật toán cơ bản nhưng vô cùng quan trọng trong lập trình, đặc biệt trong các kỳ thi học sinh giỏi và lập trình thi đấu như USACO, Codeforces, LeetCode,... Thuật toán này hoạt động trên các cấu trúc dữ liệu có tính chất sắp xếp, giúp giảm độ phức tạp từ O(n) xuống O(log n) – một cải tiến mang tính bước ngoặt về hiệu năng.

Việc rèn luyện Binary Search không chỉ giúp học sinh thành thạo một kỹ thuật cốt lõi mà còn hình thành tư duy "thu hẹp không gian tìm kiếm", là nền tảng cho nhiều kỹ thuật nâng cao như tìm nhị phân đáp án (binary search on answer), tìm nghiệm nhị phân trên các hàm đơn điệu, hoặc khi kết hợp với các cấu trúc dữ liệu nâng cao như prefix sum, segment tree,...

Trong dạy học, Binary Search là chuyên đề lý tưởng để giúp học sinh rèn luyện các bước tư duy:

Nhận diện được điều kiện áp dụng nhị phân (hàm đơn điệu, dãy có thứ tự,...)

Biến đổi bài toán về dạng so sánh – quyết định

Thiết kế hàm kiểm tra và tổ chức chia miền hợp lý

Việc thành thạo Binary Search không chỉ giúp học sinh giải nhanh các bài toán dạng cơ bản, mà còn giúp các em tiếp cận những bài toán tư duy hóa sâu sắc – nơi mà lời giải không chỉ đúng mà còn phải cực kỳ tối ưu.

## Bài 1: Tìm kiếm nhị phân cơ bản

**Link bài gốc:** [LeetCode 704 - Binary Search](https://leetcode.com/problems/binary-search/)

### Mô tả bài toán

Cho một mảng số nguyên `nums` đã được **sắp xếp tăng dần**, và một số nguyên `target`. Hãy trả về **chỉ số** của phần tử bằng `target` trong mảng. Nếu không tồn tại, trả về `-1`.

### Input

* Một mảng số nguyên `nums` đã sắp xếp tăng dần
* Một số nguyên `target`

### Output

* Một số nguyên: chỉ số của phần tử `target` trong `nums`, hoặc `-1` nếu không tìm thấy

### Ví dụ

**Input:**

```
nums = [-1, 0, 3, 5, 9, 12], target = 9
```

**Output:**

```
4
```

**Giải thích:** `nums[4] = 9`

**Input:**

```
nums = [-1, 0, 3, 5, 9, 12], target = 2
```

**Output:**

```
-1
```

### Ràng buộc

* `1 ≤ nums.length ≤ 10^4`
* `-10^4 < nums[i], target < 10^4`
* `nums` không có phần tử trùng nhau
* `nums` đã được sắp xếp theo thứ tự tăng dần

---

### Phân tích giải thuật

#### Brute-force:

* Duyệt toàn bộ mảng, kiểm tra từng phần tử có bằng `target` không.
* **Độ phức tạp:** `O(n)`

#### Tối ưu bằng Binary Search:

* Dùng nhị phân để thu hẹp phạm vi tìm kiếm.
* Giả sử `left = 0`, `right = n - 1`, sau mỗi lần kiểm tra:

  * Nếu `nums[mid] == target` → trả về `mid`
  * Nếu `nums[mid] < target` → tìm phía phải (`left = mid + 1`)
  * Nếu `nums[mid] > target` → tìm phía trái (`right = mid - 1`)
* **Độ phức tạp:** `O(log n)`

---

### Code mẫu

#### C++

```cpp
int search(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] == target) return mid;
        else if (nums[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}
```

#### Python

```python
def search(nums, target):
    left, right = 0, len(nums) - 1
    while left <= right:
        mid = (left + right) // 2
        if nums[mid] == target:
            return mid
        elif nums[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1
```

---

## Bài 2: Vị trí chèn phần tử

**Link bài gốc:** [LeetCode 35 - Search Insert Position](https://leetcode.com/problems/search-insert-position/)

### Mô tả bài toán

Cho một mảng số nguyên đã **sắp xếp tăng dần** `nums` và một số nguyên `target`. Trả về **chỉ số** nơi `target` nên được chèn vào trong mảng để giữ thứ tự tăng dần. Nếu `target` đã tồn tại trong mảng, trả về chỉ số của nó.

### Input

* Một mảng số nguyên `nums` đã sắp xếp tăng dần
* Một số nguyên `target`

### Output

* Một số nguyên: chỉ số phù hợp để chèn `target`

### Ví dụ

**Input:**

```
nums = [1, 3, 5, 6], target = 5
```

**Output:**

```
2
```

**Input:**

```
nums = [1, 3, 5, 6], target = 2
```

**Output:**

```
1
```

### Ràng buộc

* `1 ≤ nums.length ≤ 10^4`
* `-10^4 ≤ nums[i], target ≤ 10^4`
* `nums` không có phần tử trùng nhau

---

### Phân tích giải thuật

#### Brute-force:

* Duyệt toàn bộ mảng, tìm vị trí đầu tiên mà `nums[i] ≥ target`
* **Độ phức tạp:** `O(n)`

#### Tối ưu bằng Binary Search:

* Tìm vị trí đầu tiên thỏa mãn `nums[i] ≥ target`
* Sử dụng biến `left = 0`, `right = n`, rút gọn tìm kiếm đến khi `left == right`
* **Độ phức tạp:** `O(log n)`

---

### Code mẫu

#### C++

```cpp
int searchInsert(vector<int>& nums, int target) {
    int left = 0, right = nums.size();
    while (left < right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] < target) left = mid + 1;
        else right = mid;
    }
    return left;
}
```

#### Python

```python
def searchInsert(nums, target):
    left, right = 0, len(nums)
    while left < right:
        mid = (left + right) // 2
        if nums[mid] < target:
            left = mid + 1
        else:
            right = mid
    return left
```

---

## Bài 3: Căn bậc hai của số nguyên

**Link bài gốc:** [LeetCode 69 - Sqrt(x)](https://leetcode.com/problems/sqrtx/)

### Mô tả bài toán

Cho một số nguyên không âm `x`, hãy tính **căn bậc hai nguyên** của `x`. Trả về kết quả làm tròn xuống (floor).

Không được sử dụng hàm thư viện như `sqrt`.

### Input

* Một số nguyên `x`

### Output

* Một số nguyên: căn bậc hai làm tròn xuống của `x`

### Ví dụ

**Input:**

```
x = 4
```

**Output:**

```
2
```

**Input:**

```
x = 8
```

**Output:**

```
2
```

**Giải thích:** Căn bậc hai của 8 là 2.828..., làm tròn xuống là 2

### Ràng buộc

* `0 ≤ x ≤ 2^31 - 1`

---

### Phân tích giải thuật

#### Brute-force:

* Duyệt `i` từ 0 đến `x`, kiểm tra `i * i <= x`
* Khi nào `i * i > x` thì dừng, trả về `i - 1`
* **Độ phức tạp:** `O(√x)`

#### Tối ưu bằng Binary Search:

* Tìm giá trị lớn nhất `mid` sao cho `mid * mid ≤ x`
* Dùng nhị phân với `left = 0`, `right = x`
* **Độ phức tạp:** `O(log x)`

---

### Code mẫu

#### C++

```cpp
int mySqrt(int x) {
    int left = 0, right = x, ans = 0;
    while (left <= right) {
        long long mid = (left + right) / 2;
        if (mid * mid <= x) {
            ans = mid;
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return ans;
}
```

#### Python

```python
def mySqrt(x):
    left, right = 0, x
    ans = 0
    while left <= right:
        mid = (left + right) // 2
        if mid * mid <= x:
            ans = mid
            left = mid + 1
        else:
            right = mid - 1
    return ans
```

---

## Bài 4: Phiên bản đầu tiên bị lỗi

**Link bài gốc:** [LeetCode 278 - First Bad Version](https://leetcode.com/problems/first-bad-version/)

### Mô tả bài toán

Bạn là lập trình viên đang phát triển một sản phẩm và các phiên bản được đánh số từ `1` đến `n`. Bạn được cung cấp một API `bool isBadVersion(version)` để kiểm tra xem phiên bản đó có lỗi không.

Giả định rằng một khi phiên bản `bad` xuất hiện thì tất cả các phiên bản sau nó cũng đều `bad`. Nhiệm vụ của bạn là tìm phiên bản đầu tiên bị lỗi.

### Input

* Một số nguyên `n`: tổng số phiên bản
* Hàm kiểm tra `isBadVersion(version)` được cung cấp sẵn

### Output

* Một số nguyên: chỉ số của phiên bản đầu tiên bị lỗi

### Ví dụ

**Input:**

```
n = 5, bad = 4
```

**Output:**

```
4
```

### Ràng buộc

* `1 ≤ bad ≤ n ≤ 2^31 - 1`

---

### Phân tích giải thuật

#### Brute-force:

* Duyệt từ 1 đến n, gọi `isBadVersion(i)`, nếu trả về true thì return i
* **Độ phức tạp:** `O(n)`

#### Tối ưu bằng Binary Search:

* Tìm giá trị nhỏ nhất `i` sao cho `isBadVersion(i)` là true
* Áp dụng binary search với `left = 1`, `right = n`
* Nếu `mid` là bad → tiếp tục tìm bên trái (có thể có bad sớm hơn)
* **Độ phức tạp:** `O(log n)`

---

### Code mẫu

#### C++

```cpp
// API isBadVersion(version) đã được định nghĩa
int firstBadVersion(int n) {
    int left = 1, right = n;
    while (left < right) {
        int mid = left + (right - left) / 2;
        if (isBadVersion(mid)) right = mid;
        else left = mid + 1;
    }
    return left;
}
```

#### Python

```python
# API isBadVersion(version) đã được định nghĩa
def firstBadVersion(n):
    left, right = 1, n
    while left < right:
        mid = (left + right) // 2
        if isBadVersion(mid):
            right = mid
        else:
            left = mid + 1
    return left
```

---

## Bài 5: Tìm ký tự nhỏ nhất lớn hơn target

**Link bài gốc:** [LeetCode 744 - Find Smallest Letter Greater Than Target](https://leetcode.com/problems/find-smallest-letter-greater-than-target/)

### Mô tả bài toán

Cho một mảng các chữ cái tiếng Anh in thường đã được **sắp xếp tăng dần** `letters`, và một ký tự `target`. Tìm ký tự nhỏ nhất trong `letters` **lớn hơn** `target`. Mảng có tính **vòng lặp**, nghĩa là nếu không có ký tự lớn hơn, trả về ký tự đầu tiên của mảng.

### Input

* Một mảng ký tự `letters` đã được sắp xếp tăng dần
* Một ký tự `target`

### Output

* Một ký tự: kết quả cần tìm

### Ví dụ

**Input:**

```
letters = ["c", "f", "j"], target = "a"
```

**Output:**

```
"c"
```

**Input:**

```
letters = ["c", "f", "j"], target = "k"
```

**Output:**

```
"c"
```

### Ràng buộc

* `2 ≤ letters.length ≤ 10^4`
* `letters[i]` là chữ cái in thường
* `letters` đã được sắp xếp tăng dần
* `letters` có thể chứa ký tự trùng

---

### Phân tích giải thuật

#### Brute-force:

* Duyệt từng phần tử trong mảng, tìm phần tử đầu tiên lớn hơn `target`
* Nếu không tìm thấy thì trả về phần tử đầu tiên
* **Độ phức tạp:** `O(n)`

#### Tối ưu bằng Binary Search:

* Dùng nhị phân tìm phần tử đầu tiên thỏa `letters[i] > target`
* Nếu không có phần tử nào thỏa, trả về `letters[0]`
* **Độ phức tạp:** `O(log n)`

---

### Code mẫu

#### C++

```cpp
char nextGreatestLetter(vector<char>& letters, char target) {
    int left = 0, right = letters.size();
    while (left < right) {
        int mid = left + (right - left) / 2;
        if (letters[mid] <= target) left = mid + 1;
        else right = mid;
    }
    return letters[left % letters.size()];
}
```

#### Python

```python
def nextGreatestLetter(letters, target):
    left, right = 0, len(letters)
    while left < right:
        mid = (left + right) // 2
        if letters[mid] <= target:
            left = mid + 1
        else:
            right = mid
    return letters[left % len(letters)]
```

---

## Bài 6: Tìm chỉ số đầu và cuối của phần tử trong mảng sắp xếp

**Link bài gốc:** [LeetCode 34 - Find First and Last Position of Element in Sorted Array](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/)

### Mô tả bài toán

Cho một mảng số nguyên `nums` đã được **sắp xếp tăng dần**, và một số nguyên `target`. Hãy tìm **chỉ số đầu tiên và chỉ số cuối cùng** của `target` trong mảng. Nếu không tìm thấy, trả về `[-1, -1]`.

### Input

* Một mảng số nguyên `nums`
* Một số nguyên `target`

### Output

* Một mảng gồm 2 phần tử: `[first_index, last_index]`

### Ví dụ

**Input:**

```
nums = [5,7,7,8,8,10], target = 8
```

**Output:**

```
[3,4]
```

**Input:**

```
nums = [5,7,7,8,8,10], target = 6
```

**Output:**

```
[-1,-1]
```

### Ràng buộc

* `0 ≤ nums.length ≤ 10^5`
* `-10^9 ≤ nums[i], target ≤ 10^9`
* `nums` đã được sắp xếp tăng dần

---

### Phân tích giải thuật

#### Brute-force:

* Duyệt từ đầu đến cuối tìm `first_index`, rồi từ cuối về đầu tìm `last_index`
* **Độ phức tạp:** `O(n)`

#### Tối ưu bằng Binary Search:

* Dùng 2 lần nhị phân:

  * Lần 1: tìm vị trí đầu tiên ≥ `target`
  * Lần 2: tìm vị trí cuối cùng ≤ `target`
* **Độ phức tạp:** `O(log n)`

---

### Code mẫu

#### C++

```cpp
int findFirst(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1, ans = -1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] >= target) {
            if (nums[mid] == target) ans = mid;
            right = mid - 1;
        } else {
            left = mid + 1;
        }
    }
    return ans;
}

int findLast(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1, ans = -1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] <= target) {
            if (nums[mid] == target) ans = mid;
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return ans;
}

vector<int> searchRange(vector<int>& nums, int target) {
    return {findFirst(nums, target), findLast(nums, target)};
}
```

#### Python

```python
def searchRange(nums, target):
    def findFirst():
        left, right, ans = 0, len(nums) - 1, -1
        while left <= right:
            mid = (left + right) // 2
            if nums[mid] >= target:
                if nums[mid] == target:
                    ans = mid
                right = mid - 1
            else:
                left = mid + 1
        return ans

    def findLast():
        left, right, ans = 0, len(nums) - 1, -1
        while left <= right:
            mid = (left + right) // 2
            if nums[mid] <= target:
                if nums[mid] == target:
                    ans = mid
                left = mid + 1
            else:
                right = mid - 1
        return ans

    return [findFirst(), findLast()]
```

---

## Bài 7: Tìm phần tử trong mảng xoay

**Link bài gốc:** [LeetCode 33 - Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)

### Mô tả bài toán

Cho một mảng `nums` đã được **xoay** tại một chỉ số không xác định (mảng ban đầu được sắp xếp tăng dần), và một số nguyên `target`. Hãy tìm chỉ số của `target` trong mảng. Nếu không tồn tại, trả về `-1`.

### Input

* Một mảng số nguyên `nums` (có thể đã xoay)
* Một số nguyên `target`

### Output

* Một số nguyên: chỉ số của phần tử `target`, hoặc `-1` nếu không có

### Ví dụ

**Input:**

```
nums = [4,5,6,7,0,1,2], target = 0
```

**Output:**

```
4
```

**Input:**

```
nums = [4,5,6,7,0,1,2], target = 3
```

**Output:**

```
-1
```

### Ràng buộc

* `1 ≤ nums.length ≤ 5000`
* `-10^4 ≤ nums[i], target ≤ 10^4`
* `nums` không có phần tử trùng nhau

---

### Phân tích giải thuật

#### Brute-force:

* Duyệt từng phần tử trong mảng, kiểm tra từng giá trị
* **Độ phức tạp:** `O(n)`

#### Tối ưu bằng Binary Search:

* Mỗi bước kiểm tra `nums[mid]` nằm ở nửa đã sắp xếp:

  * Nếu `nums[left] <= nums[mid]`, bên trái đã sắp xếp

    * Nếu `nums[left] <= target < nums[mid]` → tìm bên trái
    * Ngược lại → tìm bên phải
  * Nếu không, bên phải đã sắp xếp

    * Nếu `nums[mid] < target <= nums[right]` → tìm bên phải
    * Ngược lại → tìm bên trái
* **Độ phức tạp:** `O(log n)`

---

### Code mẫu

#### C++

```cpp
int search(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] == target) return mid;
        if (nums[left] <= nums[mid]) {
            if (nums[left] <= target && target < nums[mid]) right = mid - 1;
            else left = mid + 1;
        } else {
            if (nums[mid] < target && target <= nums[right]) left = mid + 1;
            else right = mid - 1;
        }
    }
    return -1;
}
```

#### Python

```python
def search(nums, target):
    left, right = 0, len(nums) - 1
    while left <= right:
        mid = (left + right) // 2
        if nums[mid] == target:
            return mid
        if nums[left] <= nums[mid]:
            if nums[left] <= target < nums[mid]:
                right = mid - 1
            else:
                left = mid + 1
        else:
            if nums[mid] < target <= nums[right]:
                left = mid + 1
            else:
                right = mid - 1
    return -1
```

---

## Bài 8: Phần tử xuất hiện một lần duy nhất trong mảng đã sắp xếp

**Link bài gốc:** [LeetCode 540 - Single Element in a Sorted Array](https://leetcode.com/problems/single-element-in-a-sorted-array/)

### Mô tả bài toán

Cho một mảng `nums` đã được **sắp xếp tăng dần**, trong đó **mỗi phần tử xuất hiện đúng hai lần**, ngoại trừ **một phần tử duy nhất xuất hiện một lần**. Hãy tìm phần tử xuất hiện một lần đó.

### Input

* Một mảng số nguyên `nums`, có độ dài lẻ

### Output

* Một số nguyên là phần tử duy nhất trong mảng

### Ví dụ

**Input:**

```
nums = [1,1,2,3,3,4,4,8,8]
```

**Output:**

```
2
```

**Input:**

```
nums = [3,3,7,7,10,11,11]
```

**Output:**

```
10
```

### Ràng buộc

* `1 ≤ nums.length ≤ 10^5`
* `nums.length` là số lẻ
* `0 ≤ nums[i] ≤ 10^5`
* `nums` đã sắp xếp tăng dần

---

### Phân tích giải thuật

#### Brute-force:

* Duyệt từng cặp, kiểm tra nếu `nums[i] != nums[i+1]` thì đó là phần tử đơn lẻ
* **Độ phức tạp:** `O(n)`

#### Tối ưu bằng Binary Search:

* Với chỉ số `mid` chẵn:

  * Nếu `nums[mid] == nums[mid+1]`, phần tử đơn lẻ nằm phía phải
  * Ngược lại, nằm phía trái hoặc chính giữa
* Với `mid` lẻ:

  * So sánh với `mid - 1` tương tự
* **Độ phức tạp:** `O(log n)`

---

### Code mẫu

#### C++

```cpp
int singleNonDuplicate(vector<int>& nums) {
    int left = 0, right = nums.size() - 1;
    while (left < right) {
        int mid = left + (right - left) / 2;
        if (mid % 2 == 1) mid--;
        if (nums[mid] == nums[mid+1]) left = mid + 2;
        else right = mid;
    }
    return nums[left];
}
```

#### Python

```python
def singleNonDuplicate(nums):
    left, right = 0, len(nums) - 1
    while left < right:
        mid = (left + right) // 2
        if mid % 2 == 1:
            mid -= 1
        if nums[mid] == nums[mid + 1]:
            left = mid + 2
        else:
            right = mid
    return nums[left]
```

---

## Bài 9: Tốc độ ăn chuối tối thiểu

**Link bài gốc:** [LeetCode 875 - Koko Eating Bananas](https://leetcode.com/problems/koko-eating-bananas/)

### Mô tả bài toán

Koko có một số đống chuối, mỗi đống có `piles[i]` quả chuối. Cô ấy ăn với tốc độ `k` quả chuối mỗi giờ, nếu trong 1 giờ đống chuối có ít hơn `k` quả thì cô ăn hết đống đó. Hãy tìm tốc độ nhỏ nhất `k` sao cho Koko ăn hết tất cả chuối trong vòng `h` giờ.

### Input

* Một mảng `piles` gồm `n` số nguyên dương, mỗi số là số chuối trong một đống
* Một số nguyên `h`, là số giờ Koko có thể ăn

### Output

* Một số nguyên: tốc độ tối thiểu `k` (số chuối/giờ)

### Ví dụ

**Input:**

```
piles = [3,6,7,11], h = 8
```

**Output:**

```
4
```

**Input:**

```
piles = [30,11,23,4,20], h = 5
```

**Output:**

```
30
```

### Ràng buộc

* `1 ≤ piles.length ≤ 10^4`
* `piles[i] ∈ [1, 10^9]`
* `h ∈ [1, 10^9]`

---

### Phân tích giải thuật

#### Brute-force:

* Thử từng tốc độ `k` từ 1 đến max(piles), tính tổng thời gian cần → chọn tốc độ nhỏ nhất thoả mãn
* **Độ phức tạp:** `O(max(piles) * n)` → quá lớn khi `piles[i] = 10^9`

#### Tối ưu bằng Binary Search:

* Áp dụng binary search trên khoảng `k ∈ [1, max(piles)]`
* Với mỗi `k`, tính tổng thời gian cần: `sum((pile + k - 1) // k)`
* Nếu tổng thời gian ≤ `h`, ta thử `k` nhỏ hơn
* **Độ phức tạp:** `O(n * log(max(piles)))`

---

### Code mẫu

#### C++

```cpp
int minEatingSpeed(vector<int>& piles, int h) {
    int left = 1, right = *max_element(piles.begin(), piles.end());
    int ans = right;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        long long hours = 0;
        for (int p : piles) {
            hours += (p + mid - 1) / mid;
        }
        if (hours <= h) {
            ans = mid;
            right = mid - 1;
        } else {
            left = mid + 1;
        }
    }
    return ans;
}
```

#### Python

```python
def minEatingSpeed(piles, h):
    left, right = 1, max(piles)
    ans = right
    while left <= right:
        mid = (left + right) // 2
        hours = sum((p + mid - 1) // mid for p in piles)
        if hours <= h:
            ans = mid
            right = mid - 1
        else:
            left = mid + 1
    return ans
```

---

## Bài 10: Phân phối gói hàng trong số ngày tối thiểu

**Link bài gốc:** [LeetCode 1011 - Capacity To Ship Packages Within D Days](https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/)

### Mô tả bài toán

Bạn có một danh sách các gói hàng, mỗi gói có trọng lượng `weights[i]`. Bạn cần vận chuyển toàn bộ gói hàng trong `days` ngày. Mỗi ngày, bạn phải vận chuyển các gói hàng liên tiếp nhau, và tổng trọng lượng không vượt quá `capacity` (trọng tải tàu).

Tìm giá trị nhỏ nhất của `capacity` sao cho có thể giao hết hàng trong `days` ngày.

### Input

* Mảng số nguyên `weights` là trọng lượng các gói hàng
* Một số nguyên `days` là số ngày vận chuyển

### Output

* Một số nguyên: trọng tải tàu nhỏ nhất cần thiết

### Ví dụ

**Input:**

```
weights = [1,2,3,4,5,6,7,8,9,10], days = 5
```

**Output:**

```
15
```

**Input:**

```
weights = [3,2,2,4,1,4], days = 3
```

**Output:**

```
6
```

### Ràng buộc

* `1 ≤ weights.length ≤ 5 * 10^4`
* `1 ≤ weights[i] ≤ 500`
* `1 ≤ days ≤ weights.length`

---

### Phân tích giải thuật

#### Brute-force:

* Thử từng `capacity` từ max(weights) đến sum(weights), kiểm tra liệu có thể chia thành ≤ `days` đoạn
* **Độ phức tạp:** `O(n * (sum - max))`

#### Tối ưu bằng Binary Search:

* Miền tìm kiếm `capacity` là từ `max(weights)` đến `sum(weights)`
* Với mỗi `mid`, kiểm tra xem có thể chia thành ≤ `days` ngày không bằng cách duyệt tuyến tính
* **Độ phức tạp:** `O(n log(sum - max))`

---

### Code mẫu

#### C++

```cpp
bool canShip(vector<int>& weights, int days, int capacity) {
    int current = 0, d = 1;
    for (int w : weights) {
        if (current + w > capacity) {
            d++;
            current = 0;
        }
        current += w;
    }
    return d <= days;
}

int shipWithinDays(vector<int>& weights, int days) {
    int left = *max_element(weights.begin(), weights.end());
    int right = accumulate(weights.begin(), weights.end(), 0);
    int ans = right;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (canShip(weights, days, mid)) {
            ans = mid;
            right = mid - 1;
        } else {
            left = mid + 1;
        }
    }
    return ans;
}
```

#### Python

```python
def canShip(weights, days, capacity):
    current, d = 0, 1
    for w in weights:
        if current + w > capacity:
            d += 1
            current = 0
        current += w
    return d <= days

def shipWithinDays(weights, days):
    left, right = max(weights), sum(weights)
    ans = right
    while left <= right:
        mid = (left + right) // 2
        if canShip(weights, days, mid):
            ans = mid
            right = mid - 1
        else:
            left = mid + 1
    return ans
```

---
## Tổng kết

Chuyên đề Binary Search là một trong những nền tảng cốt lõi mà mọi học sinh luyện thi lập trình cần nắm vững. Thông qua việc thực hành với 10 bài toán có độ khó tăng dần, học sinh không chỉ rèn luyện kỹ năng cài đặt mà quan trọng hơn là phát triển tư duy thu hẹp không gian tìm kiếm, xác định miền giá trị hợp lý và viết các hàm kiểm tra chính xác.

Các bài tập trong chuyên đề này bao phủ đa dạng các kiểu ứng dụng: từ tìm kiếm vị trí chính xác, tìm giá trị đầu tiên / cuối cùng thoả mãn điều kiện, đến tìm nhị phân trên hàm đơn điệu và tối ưu đáp án. Sự quen thuộc với các mô hình binary search này là bước đệm cần thiết để học sinh chinh phục các bài toán khó hơn ở các kỳ thi quốc gia và quốc tế.

Giáo viên có thể sử dụng tài liệu này để tổ chức buổi luyện tập theo từng nhóm bài, hướng dẫn học sinh tư duy từ brute-force đến tối ưu, và khuyến khích học sinh tự viết code, tự kiểm tra test và phân tích độ phức tạp. Đây là một trong những bước quan trọng để xây dựng tư duy giải quyết vấn đề và sự trưởng thành trong hành trình học thuật của mỗi học sinh.

**Nếu bạn cần test để phục vụ mục đích dạy học hãy liên hệ với tôi [mailto: hahoangthi@gmail.com]**


