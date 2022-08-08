## Array 

+ [Fizz Buzz](#fizz-buzz)
+ [Max Consecutive Ones](#max-consecutive-ones)
+ [Matrix Diagonal Sum](#matrix-diagonal-sum)

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

# Max Consecutive Ones

https://leetcode.com/problems/max-consecutive-ones/

```go
func findMaxConsecutiveOnes(nums []int) int {
    var prev int
    var curr int 
    for i:=0; i < len(nums);i++ {
        if nums[i] == 1 {
            curr++
           
            if prev <= curr {
                prev = curr
                
            }
        }else {
            curr = 0
        }
    }
    return prev
}

```

# Matrix Diagonal Sum

https://leetcode.com/problems/matrix-diagonal-sum/

```go
func diagonalSum(mat [][]int) int {
    var x int = 0
    var y int = 0
    n := len(mat)
    for i:=0;i<len(mat);i++{
        for j:=0;j<len(mat);j++{
            if i==j{
                y += mat[i][j]
            }else if i+j == n-1{
                x += mat[i][j]
            }
        }  
            
        
    }
    return x+y
}

```
