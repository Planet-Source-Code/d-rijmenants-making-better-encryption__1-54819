<div align="center">

## \[ Making better encryption \]


</div>

### Description

Want to make your own encryption algorithm? Taking your first steps into cryptology? Busy for a while but not too sure about it? Think your encryption is strong? Read this article first and get some good tips!
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[D\. Rijmenants](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/d-rijmenants.md)
**Level**          |Intermediate
**User Rating**    |4.7 (80 globes from 17 users)
**Compatibility**  |VB 3\.0, VB 4\.0 \(16\-bit\), VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Encryption](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/encryption__1-48.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/d-rijmenants-making-better-encryption__1-54819/archive/master.zip)





### Source Code

<html>
<p><br>
<font size="4"><strong><br>
</strong></font><font color="#0000FF" size="4"><strong>Guide for
better encryption.</strong></font></p>
<p>I notice that many people are fascinated by cryptology. It's
an exciting branch of coding, but many put their first steps into
it without any background. This results in huge mistakes in
writing and implementing their new 'unbreakable' algorithm.
Every cipher can be broken! the only question is: How long does
it takes?</p>
<p>Many programmers proclaiming they have good encryption, and
i'm sure they believe it. Unfortunately their ciphers are all
broken within very short time without any 'brute force attack' or
cryptanalysing, but with a bit of examining and maths by anyone
who sets his mind to it. This goes surprisingly also for many
commercial software! I hope by giving some simple basic tips,
they realize how easy it is to break weak ciphers and they will
make the code a bit securer, so that not every amateur can break
their cipher.</p>
<p><font color="#0000FF"><strong>Tip1: Don't thrust yourself</strong></font><br>
NEVER thrust your own encryption. Yes, you're smart and you don't
find a way to break it, but there are always others, smarter than
you (unless you're Stephen Hawkins), who will break it. Thats why
you allways need others to check your work. The best way to learn
writing ciphers, is by first learning how to break them. How can
you tell your encryption is safe, if you don't know how to break
(read cryptanalyse) it?</p>
<p><font color="#0000FF"><strong>Tip 2: The easy way?</strong></font><br>
Stream ciphers like RC4 are popular because they are easy to
implement. Watch out! Streams have some big weak spots. You can
only use the key once. If you use it twice, simple cryptanalyse
can compromise the key. This very important disadvantage goes for
all xor ciphers! If you really want to use xor based ciphers, you
should always follow tip 3 and tip 10. Don't get blinded by easy
ciphers. A good example is the very simple one-time-pad. Although
theoretically unbreakable, it is impossible to implement it in a
practical way, due to hughe problems it poses on management and
distribution of keys. Often good ciphers are useless because they
are implemented the wrong way. It is not because a cipher is
unbreakable in theory, that you can also implement it on a
unbreakable way.</p>
<p><font color="#0000FF"><strong>Tip 3: Easy to enhance</strong></font><br>
Finished your cipher? Take the next char to encrypt, and xor it
with the previous cipher output. On decrypting, just xor the
result with the previous decrypted char. This is called chaining.
That way, one decryption error is fatal to the rest of the
message and thus makes the cipher much stronger. You can chain
ciphers, output or input. This is a simple tip, easy to apply,
but has a great result!</p>
<p><font color="#0000FF"><strong>Tip 4: Don't make it easy to the
bad guys</strong></font><br>
Never use your key or password directly to manipulate bits and
bytes in your plain text, or use the bytes of your key one by
one, and start all over at the end. That way you link your key
directly to the cipher text and the door is wide open to crack
the cipher. It's like giving it away for free. About 90 percent
of all ciphers, found on PSC, are all kinds of variations on
poly-alphabetic rotation or substitution, and easy to break by
simple multiple frequency analysis!</p>
<p><font color="#0000FF"><strong>Tip 5: Make it hard to follow</strong></font><br>
Create a cipher where the plain input determins how the algorithm
works. A cipher that does the same work all the time is sensitive
to attacks. Simplified example: if the next plain text is an A,
the cipher will for instance xor it with a value, but if the next
plain is a B, it rotates the bits n times left, and is it a C
then rotate 2n times right. On xor ciphers, you could use a mask
byte, changed on certain conditions as just described, and xor it
with each cipher output. You could have the plain input
manipulate the key bits, or swap key bits or bytes, so that the
key changes all the time during encryption. How does the cipher
works? Who knows, it's changes all the time. </p>
<p><font color="#0000FF"><strong>Tip 6: The serious work</strong></font><br>
To create a block cipher the most common way to encrypt data is a
feistel network. When you use 64 bit blocks, divide the block in
two 32 bit parts where the right part together with the key are
the input of a function, and the output is xored with the left
part. Next the left part is encrypted with the right and so on.
Each step is called a round (DES uses 16 rounds). To decrypt, the
whole process is reversed form step 16 to 1. You can find plenty
of documentation on the structure of block ciphers on the net.</p>
<p><font color="#0000FF"><strong>Tip 7: The basics</strong></font><br>
A good function uses three important steps:<br>
1. Substitution: the replacing of groups of bits or words by
others.<br>
2. Fractionation: breaking up groups of bytes in smaller parts
before relocating.<br>
3. Transposition: swap words, bytes or bits from position with
each other.<br>
The combination of these three operations results in diffusion.
This diffusion is required for any good encryption scheme (see
Shannon). This can be applied in a whole text, or within blocks,
for instance combined with a feistel network. The way these steps
are executed must depend on a secret key.</p>
<p><font color="#0000FF"><strong>Tip 8: Help the users</strong></font><br>
Don't make it possible for the user to use weak keys. Write a
routine where you refuse key's as 'aaaa', 'mamama' or '123'. Even
good ciphers are useless if you use those, or 'top secret' or
'britney spears' as password. There are many idi*ts that use
those keys. Be nice and help them to use only good passwords.
Of course, they will always be that negligent to use the same key
more than once. So take care that the key isn't compromised by
this (see straightforward used streams and xor's). If a key is
compromised, and they use it also for other important stuff like
banking or account login, this could mean that your weak cipher
is responsible for their problems!</p>
<p><font color="#0000FF"><strong>Tip 9: Random and Random</strong></font><br>
Big mistake of many beginners: random isn't random when it comes
out of your computer. Computers are NEVER random, they are to
disciplined for that. If you do use a computers rnd function,
seed it first with randomly chosen values. Better to use your own
rnd-code. But it's very difficult to write a good one. Writing
good randoms, as for use in stream ciphers, is an art. You want
random? Get a bunch of xy values from the moving of your mouse,
and use these to initialize your own rnd code. that's random
(unless you have some tic). Never forget that there is a big
difference between randomness and crypto secure randomness, so
get well informed on the quality of Linear Shift Registers and
other pseudorandom generation schemes before getting into the
Random bussiness.</p>
<p><font color="#0000FF"><strong>Tip 10: Get a good start</strong></font><br>
Put a bunch of randomly chosen bits and bytes before your real
data and encrypt them along with them. This is very effective in
a cipher where the algorithm is used in a chaining or feedback
mode. That way, others cannot retrieve the key settings at the
beginning of the actual data, and every encryption, althoug with
the same key, is different. Those rnd bytes are simply disgarded
during decryption. Even better is that the number of rnd bytes is
also a random quantity, by this hiding the position of the actual
start of data, so encrypt your rnd header length also. This tip
is an absolute must on xor ciphers like RC4 if you really want to
use them.</p>
<p><font color="#0000FF"><strong>Tip 11: Stronger stuff</strong></font><br>
Compress your data BEFORE encryption, this will stenghten your
encryption greatly! Ofcourse, don't use a zip-file, but compress
it in your code. There are several good compressions in vb.
Compression will fraction the data already before any encryption
deals with it.</p>
<p><font color="#0000FF"><strong>Tip 12: The finish?</strong></font><br>
Think it's finished? Try to encrypt let's say 100.000 A's with a
repetitive key like 'ABC'. Next, take a good look at the
encrypted data and do some statistics on it. If there are any
repetitions or regular patterns, there's a smelly thing about
your algorithm. Back to the drawing board! ALWAYS be paranoia
about your own cipher, and NEVER thrust others so called
unbreakable ciphers before you have done a good analysing of
them. I know, it's easy to copy and use that encryption scheme
from mister X. Do you want to use and thrust code that does
unknown things? Finally, copy these tips and save them. Read them
all over when you finished writing your cipher. </p>
<p><font color="#0000FF"><strong>Tip 13: Top Secret?</strong></font><br>
A good algorithm should always be published. If you wrote some
encryption scheme, document it properly, with commonly used
notation, so that anyone can understand it. A secrecy system may
only depend on the secrecy of the key, NEVER on the secrecy of
the algorithm! Any crypto program can be reverse engineerd, so
secrecy is useless. A good hint on the quality of the encryption
is it's description. Watch out for snakeoil with great names like
chaos theoretics, triangulating arrays, cryptonic sublimation,
cosmic correlation, bla bla bla: Big crap! If they say it's a
secret algorithm, you can be absolutely sure that it's junk or
has backdoors.</p>
<p><font color="#0000FF"><strong>Tip 14: Think it's too hard?</strong></font><br>
Never give up, it's a great and exiting art. look around, read
crypto papers, check out FIPS's and RFC's on encryption on the
net, visit sites, learn from the big ones. Start by learning how
the classic ciphers like Vigenere, Auto-key, Bifid and Trifid,
ADFGVX, and many more work, and how they were broken. These are
the origins of modern cryptology and a good learning base. Good
luck !</p>
<p><font color="#0000FF"><strong>Tip 15: Some ideas</strong></font><br>
Check out submissions like 'Cipher Classics' or 'ULTRA file and
text encryption', an example that applies many of the tips...and
no, I won't say that ULTRA is unbreakable...but it's a strong one
;-)</p>
<p><font color="#0000FF"><strong>Tip 16: Some great links</strong></font><br>
Introduction to Codes, Ciphers and breaking them:<br>
<font color="#0000FF">http://www.vectorsite.net/ttcode.html<br>
</font>Basics on classic ciphers and how to break them:<br>
<font color="#0000FF">http://www.simonsingh.net/The_Black_Chamber/home.html</font><br>
Bruce Schneier's site, the crypto and security guru:<br>
<font color="#0000FF">http://www.schneier.com/</font><br>
Handbook of Applied Cryptography, pdf downloads<font
color="#0000FF"><br>
http://www.cacr.math.uwaterloo.ca/hac/</font><br>
A cryptographic compendium:<br>
<font color="#0000FF">http://fn2.freenet.edmonton.ab.ca/~jsavard/crypto/intro.htm</font><br>
Claude Shannon Theory Of Secrecy, the basics on crypto:<br>
<font color="#0000FF">http://www.cs.ucla.edu/~jkong/research/security/shannon1949.pdf</font><br>
A crypto dictionary:<br>
<font color="#0000FF">http://www.cryptnet.net/fdp/crypto/crypto-dict.html</font><br>
<br>
Never forget:<strong><br>
</strong><font color="#FF0000" size="4"><strong>A weak encryption
is more dangerous<br>
than being careful without encryption !!!</strong></font></p>
<p><font color="#0000FF"><strong>Happy codings from Dirk ;-)</strong></font></p>
<p>PS: and pleaaaase don't call your ciphers unbreakable any
more, even in best cases, call it strong... :-)</p>
</html>

