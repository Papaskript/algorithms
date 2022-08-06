# Binary search

+ [Binary Search](#binary-search)
+ [Sqrt(x)](#sqrtx)
+ [Guess Number Higher or Lower](#guess-number-higher-or-lower)

## Binary Search

https://leetcode.com/problems/binary-search/

```go
func search(nums []int, target int) int {
    
    var low int = 0
    var high int = len(nums)-1
    var mid int = 0
    
    
    
    for low <= high {
        mid = (low + high)/2
        if nums[mid] < target {
            low = mid +1
            
        }else if nums[mid] > target{
            high = mid -1
           
            
        } 
        if nums[mid] == target{
            return mid
        }
            
         
    }
return -1
}

```

## Sqrt(x)

https://leetcode.com/problems/sqrtx/

```go
func mySqrt(x int) int {
    if x <= 1 {
        return x
    }
    
    low := 0
    high := x
    mid := 0
    
    for low <= high {
        mid = low + (high - low) / 2
    
        if mid == x / mid {
            return mid
        }else if mid > x / mid{
            high = mid - 1
        } else {
            low = mid + 1
        }
    }
    
    if low * low > mid {
        return low - 1
    }
    
    return low
}

```

## Guess Number Higher or Lower

https://leetcode.com/problems/guess-number-higher-or-lower/

```go
func guessNumber(n int) int {
    low := 1
    high := n
    mid := 0
    res := 0 
  
    for low <= high {
        mid = low + (high - low)/2
       
        res = guess(mid)
        if res == -1 {
            high = mid -1
        }else if res == 1 {
            low = mid +1
        } else if res == 0 {
            return mid 
        }
            
        
        
    }
    return mid
}

```
