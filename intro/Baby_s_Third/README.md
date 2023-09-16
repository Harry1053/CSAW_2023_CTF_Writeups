# Baby's Third
## Category: Intro
## Author: ElykDeer

# Description

>Babies can't count, but they can do binaries?
>
>(Where did Baby Two go?[)]

# Ressources

We are being given a babysthird, and a readme.txt file.

# Solution:

I think this is not the intended solution as it seems to not be relevant to the description or the contents of the readme.txt file, but if we use the strings command on the file. If we filter for the flag, we end up getting it just by that.

>strings babythird | grep csawctf{.*}

Explanation: We use the strings command to get all the sequences of printable characters in the babythird file. Then we are pining that to grep, to look for any sequence that starts with csawctf{, ends with }, and has any characters in between (hence the .*).

# Flag

>csawctf{st1ng_th30ry_a1nt_so_h4rd}
