# Array 

+ [Fizz Buzz](#fizz-buzz)
+ [Max Consecutive Ones](#max-consecutive-ones)
+ [Matrix Diagonal Sum](#matrix-diagonal-sum)
+ [Two Sum](#two-sum)
+ [Two Sum II - Input Array Is Sorted](#two-sum-ii-input-array-is-sorted)

## Fizz Buzz

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

## Max Consecutive Ones

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

## Matrix Diagonal Sum

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

## Two Sum

https://leetcode.com/problems/two-sum/

```go
func twoSum(nums []int, target int) []int {
     var sum []int
    for i,v:= range nums {
        for i2,v2 := range nums{
            if target == v+v2 && i!=i2 {
                sum = append(sum, i,i2)
                return sum
            }
        }
    }
    return sum
}

```

## Two Sum II - Input Array Is Sorted

https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/

```go
func twoSum(numbers []int, target int) []int {
    numbersize := len(numbers)
    res := []int{0,0}
    if numbersize <= 1 {
        return res
    }
    left,right := 0,numbersize-1
    for left < right {
        totalsum := numbers[left] + numbers[right]
        if totalsum < target {
            left++
        }else if totalsum > target{
            right-- 
        }else if  totalsum == target {
            res[0] = left +1
            res[1] = right +1
            return res
        }
    }
    return res
}

```
