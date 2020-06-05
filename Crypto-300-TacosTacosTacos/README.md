# TacosTacosTacos

```
Our operative Dan seems to have lost a few marbles. After spending months deep undercover he has finally returned. However, all he does now is walk in circles repeating the phrase: "TacosTacosTacos"... quite strange...

He handed me a note with this message, but I can't read it?

U2FsdGVkX1/0bVXVglaanXcM8UJ0F6cqU8c29EWHb4U/Z5DLr9LAeY+N5RkrvfGJPPFe2wnGxd+6Brk=
Moderator Note: The digest used to encrypt this string is MD5.
```

This one ended up being MUCH more challenging than I had expected. I ended up unlocking both hints:

```
The decryption key is "TacosTacosTacos"
```

```
If you have the key and the ciphertext... all you need to know is what type of cipher was used.. how many ciphers does openssl support?
```

To solve it, I ended up writing a little Bash script to loop through all OpenSSL supported algorithms (trying many MANY different combinations of keys until I got the hint saying it was "TacosTacosTacos") and eventually found the -md command-line switch for OpenSSL. The command that finally worked to decrypt it is:

```
echo U2FsdGVkX1/0bVXVglaanXcM8UJ0F6cqU8c29EWHb4U/Z5DLr9LAeY+N5RkrvfGJPPFe2wnGxd+6Brk= | openssl enc -d -a -md md5 -camellia-256-cfb8 -k 'TacosTacosTacos'
```

Resulting in the following:

```
Tacocon{AES_aint_the_only_cipher_out_there}
```
