# tacosay

```
There's one sound that no one knows - the sound of a taco. We've got a computer program that simulates a taco. I believe correctly answering the question of "what sound does a taco make?" will get us critical information for opening the vault.

Note: This binary only works on 32/64-bit Linux.
```

The difficulty with this one was that it is a Linux binary, so I had to set up a Linux VM to run it. Furthermore, it is a 32-bit binary, so i had to install special stuff to run it. Once that was done, I executed the binary and came up with a generic prompt asking "What does the taco say?"

After running strings on the binary, I found the following:

```
Ring-ding-ding-ding-dingeringeding!
```

Which isn't the answer, because if you run the following:

```
./tacosay Ring-ding-ding-ding-dingeringeding!
```

It will point you to a YouTube link for "What does the fox say?"

After a little investication I ran the following:

```
ltrace ./tacosay Ring-ding-ding-ding-dingeringeding!
```

Which gave the following

```
strcmp("m00o!", "Ring-ding-ding-ding-dingeringeding!")
strcmp("Ring-ding-ding-ding-dingeringeding!", "Ring-ding-ding-ding-dingeringeding!")
```

So, then I tried "m00o!":

```
./tacosay m00o!
```

And received:

```
Tacocon{R3verseEngineeringIsAllITacoAbout}
```
