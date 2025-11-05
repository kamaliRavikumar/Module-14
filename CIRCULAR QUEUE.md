# Exp No: 36  
## Circular Queue 
---

### AIM  
To write a Python program with a function to insert float values into a Circular Queue.

---

### ALGORITHM

1. Start  
2. Check if the Circular Queue is full  
   - If `size == max_size`, print `"Queue is full"` and exit the function  
3. If the queue is not full:  
   - Read the element to be inserted  
   - Convert it to float  
   - Insert the element at the `tail` position  
   - Update tail using: `tail = (tail + 1) % max_size` (circular increment)  
   - Increment `size` by 1  
4. End

---

### PROGRAM

```
class Queue:
    def __init__(self,limit):
        self.queue=[]
        self.rear=0
        self.front=0
        self.limit=limit
    def isempty(self):
        if len(self.queue)==0:
            return True
        else:
            return False
    def enqueue(self,item):
        if len(self.queue)==self.limit:
            print("the queue is full")


        else:
            if self.front==self.limit:
                self.front=self.rear-1

            self.queue.insert(self.front,item)
            self.front+=1
    def dequeue(self):
        if len(self.queue)==0:
            print("the stack is under flow")
        else:
            if self.rear==self.limit:
                self.rear=0
            self.queue.pop(self.rear)
            self.rear+=1
    def display(self):
        print(self.queue)

size=int(input())
a=Queue(size)
str=float(input())
str1=float(input())
str2=float(input())

a.enqueue(str)
a.enqueue(str1)
a.enqueue(str2)
a.display()
a.dequeue()
a.display()

```

### OUTPUT
<img width="1206" height="215" alt="image" src="https://github.com/user-attachments/assets/10983f87-0eed-46f0-9ce2-50d99670747e" />


### RESULT
Thus The program creates a queue, adds three float values, displays them, removes one value, and shows the updated queue.
