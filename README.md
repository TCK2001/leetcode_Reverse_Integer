# leetcode_Reverse_Integer
+ 0을제외한 모든 것을 반대로 출력하기
+ 除了0以外的所有數字由反過來輸出

-----
+ Example1
```
Input: x = 123
Output: 321
```
----
+ Example2
```
Input: x = -123
Output: -321
```
----
+ Example3
```
Input: x = 120
Output: 21
```
----
```python
class Solution:
    def reverse(self, x: int) -> int:
        strings = str(x)
        res = '' # - 기호를 저장 할 곳을 만듬
  
        if strings[0] == '-': # 만약 - 마이너스 표시가 있을경우 따로 저장을 해놓음 
            res += strings[0]
            strings = strings.replace("-","") # 그리고 - 마이너스를 기존에 string 에서 지움

        elif strings == '0' and len(strings) == 1: # 만약 0 하나만 있을경우 0 반환
            return(strings)

        strings = strings[::-1] # 코드가 여기까지오면 숫자만 남게 되어있음 그래서 모든걸 뒤집어줌
        while strings[0] == '0' and len(strings) > 1: # 뒤집어서 while문으로 0을 하나씩 지워가기
            strings = strings[1:]
        if int(strings) >= -2 ** 31 and int(strings) < 2 ** 31: #뒤집은 결과값이 문제에서 준 범위보다 작을시 출력
            return(res+strings)
        else: # 아니면 0출력
            return(0)
```
---
```
결론 : 
이번 문제의 핵심은 0을 지우는 방법인것같다 0만 따로 지우는 방법을 안다면 어려움이 없을듯하다
```
---
```
結論:
這次的題目只要知道處理0的方式就好解決了，大致上還可以的題目
```
---
### Result
Runtime: 32 ms, faster than 94.56% of Python3 online submissions for Reverse Integer.\
Memory Usage: 13.9 MB, less than 15.53% of Python3 online submissions for Reverse Integer.
