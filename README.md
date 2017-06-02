# 010Regular-Expression-Matching

'.' Matches any single character.
'*' Matches zero or more of the preceding element.
The matching should cover the entire input string (not partial).
The function prototype should be:
bool isMatch(const char *s, const char *p)

Some examples:
isMatch("aa","a") → false
isMatch("aa","aa") → true
isMatch("aaa","aa") → false
isMatch("aa", "a*") → true
isMatch("aa", ".*") → true
isMatch("ab", ".*") → true
isMatch("aab", "c*a*b") → true

题目为正则匹配，初步思路两个字符串一个一个相比较，如果匹配接着子字符串相比较，如果不匹配的话返回false，大概是一个递归的思路。
具体字符串情况如下，
如果s为空，p为空，返回true
如果p长度为1，s为空，返回false
如果p度为1，s度为1，判断是否匹配，如果p是.或者相同，返回true，否则返回false
如果p长度>1，判断第二位是否是*
    如果是*，判断s是否匹配p，如果匹配，去掉匹配后的子字符串接着下一步匹配，如果匹配返回false
    如果不是*，判断第一位是否匹配s，如果匹配接着子字符串，如果不匹配返回false
    
代码如下：
public class Solution {
    public boolean isMatch(String s, String p) {
        
        //if(s.isEmpty() && p.isEmpty())
        //      return true;
        
        if(p.isEmpty()) return s.isEmpty();
        
        if(p.size() == 1 ) 
            return (s.size == 1) && (s[0] == p[0] || p[0] =='.');
        
        if(p[1] != '*'){
            if(s.isEmpty()) return false;
            
        }
        
    }
}
