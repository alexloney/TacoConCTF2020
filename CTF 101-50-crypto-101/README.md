# Crypto-101

```
We offer training to all our new T.A.C.O. recruits to ensure they have the skills necessary once they are out in the field.

The first lesson is cryptography. Cryptography is the art of creating codes and reading them. We've provided an encoded message below. Try to determine what encoding is used and what the plaintext message is.

VGFjb2NvbntUaGlzSXNUaGVGbGFnISF9Cg==
```

That looks like base64?

```
echo VGFjb2NvbntUaGlzSXNUaGVGbGFnISF9Cg== | base64 -d
Tacocon{ThisIsTheFlag!!}
```
