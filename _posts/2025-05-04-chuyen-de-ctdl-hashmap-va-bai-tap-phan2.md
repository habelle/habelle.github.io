---
layout: post
title: "Luyện tập Cấu trúc Dữ liệu Map (HashMap) - Phần 2"
subtitle: "Tổng hợp 19 bài tập tiêu biểu sử dụng CTDL map với độ khó tăng dần"
tags: [HashMap]
author: Hoàng Hà
---


# Luyện tập Cấu trúc Dữ liệu Map (HashMap) qua 10 bài LeetCode

Tài liệu này tổng hợp 10 bài tập tiêu biểu sử dụng `map` trên LeetCode, theo thứ tự tăng dần độ khó. Mỗi bài gồm:
- Link bài gốc
- Tóm tắt đề bài
- Vai trò của HashMap
- Hướng giải
- Code mẫu (C++ và Python)

---


## ✅ Bài 1: Two Sum  
🔗 [LeetCode 1 - Two Sum](https://leetcode.com/problems/two-sum/)

### 📝 Tóm tắt đề bài
Cho mảng `nums` và một số nguyên `target`. Tìm hai chỉ số i, j sao cho `nums[i] + nums[j] == target`.

### 🎯 Vai trò của HashMap
Dùng map lưu: `giá trị -> chỉ số`. Truy xuất ngược giá trị còn thiếu `target - nums[i]` trong O(1).

### 💡 Gợi ý hướng làm
- Duyệt từng phần tử `nums[i]`
- Tính `complement = target - nums[i]`
- Nếu `complement` đã có trong `map` → trả về chỉ số
- Nếu chưa → lưu `nums[i]` vào map

### 💻 Code mẫu

#### C++
```cpp
vector<int> twoSum(vector<int>& nums, int target) {
    unordered_map<int, int> mp;
    for (int i = 0; i < nums.size(); ++i) {
        int complement = target - nums[i];
        if (mp.count(complement)) return {mp[complement], i};
        mp[nums[i]] = i;
    }
    return {};
}
```

#### Python
```python
def twoSum(nums, target):
    mp = {}
    for i, num in enumerate(nums):
        complement = target - num
        if complement in mp:
            return [mp[complement], i]
        mp[num] = i
    return []
```

---

## ✅ Bài 2: First Unique Character in a String  
🔗 [LeetCode 387 - First Unique Character in a String](https://leetcode.com/problems/first-unique-character-in-a-string/)

### 📝 Tóm tắt đề bài
Cho một chuỗi `s`, hãy tìm chỉ số ký tự đầu tiên không lặp lại. Nếu không có, trả về -1.

### 🎯 Vai trò của HashMap
Sử dụng `map<char, int>` để đếm tần suất xuất hiện của mỗi ký tự.

### 💡 Gợi ý hướng làm
- Duyệt 1: đếm số lần xuất hiện của từng ký tự
- Duyệt 2: tìm ký tự đầu tiên có tần suất = 1 → trả về chỉ số
- Nếu không có ký tự nào thỏa → trả về -1

### 💻 Code mẫu

#### C++
```cpp
int firstUniqChar(string s) {
    unordered_map<char, int> freq;
    for (char c : s) freq[c]++;
    for (int i = 0; i < s.size(); ++i) {
        if (freq[s[i]] == 1) return i;
    }
    return -1;
}
```

#### Python
```python
def firstUniqChar(s):
    from collections import Counter
    freq = Counter(s)
    for i, c in enumerate(s):
        if freq[c] == 1:
            return i
    return -1
```

---

## ✅ Bài 3: Valid Anagram  
🔗 [LeetCode 242 - Valid Anagram](https://leetcode.com/problems/valid-anagram/)

### 📝 Tóm tắt đề bài
Cho hai chuỗi `s` và `t`, kiểm tra xem `t` có phải là một hoán vị của `s` hay không (tức là chứa cùng ký tự với số lượng giống nhau, không phân biệt thứ tự).

### 🎯 Vai trò của HashMap
Dùng `map<char, int>` để đếm tần suất ký tự trong chuỗi `s` và trừ dần khi duyệt `t`. Nếu tất cả về 0 → là hoán vị.

### 💡 Gợi ý hướng làm
- Nếu độ dài khác nhau → không thể là hoán vị
- Đếm số lần xuất hiện ký tự trong `s`
- Duyệt `t`, giảm đếm. Nếu có ký tự không tồn tại hoặc đếm < 0 → sai
- Hoặc dùng `Counter(s) == Counter(t)` trong Python

### 💻 Code mẫu

#### C++
```cpp
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

#### Python
```python
def isAnagram(s, t):
    from collections import Counter
    return Counter(s) == Counter(t)
```

---

## ✅ Bài 4: Ransom Note  
🔗 [LeetCode 383 - Ransom Note](https://leetcode.com/problems/ransom-note/)

### 📝 Tóm tắt đề bài
Cho hai chuỗi `ransomNote` và `magazine`. Kiểm tra xem có thể tạo ra `ransomNote` từ các ký tự của `magazine` hay không. Mỗi ký tự trong `magazine` chỉ được dùng một lần.

### 🎯 Vai trò của HashMap
Dùng map để đếm số lượng ký tự trong `magazine`, sau đó kiểm tra từng ký tự trong `ransomNote`.

### 💡 Gợi ý hướng làm
- Đếm số lượng ký tự trong `magazine`
- Duyệt `ransomNote`, giảm số lượng tương ứng
- Nếu không đủ → trả về false

### 💻 Code mẫu

#### C++
```cpp
bool canConstruct(string ransomNote, string magazine) {
    unordered_map<char, int> count;
    for (char c : magazine) count[c]++;
    for (char c : ransomNote) {
        if (count[c] == 0) return false;
        count[c]--;
    }
    return true;
}
```

#### Python
```python
def canConstruct(ransomNote, magazine):
    from collections import Counter
    cnt = Counter(magazine)
    for c in ransomNote:
        if cnt[c] == 0:
            return False
        cnt[c] -= 1
    return True
```

---

## ✅ Bài 5: Contains Duplicate II  
🔗 [LeetCode 219 - Contains Duplicate II](https://leetcode.com/problems/contains-duplicate-ii/)

### 📝 Tóm tắt đề bài
Cho mảng `nums` và số nguyên `k`. Kiểm tra xem có tồn tại hai chỉ số i, j sao cho `nums[i] == nums[j]` và `|i - j| ≤ k`.

### 🎯 Vai trò của HashMap
Dùng map để lưu chỉ số gần nhất của mỗi giá trị trong mảng.

### 💡 Gợi ý hướng làm
- Duyệt từng phần tử, nếu phần tử đã có trong map:
  - Kiểm tra khoảng cách `i - lastIndex ≤ k`
  - Nếu đúng → trả về true
- Nếu không có hoặc sai điều kiện → cập nhật map

### 💻 Code mẫu

#### C++
```cpp
bool containsNearbyDuplicate(vector<int>& nums, int k) {
    unordered_map<int, int> lastSeen;
    for (int i = 0; i < nums.size(); ++i) {
        if (lastSeen.count(nums[i]) && i - lastSeen[nums[i]] <= k)
            return true;
        lastSeen[nums[i]] = i;
    }
    return false;
}
```

#### Python
```python
def containsNearbyDuplicate(nums, k):
    lastSeen = {}
    for i, val in enumerate(nums):
        if val in lastSeen and i - lastSeen[val] <= k:
            return True
        lastSeen[val] = i
    return False
```

---

## ✅ Bài 6: 4Sum II  
🔗 [LeetCode 454 - 4Sum II](https://leetcode.com/problems/4sum-ii/)

### 📝 Tóm tắt đề bài
Cho 4 mảng `A`, `B`, `C`, `D`, mỗi mảng có n phần tử. Tìm số bộ 4 `(i, j, k, l)` sao cho `A[i] + B[j] + C[k] + D[l] == 0`.

### 🎯 Vai trò của HashMap
Dùng map để lưu tổng `A[i] + B[j]` → đếm số lần xuất hiện. Sau đó duyệt `C[k] + D[l]` và tìm phần bù trong map.

### 💡 Gợi ý hướng làm
- Duyệt qua tất cả cặp `(A[i], B[j])`, lưu tổng vào map
- Duyệt qua tất cả `(C[k], D[l])`, tính `-(C[k] + D[l])` → cộng dồn theo số lần xuất hiện trong map

### 💻 Code mẫu

#### C++
```cpp
int fourSumCount(vector<int>& A, vector<int>& B, vector<int>& C, vector<int>& D) {
    unordered_map<int, int> abSum;
    for (int a : A)
        for (int b : B)
            abSum[a + b]++;
    int count = 0;
    for (int c : C)
        for (int d : D)
            count += abSum[-(c + d)];
    return count;
}
```

#### Python
```python
def fourSumCount(A, B, C, D):
    from collections import Counter
    abSum = Counter(a + b for a in A for b in B)
    return sum(abSum[-(c + d)] for c in C for d in D)
```

---

## ✅ Bài 7: Top K Frequent Elements  
🔗 [LeetCode 347 - Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/)

### 📝 Tóm tắt đề bài
Cho mảng `nums` và số nguyên `k`. Trả về `k` phần tử xuất hiện nhiều nhất (thứ tự không quan trọng).

### 🎯 Vai trò của HashMap
Dùng map để đếm tần suất xuất hiện các số, sau đó chọn top-k phần tử theo tần suất.

### 💡 Gợi ý hướng làm
- Đếm tần suất bằng hashmap
- Sử dụng heap hoặc bucket để lấy top-k phần tử tần suất cao nhất

### 💻 Code mẫu

#### C++
```cpp
vector<int> topKFrequent(vector<int>& nums, int k) {
    unordered_map<int, int> freq;
    for (int num : nums) freq[num]++;
    priority_queue<pair<int, int>> pq;
    for (auto& [num, count] : freq)
        pq.emplace(count, num);
    vector<int> res;
    while (k-- && !pq.empty()) {
        res.push_back(pq.top().second);
        pq.pop();
    }
    return res;
}
```

#### Python
```python
def topKFrequent(nums, k):
    from collections import Counter
    return [item[0] for item in Counter(nums).most_common(k)]
```

---

## ✅ Bài 8: Valid Sudoku  
🔗 [LeetCode 36 - Valid Sudoku](https://leetcode.com/problems/valid-sudoku/)

### 📝 Tóm tắt đề bài
Cho bảng Sudoku 9x9, kiểm tra xem trạng thái hiện tại có hợp lệ hay không (không trùng số trong hàng, cột, và khối 3x3).

### 🎯 Vai trò của HashMap
Dùng 3 hashmap hoặc set để lưu trạng thái:
- `rows[i]`: số đã xuất hiện ở hàng i
- `cols[j]`: số đã xuất hiện ở cột j
- `boxes[i//3][j//3]`: số trong khối 3x3

### 💡 Gợi ý hướng làm
- Duyệt từng ô trong bảng
- Nếu không phải '.', kiểm tra xem đã tồn tại ở hàng/cột/khối chưa
- Nếu trùng → không hợp lệ

### 💻 Code mẫu

#### C++
```cpp
bool isValidSudoku(vector<vector<char>>& board) {
    unordered_set<string> seen;
    for (int i = 0; i < 9; ++i)
        for (int j = 0; j < 9; ++j) {
            char c = board[i][j];
            if (c == '.') continue;
            string row = to_string(c) + " in row " + to_string(i);
            string col = to_string(c) + " in col " + to_string(j);
            string box = to_string(c) + " in box " + to_string(i/3) + "-" + to_string(j/3);
            if (!seen.insert(row).second || !seen.insert(col).second || !seen.insert(box).second)
                return false;
        }
    return true;
}
```

#### Python
```python
def isValidSudoku(board):
    seen = set()
    for i in range(9):
        for j in range(9):
            num = board[i][j]
            if num == '.':
                continue
            if (num, i) in seen or (num, j + 9) in seen or (num, i//3, j//3) in seen:
                return False
            seen.add((num, i))
            seen.add((num, j + 9))
            seen.add((num, i//3, j//3))
    return True
```

---

## ✅ Bài 9: Longest Consecutive Sequence  
🔗 [LeetCode 128 - Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)

### 📝 Tóm tắt đề bài
Cho một mảng số nguyên `nums`, hãy tìm độ dài của chuỗi con gồm các số liên tiếp dài nhất (không cần liên tiếp trong mảng, không trùng lặp).

### 🎯 Vai trò của HashMap
Sử dụng `unordered_set` (cũng dựa trên hash table) để kiểm tra nhanh xem phần tử liền trước có tồn tại không (bắt đầu chuỗi), từ đó mở rộng chuỗi liên tiếp.

### 💡 Gợi ý hướng làm
- Đưa tất cả phần tử vào set
- Duyệt từng phần tử:
  - Nếu phần tử - 1 **không có** trong set → bắt đầu chuỗi mới
  - Tăng dần đến khi không còn phần tử kế tiếp
  - Cập nhật độ dài chuỗi liên tiếp dài nhất

### 💻 Code mẫu

#### C++
```cpp
int longestConsecutive(vector<int>& nums) {
    unordered_set<int> s(nums.begin(), nums.end());
    int longest = 0;
    for (int num : s) {
        if (!s.count(num - 1)) {
            int length = 1;
            while (s.count(num + length)) ++length;
            longest = max(longest, length);
        }
    }
    return longest;
}
```

#### Python
```python
def longestConsecutive(nums):
    num_set = set(nums)
    longest = 0
    for num in num_set:
        if num - 1 not in num_set:
            length = 1
            while num + length in num_set:
                length += 1
            longest = max(longest, length)
    return longest
```

---

## ✅ Bài 10: Substring with Concatenation of All Words  
🔗 [LeetCode 30 - Substring with Concatenation of All Words](https://leetcode.com/problems/substring-with-concatenation-of-all-words/)

### 📝 Tóm tắt đề bài
Cho một chuỗi `s` và một mảng `words`, trong đó tất cả các từ có độ dài bằng nhau. Hãy tìm tất cả các vị trí bắt đầu của các chuỗi con trong `s` là sự nối liền **không trùng lặp** của tất cả từ trong `words` (theo mọi thứ tự).

### 🎯 Vai trò của HashMap
Dùng `map<string, int>` để đếm tần suất từ trong `words` và so sánh với các sliding window trong chuỗi `s`.

### 💡 Gợi ý hướng làm
- Mỗi từ có độ dài cố định `wordLen`, tổng chuỗi cần xét có độ dài `wordLen * len(words)`
- Với mỗi offset `i ∈ [0, wordLen)`, duyệt sliding window chia theo từng từ
- Dùng hashmap đếm từ xuất hiện trong đoạn kiểm tra

### 💻 Code mẫu

#### C++
```cpp
vector<int> findSubstring(string s, vector<string>& words) {
    if (words.empty()) return {};
    int wordLen = words[0].size();
    int totalLen = wordLen * words.size();
    unordered_map<string, int> wordCount;
    for (auto& w : words) wordCount[w]++;
    
    vector<int> result;
    for (int i = 0; i < wordLen; ++i) {
        unordered_map<string, int> window;
        int left = i, count = 0;
        for (int j = i; j + wordLen <= s.size(); j += wordLen) {
            string word = s.substr(j, wordLen);
            if (wordCount.count(word)) {
                window[word]++;
                count++;
                while (window[word] > wordCount[word]) {
                    window[s.substr(left, wordLen)]--;
                    count--;
                    left += wordLen;
                }
                if (count == words.size()) result.push_back(left);
            } else {
                window.clear();
                count = 0;
                left = j + wordLen;
            }
        }
    }
    return result;
}
```

#### Python
```python
def findSubstring(s, words):
    from collections import Counter
    if not s or not words:
        return []
    word_len = len(words[0])
    total_len = word_len * len(words)
    word_count = Counter(words)
    result = []

    for i in range(word_len):
        left = i
        curr_count = Counter()
        count = 0
        for j in range(i, len(s) - word_len + 1, word_len):
            word = s[j:j+word_len]
            if word in word_count:
                curr_count[word] += 1
                count += 1
                while curr_count[word] > word_count[word]:
                    curr_count[s[left:left+word_len]] -= 1
                    count -= 1
                    left += word_len
                if count == len(words):
                    result.append(left)
            else:
                curr_count.clear()
                count = 0
                left = j + word_len
    return result
```

---

## ✅ Bài 9: Longest Consecutive Sequence  
🔗 [LeetCode 128 - Longest Consecutive Sequence](https://leetcode.com/problems/longest-consecutive-sequence/)

### 📝 Tóm tắt đề bài
Cho một mảng số nguyên chưa sắp xếp. Tìm độ dài dãy số liên tiếp dài nhất.

### 🎯 Vai trò của HashMap
Dùng set/map để lưu các phần tử và kiểm tra sự tồn tại của phần tử liên tiếp. Tránh sort để giữ độ phức tạp O(n).

### 💡 Gợi ý hướng làm
- Dùng `unordered_set` lưu tất cả phần tử
- Duyệt từng phần tử `num`:
  - Nếu `num - 1` không tồn tại → bắt đầu chuỗi mới
  - Duyệt `num + 1, num + 2,...` để đếm độ dài dãy liên tiếp

### 💻 Code mẫu

#### C++
```cpp
int longestConsecutive(vector<int>& nums) {
    unordered_set<int> s(nums.begin(), nums.end());
    int maxLen = 0;
    for (int num : s) {
        if (!s.count(num - 1)) {
            int cur = num, len = 1;
            while (s.count(cur + 1)) {
                cur++;
                len++;
            }
            maxLen = max(maxLen, len);
        }
    }
    return maxLen;
}
```

#### Python
```python
def longestConsecutive(nums):
    s = set(nums)
    max_len = 0
    for num in s:
        if num - 1 not in s:
            cur = num
            length = 1
            while cur + 1 in s:
                cur += 1
                length += 1
            max_len = max(max_len, length)
    return max_len
```

---

## ✅ Bài 10: Substring with Concatenation of All Words  
🔗 [LeetCode 30 - Substring with Concatenation of All Words](https://leetcode.com/problems/substring-with-concatenation-of-all-words/)

### 📝 Tóm tắt đề bài
Cho chuỗi `s` và mảng `words`, mỗi từ có độ dài bằng nhau. Tìm tất cả các chỉ số bắt đầu của chuỗi con trong `s` là sự nối tiếp của tất cả từ trong `words`, không trùng và không thừa.

### 🎯 Vai trò của HashMap
Dùng map đếm số lượng từ trong `words`, sau đó kiểm tra chuỗi con theo sliding window.

### 💡 Gợi ý hướng làm
- Duyệt từ `i = 0` đến `word_len - 1`:
  - Duyệt từng khung có kích thước `len(words) * word_len`
  - Dùng hashmap đếm từ trong cửa sổ, so sánh với từ đã cho

### 💻 Code mẫu

#### C++
```cpp
vector<int> findSubstring(string s, vector<string>& words) {
    vector<int> res;
    if (words.empty()) return res;
    int wordLen = words[0].length(), wordCount = words.size();
    int totalLen = wordLen * wordCount;
    unordered_map<string, int> wordMap;
    for (auto& w : words) wordMap[w]++;

    for (int i = 0; i < wordLen; ++i) {
        unordered_map<string, int> window;
        int left = i, count = 0;
        for (int j = i; j + wordLen <= s.length(); j += wordLen) {
            string w = s.substr(j, wordLen);
            if (wordMap.count(w)) {
                window[w]++;
                count++;
                while (window[w] > wordMap[w]) {
                    string leftWord = s.substr(left, wordLen);
                    window[leftWord]--;
                    left += wordLen;
                    count--;
                }
                if (count == wordCount) res.push_back(left);
            } else {
                window.clear();
                count = 0;
                left = j + wordLen;
            }
        }
    }
    return res;
}
```

#### Python
```python
def findSubstring(s, words):
    from collections import Counter
    if not words:
        return []
    word_len = len(words[0])
    total_len = word_len * len(words)
    word_count = Counter(words)
    res = []

    for i in range(word_len):
        left = i
        cur_count = Counter()
        count = 0
        for j in range(i, len(s) - word_len + 1, word_len):
            word = s[j:j+word_len]
            if word in word_count:
                cur_count[word] += 1
                count += 1
                while cur_count[word] > word_count[word]:
                    left_word = s[left:left+word_len]
                    cur_count[left_word] -= 1
                    left += word_len
                    count -= 1
                if count == len(words):
                    res.append(left)
            else:
                cur_count.clear()
                count = 0
                left = j + word_len
    return res
```

---
