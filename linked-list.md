# linked list

+ [Design Linked List](#design-linked-list)

##  Design Linked List

https://leetcode.com/problems/design-linked-list/

```go
type Node struct {
    Val int 
    Next *Node
}

type MyLinkedList struct {
 Head *Node
 length int
  
}


func Constructor() MyLinkedList {
    return MyLinkedList{}

}


func (this *MyLinkedList) Get(index int) int {
    if index < 0{
        return -1
    }
    cur := this.Head
    
    i:=0
    
    for cur != nil{
        if i == index{
        
            return cur.Val
            
        }
        i++
        cur = cur.Next
    }
    
return -1 
}


func (this *MyLinkedList) AddAtHead(val int)  {
    
    if this.Head == nil {
        this.Head = &Node{Val: val}
        
        this.length++
            return
        }
        newNode := &Node{Val:val,Next: this.Head}

        this.Head = newNode
    
        this.length++
        return;
    }



func (this *MyLinkedList) AddAtTail(val int)  {
    if this.AddAtTail == nil{
        this.AddAtTail(val)
        return
    }
    cur:= this.Head
    
    for cur.Next != nil {
        cur = cur.Next
    }
     cur.Next = &Node{Val: val}
    this.length++
    return
}


func (this *MyLinkedList) AddAtIndex(index int, val int)  {
     if index == 0 {
        this.AddAtHead(val)
        return
    }
    if index == this.length {
        this.AddAtTail(val)
        return
    }
    if index > this.length {
        return
    }
    
    i := 0
    cur := this.Head
    for cur.Next != nil {
        if i == index - 1 {
            newNode := &Node{Val: val, Next: cur.Next}
            cur.Next = newNode
            this.length++
            return
        }
        i++
        cur = cur.Next
    }
}


func (this *MyLinkedList) DeleteAtIndex(index int)  {
    if index < 0 || index >= this.length {
        return
    }
    if index == 0 {
        this.Head = this.Head.Next
        this.length--
        return
    }
    
    i := 0
    cur := this.Head 
    for cur.Next != nil {
        if i == index - 1 {
            cur.Next = cur.Next.Next
            this.length--
            return
        }
        i++
        cur = cur.Next
    }
}

```
