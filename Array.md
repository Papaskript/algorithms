# Array 

+ [Fizz Buzz](#fizz-buzz)

# Fizz Buzz

https://leetcode.com/problems/fizz-buzz/

```go
func fizzBuzz(n int) []string {
    var arr []string
    for i := 1; i <= n; i++ {
        if i % 3 == 0 && i % 5 == 0 {
            arr = append(arr,"FizzBuzz")
            
        } else if i % 3 == 0 {
            arr = append(arr,"Fizz")
            
        } else if i % 5 == 0 {
            arr = append(arr,"Buzz")
         
        } else {
            a := strconv.Itoa(i)
            
            arr = append(arr, a)
        }
    
}
    return arr
}

```
