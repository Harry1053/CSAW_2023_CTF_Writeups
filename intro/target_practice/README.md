# target_practice
## Category: Intro
## Author: ElykDeer

## Description

Aim carefully... This pwnie can JUMP!

# Ressources

We are provided with an executable file and netcat credentials.

# Solution

1. If we run the script we get promted the following:

>Aim carefully.... 

No other instructions, or any additional information.

My first thought was to use Ghidra to look at a decompiled version of the script. The interesting part I found was this:

>void cat_flag(void)
>
>{
>  system("cat /flag.txt");
>  return;
>}

In this bit, a function "cat_flag" is being defined, with the simple instructions to read the flag file and output its conent, which we know is the flag.
The function is not being called in the code.
We can use a decompiler/ debugger to find the function address. I will use r2:

>$ r2 target_practice 
>[#########]> aaa
>[#########]> afl

Now we can look for the cat_flag function:

>0x00400717    1 19           sym.cat_flag

If we now enter the function address as our input into the server (by connecting to it using the netcat credentials), we get the flag.

# Flag

csawctf{y0ure_a_m4s7er4im3r}
