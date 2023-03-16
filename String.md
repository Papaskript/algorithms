# String 

+ [To Lower Case](#to-lower-case)
+ [Valid Anagram](#valid-anagram)
+ [Valid Palindrome](#valid-palindrome)
+ [Sorting the Sentence](#sorting-the-sentence)
+ [Group Anagrams](#group-anagrams)
+ [Reverse Vowels of a String](#reverse-vowels-of-a-string)
+ [Check if Numbers Are Ascending in a Sentence](#Check-if-Numbers-Are-Ascending-in-a-Sentence)

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

## Group Anagrams

https://leetcode.com/problems/group-anagrams/

```go
func groupAnagrams(strs []string) [][]string {
    result := [][]string{}
    
    m := map[string][]string{}
    
    for _, str:=range strs {
        r:=[]rune(str)
       
        sort.Slice(r, func(i,j int) bool { return r[i]<r[j] })
        sorted_str :=string(r)
        fmt.Print(sorted_str," ")
        m[sorted_str] = append(m[sorted_str], str)
    }
    
    for _,arr := range m {
        result = append(result, arr)
    }
    
    return result
}

```

## Reverse Vowels of a String

https://leetcode.com/problems/reverse-vowels-of-a-string/

```go
func isVowel(c byte) bool {
    return c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u' || c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U' 
        
    }



func reverseVowels(s string) string {
 l,r := 0,len(s)-1
    result := []byte(s)
    
for{
    for l<r {
    if isVowel(result[l]){
        break
    }
    l++
}

    for l<r {
        if isVowel(result[r]){
            break
        }
        r--
}
    if l<r {
        result[l],result[r] = result[r],result[l]
        l++
        r--
    }else {
        break
    }
}
return string(result)

}

```

## Check if Numbers Are Ascending in a Sentence

https://leetcode.com/problems/check-if-numbers-are-ascending-in-a-sentence/description/

```go
func areNumbersAscending(s string) bool {
    arr := strings.Split(s," ")
    var res []int
    var flag bool
  
    //var ints []int
   for _,v := range arr {
     if i, err := strconv.Atoi(v); err == nil{
      res = append(res,i)
     }else {
         continue
     }
   }
  
left := 0
next := 1 
right := len(res)-1

for left < right {
    if res[left]>=res[next] {
        flag = false
        break

    }else {
        flag = true
    }
    left++
    next++
}

return flag
}

```
