---
toc: True
comments: False
layout: post
title: Sports Quiz
description: None
type: hacks
courses: {'csse': {'week': 1}, 'csp': {'week': 2, 'categories': ['4.A']}, 'csa': {'week': 0}}
categories: ['C1.4']
---

```python
import getpass, sys

def question_with_response(prompt):
    print("Question: " + prompt)
    msg = input()
    return msg

questions = 3
correct = 0

print('Hello, ' + getpass.getuser() + " running " + sys.executable)
print("You will be asked " + str(questions) + " questions.")
question_with_response("Are you ready to take a test?")

rsp = question_with_response("Who won the Super Bowl last year?")
if rsp == "KC Chiefs":
    print(rsp + " is correct!")
    correct += 1
else:
    print(rsp + " is incorrect!")

rsp = question_with_response("Who Won the Last Ballon D'or?")
if rsp == "Lionel Messi":
    print(rsp + " is correct!")
    correct += 1
else:
    print(rsp + " is incorrect!")

rsp = question_with_response("Who Won the NBA MVP Award Last Year")
if rsp == "Joel Embiid":
    print(rsp + " is correct!")
    correct += 1
else:
    print(rsp + " is incorrect!")

print(getpass.getuser() + " you scored " + str(correct) +"/" + str(questions))
```

    Hello, rayanesouissi running /usr/local/opt/python@3.11/bin/python3.11
    You will be asked 3 questions.
    Question: Are you ready to take a test?
    Question: Who won the Super Bowl last year?
    KC Chiefs is correct!
    Question: Who Won the Last Ballon D'or?
    Lionel Messi is correct!
    Question: Who Won the NBA MVP Award Last Year
    Joel Embiid is correct!
    rayanesouissi you scored 3/3

