# Array 

+ [Fizz Buzz](#fizz-buzz)
+ [Max Consecutive Ones](#max-consecutive-ones)
+ [Matrix Diagonal Sum](#matrix-diagonal-sum)
+ [Two Sum](#two-sum)
+ [Two Sum II - Input Array Is Sorted](#two-sum-ii-input-array-is-sorted)
+ [Find First Palindromic String in the Array](#find-first-palindromic-string-in-the-array)
+ [Merge Sorted Array](#merge-sorted-array)
+ [Move Zeroes](#move-zeroes)
+ [Merge Intervals](#merge-intervals)

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

## Find First Palindromic String in the Array

https://leetcode.com/problems/find-first-palindromic-string-in-the-array/

```go
func isPalindrom(s string)bool {
   
    left,right := 0,len(s)-1
    for left <= right {
        if s[left]!=s[right]{
            return false 
        }
        left++
        right--
    }
    return true
}
func firstPalindrome(words []string) string {
    var res string 
    for _,w := range(words) {
        if isPalindrom(w) {
            res = w
            break
        }
   
    }
    return res
}

```

## Merge Sorted Array

https://leetcode.com/problems/merge-sorted-array/

```go
func merge(nums1 []int, m int, nums2 []int, n int)  {
    p := m + n -1 
    m = m-1 
    n = n-1
   
    
    for n>=0 {
        if m>=0 && nums1[m] > nums2[n]{
          
        
            nums1[p] = nums1[m]
            
            m--
        }else {
            nums1[p]=nums2[n]
          
            n--
        }
        p --
    }
    
}

```

## Move Zeroes

https://leetcode.com/problems/move-zeroes/

``` go
func moveZeroes(nums []int)  {
    j:= 0
    for i,_ := range nums {
        if nums[i]!=0{
            nums[i],nums[j] = nums[j],nums[i]
            fmt.Print(nums[i],nums[j])
            j++
        }
    }
}

```

## Merge Intervals

https://leetcode.com/problems/merge-intervals/submissions/

``` go
func merge(intervals [][]int) [][]int {
	if len(intervals) == 0 {
		return [][]int{}
	}

	var out [][]int
	sort.Slice(intervals, func(i, j int) bool {
		return intervals[i][0] < intervals[j][0]
	})

	start, end := intervals[0][0], intervals[0][1]
	for _, i := range intervals {
		if i[0] <= end {
			end = max(end, i[1])
        } else {
			out = append(out, []int{start, end})
			start, end = i[0], i[1]
		}
	}
	out = append(out, []int{start, end})

	return out
}

func max(a, b int) int {
	if a > b {
		return a
	}

	return b
}

```
