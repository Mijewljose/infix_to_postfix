import math
import os
import random
import re
import sys



def inOpPrecLower(p, q):
    prec = {'(': 0, '=': 1, '+': 2, '-': 2, '*': 3, '/': 3, '^': 4}
    a = prec[p]
    b = prec[q]
    if p=='^' and q=='^':
        return False
    elif a<=b:
        return True
    else:
        return False
    
def infixToPostfix(expr):
    oprstack = []
   
    postfix = ""
    for ele in expr:
        if ele.isalpha():
            postfix = postfix + ele
        elif ele =='(':
            oprstack.append(ele)
        elif ele ==')':
            while oprstack[-1] != '(':
                postfix = postfix + oprstack.pop()
            oprstack.pop()
        else:
            if ele not in {'=', '+', '-', '*', '/', '^'}:
                return "INVALID OPERATOR"
            while oprstack and inOpPrecLower(ele, oprstack[-1]):
                postfix = postfix + oprstack.pop()
            oprstack.append(ele)
    while oprstack:
        postfix = postfix + oprstack.pop()
    return postfix

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    exp = input()

    x = infixToPostfix(exp)

    fptr.write(x + '\n')

    fptr.close()
