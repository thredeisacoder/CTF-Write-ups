<h1> Bucket List (300 points)</h1>
<p> You know what's a bucketlist? In simple terms, it's just a list of wishes people want to achieve before the leavee this world. I found it to be very limiting & ironic because how can you know when you'll leave the world behind? It's better to enjoy every moment and take on every opportunity you can. One of my whishes though is to pet a cat, do you mind checking this one out. So cute.</p>
<p>Challenge link: <a href="http://opening-account-acectf.s3.ap-south-1.amazonaws.com/fun/can_we_get_some_dogs/026.jpeg">Click here.</a></p>
<hr>
<p>The website leads us to an image of a cat.</p>
<p>I tried accessing the main page:<code>http://opening-account-acectf.s3.ap-south-1.amazonaws.com</code></p>
<p>It seems that I have accessed an Amazon S3 bucket at the address <code>https://opening-account-acectf.s3.ap-south-1.amazonaws.com/</code> and received an XML file listing the contents of that bucket.</p>
<p>After analyzing, I discovered two interesting text files at <code>cry-for-me/acectf/secret.txt</code> and <code>fun/aws-cli/hint.txt</code>.</p>
<p>Surely, I will access <code>cry-for-me/acectf/secret.txt</code>.</p>
<p>And I received a piece of code that has not been decoded yet.</p>

```bash
QUNFQ1RGezdoM180dzVfMTVfbTE1YzBuZjE2dXIzZH0=
```
<p>By decoding with base64, we will obtain the flag.</p>

<h3>Flag: <code>ACECTF{7h3_4w5_15_m15c0nf16ur3d}</code></h3>
