# Stack

+ [Min Stack](#min-stack)

## Min Stack

https://leetcode.com/problems/min-stack/

```go
type inStack struct {
    sl []int
}


func (s *inStack) empty() bool {
	return len(s.sl) == 0
}


func (s *inStack) push(n int) {
    s.sl = append(s.sl,n)
}


func (s *inStack) peek() int {
    if s.empty() {
        panic("stack is empty")
    }
    return s.sl[len(s.sl)-1]
}


func (s *inStack) pop() int {
    if s.empty() {
        panic("stack is empty")
    }
    val := s.sl[len(s.sl)-1]
    s.sl = s.sl[:len(s.sl)-1]
    
    return val
}

type MinStack struct {
     mins inStack
     nums inStack
    
}


func Constructor() MinStack {
    return MinStack{}
}


func (this *MinStack) Push(x int)  {
    this.nums.push(x)
    
    if this.mins.empty() || x <= this.mins.peek() {
        this.mins.push(x)
    }
    
}


func (this *MinStack) Pop()  {
    val := this.nums.pop()
    
    if val == this.mins.peek() {
        this.mins.pop()
    }
 
    
}


func (this *MinStack) Top() int {
    return this.nums.peek() 
}
    



func (this *MinStack) GetMin() int {
    return this.mins.peek()
}

```
