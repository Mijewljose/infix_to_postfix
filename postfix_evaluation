import math
import os
import random
import re
import sys

def doMath(op, opr1, opr2):
    if op == "^":
        return opr1 ** opr2
    elif op == "*":
        return opr1 * opr2
    elif op == "/":
        return opr1 / opr2
    elif op == "+":
        return opr1 + opr2
    elif op == "-":
        return opr1 - opr2

def postfixEval(expr):
    oprndstk = []
    tokenlist = expr.split()
    for token in tokenlist:
        if token in "+-*/^":
            oprnd2 = oprndstk.pop()
            oprnd1 = oprndstk.pop()
            result = doMath(token, oprnd1, oprnd2)
            oprndstk.append(result)
        elif token.isdigit():
            oprndstk.append(float(token))
        else:
            return -99999
    return oprndstk.pop()
            
if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    exp = input()

    x = postfixEval(exp)

    fptr.write(str(x) + '\n')

    fptr.close()
