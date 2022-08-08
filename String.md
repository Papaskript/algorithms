# String 

+ [To Lower Case](#to-lower-case)
+ [Valid Anagram](#valid-anagram)

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

