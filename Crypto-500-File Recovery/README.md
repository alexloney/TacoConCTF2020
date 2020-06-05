# File Recovery

```
Help! We were discovered during our intrusion of the secret Taco bunker. As soon as they discovered us, they began to encrypt their highly sensitive files.

We were discovered on 5/16/20 sometime between 5:25pm and 5:30pm PST! We really need help recovering an important file.

We were able to recover one file because they had it on a backup server: important_image.jpg

But flag.jpg looks to be gone forever!

We were able to find this python script that looks like it was used as the encryption module. Hope this helps!
```

This one is pretty straightforward, it just requires a little coding in Python. so we know that the files were encrypted in a certain time window and by looking at the Python code, we can see that the encryption happens by generating a random AES key and seeing it with the time. Furthermore, we know the seed by looking at the file names.

So, all that must be done is generate each time within the time window we are given until we generate the correct seed. From there, we then generate the AES keys for the time slots right around that seed until the AES key works to decrypt the file we know. From there, we use the same AES key on the flag file.
