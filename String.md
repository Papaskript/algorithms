# String 

+ [To Lower Case](#to-lower-case)
+ [Valid Anagram](#valid-anagram)
+ [Valid Palindrome](#valid-palindrome)
+ [Sorting the Sentence](#sorting-the-sentence)

## To Lower Case

https://leetcode.com/problems/to-lower-case/

```go
func toLowerCase(s string) string {
    
    var test []rune
    
    
    
    for _,v:= range s{
        
        if v >= 65 && v <= 90{
            v += 32
            test = append(test,v)
        }else {
            
            test = append(test,v)
           
        }
       
        }
        
         
    
    return string(test)
}

```

## Valid Anagram

https://leetcode.com/problems/valid-anagram/

```go
 func isAnagram(s string, t string) bool {
    sr := map[byte]int{}
    tr := map[byte]int{}
    
    if len(s) != len(t) {
        return false
    }
    
    for i:=0; i<len(s); i++ {
        sr[s[i]] += 1
        tr[t[i]] += 1
        fmt.Print(tr)
    }
    
    for i:=0; i<len(s); i++ {
        if sr[s[i]] != tr[s[i]] {
            return false
        }
    }
    
    return true
}

```

## Valid Palindrome

https://leetcode.com/problems/valid-palindrome/

```go
func cToLower(c byte) byte {
	if c >= 'A' && c <= 'Z' {
		c += 32
	}
	return c
}


func AlphainAm(c byte) bool {
      return (c >= '0' && c <= '9') ||
        (c >= 'a' && c <= 'z') ||
        (c >= 'A' && c <= 'Z')
}


func isPalindrome(s string) bool {
    if s == ""{
        return true 
    }
    left,right := 0,len(s)-1
    
    for left < right {
        for left < right && !AlphainAm(s[left]){
            left++
        }
        for left < right && !AlphainAm(s[right]){
            right--
        }
        if cToLower(s[left])!= cToLower(s[right]){
            return false 
        }
        left++
        right-- 
    }

   
  return true 
}

```

## Sorting the Sentence

https://leetcode.com/problems/sorting-the-sentence/

```go
func sortSentence(s string) string {
    arr := strings.Split(s," ")
    
    sorted := make([]string,len(arr))
    
    for _,word := range arr {
        end:= len(word)-1
        index := int(word[end]-'1')
        
        sorted[index] = word[:end] 
       
    }
    return strings.Join(sorted," ")
}

```
