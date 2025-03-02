<h1> Buried Deep (100 points)</h1>
<p> "I’m not a hacker. I’m just someone who wants to make the world a little better. But the world isn’t going to change itself."<br>Submit your answer in the following format: ACECTF{3x4mpl3_fl4g}<br>The flag content should be in lowercase letters only.</p>
<p>Challenge link: <a href="http://34.131.133.224:9998/">Click here.</a></p>
<hr>

<p>Use dirsearch to enumerate directories on the server.</p>

```bash
dirsearch -u 34.131.133.224:9998
```
<p>We will identify two endpoints: <code>/robots.txt</code> and <code>/secret</code>.</p>
<p>This is the content of the <code>robots.txt</code> file.</p>

```bash
# Hey there, you're not a robot, yet I see you sniffing through this file 😡
# Now get off my lawn! 🚫

Disallow: /secret/
Disallow: /hidden/
Disallow: /cryptic/
Disallow: /forbidden/
Disallow: /pvt/
Disallow: /buried/
Disallow: /underground/
Disallow: /secret_path/
Disallow: /hidden_flag/
Disallow: /buried_flag/
Disallow: /encrypted/
```
<p>Try accessing each endpoint, and we will find two parts of the flag: part 1 in <code>/buried</code> and part 2 in <code>/secret_path</code>.</p>
<p>Part 1(undecoded):</p>

```bash
49 115 116 32 80 97 114 116 32 111 102 32 116 104 101 32 70 108 97 103 32 105 115 32 58 32 65 67 69 67 84 70 123 49 110 102 49 108 55 114 52 55 49 110 103 95 55 104 51 95 53 121 53 55 51 109 95 32
```
<p>Part 2(undecoded):</p>

```bash
..--- -. -..
.--. .- .-. -
--- ..-.
- .... .
..-. .-.. .- --.
.. ...
---...
.---- ..... ..--.- ...-- ....- ..... -.-- ..--.- .-- .... ...-- -. ..--.- -.-- ----- ..- ..--.- -.- -. ----- .-- ..--.- .-- .... ...-- .-. ...-- ..--.-
```
<p>After decoding, we will get the following:</p>
<p>Part 1(Decimal): <code>1st Part of the Flag is : ACECTF{1nf1l7r471ng_7h3_5y573m_</code></p>
<p>Part 2(Morse code): <code>2ND PART OF THE FLAG IS : 15_345Y_WH3N_Y0U_KN0W_WH3R3_</code></p>
<p>To find part 3, we need to view the source code, and I found it in <code>style.css.</code></p>

```bash
#flag {
    display: none;
    content: "bC5 !2CE @7 E96 u=28 :D i f9b0db4CbEd0cCb03FC`b5N"; 
}
```
<p>Part 3(undecoded):</p>

```bash
bC5 !2CE @7 E96 u=28 :D i f9b0db4CbEd0cCb03FC`b5N
```
<p>After decoding part 3(ROT47): <code>3rd Part of the Flag is : 7h3_53cr3t5_4r3_bur13d}</code></p>


<h3>Flag: <code>ACECTF{1nf1l7r471ng_7h3_5y573m_15_345y_wh3n_y0u_kn0w_wh3r3_7h3_53cr3t5_4r3_bur13d}</code></h3>
