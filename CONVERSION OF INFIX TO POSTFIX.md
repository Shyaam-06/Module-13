# Exp.No:32  
## CONVERSION OF INFIX TO POSTFIX

---

### AIM  
To write a Python program to convert a given Infix expression to Postfix expression by following the precedence and associative rules. The input expression contains only Division, Subtraction, and Bitwise AND operators. A dictionary is used to set the priority for operators, and a set is used to hold the operators used in the given expression.

---

### ALGORITHM

1. **Start the program.**
2. **Initialize an empty stack** and an empty output string.
3. **Iterate through each character** in the infix expression:
   - If the character is **not an operator**, append it directly to the output string.
   - If the character is an **open parenthesis '('**, push it onto the stack.
   - If the character is a **close parenthesis ')'**, pop from the stack and append to the output until encountering a left parenthesis '('.
   - If the character is an **operator**, handle it based on precedence:
     - While there’s an operator at the top of the stack with higher or equal precedence, pop the stack and append those operators to the output.
     - Push the current operator onto the stack.
4. **Use a priority dictionary** to define operator precedence, ensuring higher precedence operators are placed before lower precedence ones.
5. Once the expression is fully processed, continue popping any remaining operators from the stack and append them to the output.
6. **Return the final postfix expression.**
7. **Print the result.**
8. **End the program.**

---

### PROGRAM

```

def infix_to_postfix(expression):
    stack = []
    output = ''
    operators = {'/', '-', '&'}
    precedence = {'/': 2, '-': 1, '&': 0}

    for char in expression:
        if char not in operators and char not in {'(', ')'}:
            output += char
        elif char == '(':
            stack.append(char)
        elif char == ')':
            while stack and stack[-1] != '(':
                output += stack.pop()
            stack.pop()
        else:
            while (stack and stack[-1] != '(' and
                   precedence[stack[-1]] >= precedence[char]):
                output += stack.pop()
            stack.append(char)

    while stack:
        output += stack.pop()

    return output

infix_expr = "a/(b-c)&d"
postfix_expr = infix_to_postfix(infix_expr)
print("Postfix Expression:", postfix_expr)


```

### OUTPUT
![image](https://github.com/user-attachments/assets/a1bbd52d-3175-4251-9951-cb21338e87f3)


### RESULT
Thus, the python program to convert a given Infix expression to Postfix expression by following the precedence and associative rules. The input expression contains only Division, Subtraction, and Bitwise AND operators. A dictionary is used to set the priority for operators, and a set is used to hold the operators used in the given expression has been executed and verified successfully.
