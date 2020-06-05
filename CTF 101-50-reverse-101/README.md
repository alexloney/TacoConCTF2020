# reverse-101

```
Lesson 5: Sometimes all we are given is the program and no source code. It is our job to reverse engineer the program in order to extract the information we need. Test out your reversing skills on the provided program.

All this program says is "I love tacos!". You'll need to dig deeper inside to find the flag.

Note: This binary will only run on 32/64-bit Linux, but you do not need to run it to get the flag.
```

Plop it into a hex editor, search for Taco and find...

```
Tacocon{YouFoundMe!!}
```

(Alternatively, strings would also work)
