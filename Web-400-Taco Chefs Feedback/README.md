# Taco Chef Feedback

```
This website seems to be constantly monitored. In fact, the web traffic logs indicate that this website is checked once every minute.

We have reliable intel that the protected portion of this website holds information about the vault. But it seems that only the admin can see the protected part of this page.

http://challenges.tacocon.party:8345
```

This one was pretty straightforward for me, it required a little XSS. 

I went to the form and saw that I couldn't access the comments because I was not ad administrator. So I wrote a little scritpt to steal cookies.

McAfee removes this file if I include the script here, so not including it.

When the "person" (e.g. bot) visits the comments and is redirected to my website, I record the following cookie:

```
admin_id=kCxpAJacgNoGZPEPsgcdAhaVCAXdQyLa6wHUyNPYLhDMYPuEr4inwLmRxsEPqXkK
```

Upon setting that cookie, I can view the contents of the comments section, which has the following:

```
Tacocon{XSS_is_a_great_way_to_steal_cookies!}
```
