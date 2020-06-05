# vi

```
Last lesson! Often, you will only have a command line to work with files on a system. One popular tool to create & edit files is vi.

We've left you a welcome message on our server! Download the private key and go check it out!

ssh taco@challenges.tacocon.party -p 2222 -i tacocon.key
```

This was probably one of the more difficult of the 101 challenges, at least for me. You have to exploit the ability to execute external code from rvim. So connect to the server as described, then execute the following:

```
:py3 import os; system('shell');
```

Your connection is immediately terminated and you receive the following

```
Tacocon{Over_2_Million_People_Have_Gotten_Trapped_In_Vi}
```
