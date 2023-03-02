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
+ [Maximum Product of Two Elements in an Array](#maximum-product-of-two-elements-in-an-array)
+ [Maximum Product of Two Elements in an Array 2](#maximum-product-of-two-elements-in-an-array)
+ [Longest Consecutive Sequence](#longest-consecutive-sequence)
+ [Intersection of Two Arrays](#intersection-of-two-arrays)
+ [Remove Duplicates from Sorted Array](#remove-duplicates-from-sorted-array)

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

##  Maximum Product of Two Elements in an Array

https://leetcode.com/problems/maximum-product-of-two-elements-in-an-array/

```go
func ist(a int) int {
    var res int = (a - 1)
    
 return res
}

func maxProduct(nums []int) int {
    var first int
    var second int
    var max int
    var f int
    var s int
    sort.Ints(nums)
    
    
    f = len(nums)-1
    s = len(nums)-2

    first = ist(nums[f])
    second = ist(nums[s])
    max = first * second
    
 return max   
}

```

## Maximum Product of Two Elements in an Array 2 

https://leetcode.com/problems/maximum-product-of-two-elements-in-an-array/

```go 
func maxProduct(nums []int) int {
    max1,max2 := 0,0
for i:=0;i<len(nums);i++ {
    if nums[i] > max1 {
        max2 = max1
        max1 = nums[i]
        continue
        
    }
    if nums[i] > max2 {
        max2 = nums[i]
    }
    
    }
    return (max1 - 1)*(max2 - 1)
}

```

## Longest Consecutive Sequence

https://leetcode.com/problems/longest-consecutive-sequence/

```go
func longestConsecutive(nums []int) int {
    if len(nums)==0{
        return 0
    }
    sort.Ints(nums)
    longest:=1
    current:=1
    prev:= nums[0]
   for i := 1; i < len(nums); i++ {
       if nums[i]==prev+1{
           current++
       }else if nums[i]!=prev{
           current =1
       }
       prev = nums[i]
       longest = max(longest,current)
	}
    return longest
}

func max(i int, j int) int {
    if i > j {
        return i
    }
    return j
}

```

##  Intersection of Two Arrays

https://leetcode.com/problems/intersection-of-two-arrays/

```go
func intersection(nums1 []int, nums2 []int) []int {
   var out []int
   var min int
   m := make(map[int]int)
   n := make(map[int]int)
  
    
    for _,v:= range nums1 {
       m[v] += 1  
    }
     for _,v:= range nums2 {
       n[v] += 1 
    }
    
    
    for val := range m {
        min = m[val]
        if min > n[val]{
            min = n[val]
        }
          if min > 0 {
        out = append(out,val)
    }
        
    }
    return out
}

```

## Remove Duplicates from Sorted Array

https://leetcode.com/problems/remove-duplicates-from-sorted-array

```go
func removeDuplicates(nums []int) int {
   var j int = 1 
   for i:=0;i<len(nums)-1;i++ {
       if nums[i]!= nums[i+1]{
           nums[j]= nums[i+1]
           j++
       }
       
   }
    
    return j
}

```

## Valid Anagram 

https://leetcode.com/problems/valid-anagram/description/

```go 
func isAnagram(s string, t string) bool {

nums := make([]int,26)

for _,v := range s {
    i := (v -'a')
    nums[i]++
}
for _,v := range t {
    i := (v - 'a')
    nums[i]--
}
for _, v := range nums {
    if v != 0 {
        return false
    }
}
return true
}

```
