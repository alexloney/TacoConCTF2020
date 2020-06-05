# Secret Recipe 1

```
T.A.C.O. found this website that is believed to hold valuable information. However, we have not been able to login due to a strong password being set by the user.

http://challenges.tacocon.party:8234
*Please no brute-forceing... this will not get you anywhere.
```

This one required a hint

```
There's many different types of SQL Injection
```

Well, that hint was a waste of points!

I ended up spending a LOT of time on this one and eventually solved it by playing around with the username/password. I made a user with the name "admin " and a password. Then logged in with that password and the username "admin" and it gave me the flag.

```
Tacocon{SprinkleALittleSQLInjectionOnTop19831}
```
