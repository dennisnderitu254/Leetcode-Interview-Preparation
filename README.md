# Leetcode Problems - Blind 75

### 1768. Merge Strings Alternately

You are given two strings `word1` and `word2`. Merge the strings by adding letters in alternating order, starting with `word1`. If a string is longer than the other, append the additional letters onto the end of the merged string.

Return the merged string.

```
Example 1:

Input: word1 = "abc", word2 = "pqr"
Output: "apbqcr"
Explanation: The merged string will be merged as so:
word1:  a   b   c
word2:    p   q   r
merged: a p b q c r
Example 2:

Example 2:

Input: word1 = "ab", word2 = "pqrs"
Output: "apbqrs"
Explanation: Notice that as word2 is longer, "rs" is appended to the end.
word1:  a   b
word2:    p   q   r   s
merged: a p b q   r   s
Example 3:

Example 3:

Input: word1 = "abcd", word2 = "pq"
Output: "apbqcd"
Explanation: Notice that as word1 is longer, "cd" is appended to the end.
word1:  a   b   c   d
word2:    p   q
merged: a p b q c   d
```

Constraints:

- `1 <= word1.length, word2.length <= 100`
- `word1` and `word2` consist of lowercase English letters.

### Solution

```
class Solution(object):
    def mergeAlternately(self, word1, word2):
        """
        :type word1: str
        :type word2: str
        :rtype: str
        """
        merged = []
        i, j = 0, 0

        while i < len(word1) and j < len(word2):
            merged.append(word1[i])
            merged.append(word2[j])
            i += 1
            j += 1

        #Append the remaining letters from word1
        while i < len(word1):
            merged.append(word1[i])
            i += 1

        #Append the remaining letters from word2
        while j < len(word2):
            merged.append(word2[j])
            j += 1

        return ''.join(merged)

# Example Usage
# word1 = "abc"
# word2 = "pqr"
# solution = Solution()
# output = solution.mergeAlternately(word1, word2)
# print(output)
```

**Explanation 1**

This code defines a class `Solution` with a method `mergeAlternately` that takes two input strings `word1` and `word2` and returns the merged string according to the specified alternating order.

The code uses two pointers (`i` and `j`) to iterate through the characters of both words and alternately appends them to the `merged` list.

After one of the words is exhausted, the code appends the remaining characters from the other word.

Finally, the `merged` list is joined into a string and returned as the output.

**Explanation2**

This code defines a class called `Solution` with a method called `mergeAlternately()`. This method takes two strings, `word1` and `word2`, as input and returns a new string that is created by merging the two strings alternately.

The method works by first creating an empty list called `merged`. Then, it uses two pointers, `i` and `j`, to iterate over the two strings. While both pointers are within the bounds of their respective strings, the method appends the characters at those positions to the `merged` list.

Once both pointers have reached the end of their respective strings, the method checks to see if either string has any remaining characters. If so, it appends those characters to the `merged` list.

Finally, the method returns a new string that is created by joining the characters in the `merged` list together.