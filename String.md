# String 

+ [To Lower Case](#to-lower-case)

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

