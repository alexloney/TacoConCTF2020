# network-101

```
Lesson 6: When analyzing a remote system, you may find it to have some ports open. Some may be your common ports (80 for HTTP, 22 for SSH, 443 for HTTPS) while others may be non-recognizable for a custom service. In those cases, you need to find a way to interface with them.

Get the server to tell you what the flag is!

Host: challenges.tacocon.party
Port: 6543
```

I started by trying to connect to the server with

```
telnet challenges.tacocon.party 6543
```

And to see what happens next when...

```
Tacocon{HelloFromTheOtherSideOfTheInternet}
```
