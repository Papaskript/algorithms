# Binary search

+ [Binary Search](#binary-search)

## Binary Search

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
