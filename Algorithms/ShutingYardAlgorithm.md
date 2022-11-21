# Shuting Yard Algorithm

In computer science, the shunting yard algorithm is a method for parsing arithmetical or logical expressions, or a combination of both, specified in infix notation. It can produce either a postfix notation string, also known as Reverse Polish notation (RPN), or an abstract syntax tree (AST)
***
```python
def ShutingYard(s: str):
    output = []
    stack = []
    op_o1 = "+-"
    op_o2 = "*/%"
    for c in s:
        if c.isdigit():
            output.append(c)
        elif c == "(":
            stack.append(c)
        elif c == ")":
            while stack and stack[-1] != "(":
                output.append(stack.pop())
            if stack and stack[-1] == "(":
                stack.pop()
            else:
                return ParseError("Missing closing parenthesis)
        elif c in op_o1:
            while stack and stack[-1] in op_o2:
                output.append(stack.pop())
            stack.append(c)

    for elem in stack:
        output.append(elem)
    return output
```

