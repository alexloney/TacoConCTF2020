# Tacopocalypse

```
Have you discovered the message the agent was trying to leave us?

Face the Tacopocalypse
```

This one took a little bit of effort. So to start with we had the following:

```
011010000111010001110100011100000011101000101111001011110110001101101000011000010110110001101100011001010110111001100111011001010111001100101110011101000110000101100011011011110110001101101111011011100010111001110000011000010111001001110100011110010011101000110110001101110011100000111001
```

Simple enough, it is binary for the following ascii:

```
http://challenges.tacocon.party:6789
```

That website then contains a redacted document that you can view when viewing the source code, it also contains a potential secret file with the path

```
secret_files/5:10/1:4/4:23/1:131/3:85
```

Followed by some paragraphs of text. After a bit of testing and looking into it, I figured out that "x:y" means "paragraph x, letter y". This is counted after stripping HTML but without stripping spaces or punctuation. It ends up becoming

```
secret_files/s/a/l/s/a
```

So, going to http://challenges.tacocon.party:6789/secret_files/s/a/l/s/a I discovered a "bunker_locator.html" which is a JavaScript file that slowly types an image on the screen. I don't have time for that, to the source I go!

In the source, I see that it mentions a "/{location_name}.html" and it also mentions a "Location at : 13.507993, 144.804185". Alright, that looks like GPS coordinates. I then found a latitute longitude to address website (https://www.latlong.net/Show-Latitude-Longitude.html) and reverse searched the coordinates, which resulted in a place named Tacos Sinaloa.

Going back to the CTF website, I tried http://challenges.tacocon.party:6789/Tacos_Sinaloa.html and came up with the following:

```
Tacocon{Th3_Tacopocalypse_1s_H3r3}
```
