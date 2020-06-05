# Admin Sauce packets

```
We captured some network traffic from the bunker computers. We believe we got the password of an admin.

Can you find the admin's password in this pcap?
```

The referenced file (which I haven't included) is simply a large pcap file. I opened it in WireShark and skimmed until I found unencrypted web traffic and found the key in there. It was probably just dumb luck that I found it, but I found the following:

```
Authorization: Basic YWRtaW46VGFjb0NvbntUaGlzSXNBU3BpY3lQYXNzd29yZH0=\r\n
```

Which is the following:
```
TacoCon{ThisIsASpicyPassword}
```
