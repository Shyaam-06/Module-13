# Exp.No:31  
## IMPLEMENTATION OF STACK

---

### AIM  
To write a Python program to implement a stack using a list and its built-in methods (`append()`, `pop()`).

---

### ALGORITHM

1. **Start the program.**
2. **Define a class `st`** with the following methods:
   - `push(self, num)`: Adds the number `num` to the stack.
   - `pop(self)`: Removes and returns the top element from the stack.
3. **Create a stack object `s`** using the class `st`.
4. **Input the stack size**: Take an integer input `size` to define the size of the stack.
5. **Loop through numbers from 1 to size**: Add only the odd numbers to the stack using the `push()` method.
6. **Display the elements** in the stack after the loop completes.
7. **Call `pop()`** to remove the top element from the stack and display the popped element.
8. **Display the stack again** to show the remaining elements.
9. **End the program.**

---

### PROGRAM

```
class st:
    def __init__(self):
        self.stack = []

    def push(self, num):
        self.stack.append(num)

    def pop(self):
        if not self.stack:
            return "Stack is empty"
        return self.stack.pop()

    def display(self):
        return self.stack

s = st()
size = int(input("Enter the size of the stack: "))

for i in range(1, size + 1):
    if i % 2 != 0:
        s.push(i)

print("Stack after pushing odd numbers:", s.display())

popped = s.pop()
print("Popped element:", popped)

print("Stack after popping:", s.display())


```
### OUTPUT
![image](https://github.com/user-attachments/assets/cea8713a-9d2b-4be9-858c-66549979ea03)


### RESULT
Thus, the python program to implement a stack using a list and its built-in methods (`append()`, `pop()`) has been executed and verified successfully.
