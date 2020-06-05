# SSH Keys

```
This website seems to require a private ssh key to login and see the secret message. We have reliable intel that the key has not been renewed since 2008.

Additionally, we were able to recover the corresponding public key. Is there any way to find the private key?

http://challenges.tacocon.party:8999
```

This one was pretty straightforward after a little bit of googling. I ended up locating a page on Github that I'm having trouble finding now, which directed me to https://github.com/g0tmi1k/debian-ssh that contains a list of common keys. I then grepped for the public key we were given through the common 1024 keys and found the corresponding private key.

After inserting the private key in the website referenced, it gave me the tag to enter in online.
