# Find-the-Good-String

Given a string consisting of both upper and lower case English letters, create a "good" string by removing adjacent characters that differ only in case, until no such adjacent characters exist. Print the resulting string.

def find_good_string(s):
    stack = []
    
    for char in s:
        if stack and stack[-1] == char.swapcase():
            stack.pop()
        else:
            stack.append(char)
    
    return ''.join(stack)

input_string = input().strip() 
result = find_good_string(input_string)
print(result)
