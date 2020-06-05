# Intercepted Message

```
We intercepted this message between two taco Chefs. They are trying to hide their secret ingredient.

Can you read what they were saying?

Gnpbpba{PrnfnePvcurefNeragGurOrfgRapelcgvbaZrgubq}
```

This was pretty straightforward, I immediately thought that it may be a ROT13, so with a little command-line script of:

```
echo 'Gnpbpba{PrnfnePvcurefNeragGurOrfgRapelcgvbaZrgubq}' | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

I came up with the correct flag:

```
Tacocon{CeasarCiphersArentTheBestEncryptionMethod}
```
