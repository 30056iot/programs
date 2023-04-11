# programs
def nextLargerElement(self,arr,n):
        #code here
        s=[]
        ans=[]
        for i in range(n-1,-1,-1):
            if len(s)==0:
                ans.append(-1)
            elif(len(s)>0 and s[-1]>arr[i]):
                ans.append(s[-1])
            elif(len(s)>0 and s[-1]<=arr[i]):
                while(len(s)>0 and s[-1]<=arr[i]):
                    s.pop()
                if len(s)==0:
                    ans.append(-1)
                else:
                    ans.append(s[-1])
            s.append(arr[i])
                    
        return ans[::-1]
        
    def nextSmallerElementToLeft(arr):
    n = len(arr)
    s = []
    v = [-1] * n

    for i in range(n):
        while s and s[-1] >= arr[i]:
            s.pop()
        if s:
            v[i] = s[-1]
        s.append(arr[i])

    return v

arr = [7, 8, 1, 4]
ans = nextSmallerElementToLeft(arr)
for a in ans:
    print(a, end=' ')
    
    
    def nextSmallerElementToRight(arr):
    n = len(arr)
    s = []
    v = [-1] * n

    for i in range(n - 1, -1, -1):
        while s and s[-1] >= arr[i]:
            s.pop()
        if s:
            v[i] = s[-1]
        s.append(arr[i])

    return v
    
    def nextGreaterElementToLeft(arr):
    n = len(arr)
    s = []
    v = [-1] * n

    for i in range(n - 1, -1, -1):
        while s and s[-1] <= arr[i]:
            s.pop()
        if s:
            v[i] = s[-1]
        s.append(arr[i])

    return v
    
    def isValidParentheses(s):
    stack = []
    for c in s:
        if c == '(' or c == '[' or c == '{':
            stack.append(c)
        elif c == ')' and stack and stack[-1] == '(':
            stack.pop()
        elif c == ']' and stack and stack[-1] == '[':
            stack.pop()
        elif c == '}' and stack and stack[-1] == '{':
            stack.pop()
        else:
            return False
    return not stack
    
