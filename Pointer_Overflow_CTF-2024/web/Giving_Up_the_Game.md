<h1> Web 100 - Giving Up the Game (100 points)</h1>
<p> I can't wait to reveal this one! I have spent the entire summer working up an awesome game called Space Adventure! It's a bullet storm arcade shooter with survival horror elements and looter shooter portions heavily inspired by classics like Qubort, Donkey King, and Street Flighter II. Except this game isn't like other games - the only way to win is to cheat! Good luck!</p>
<p>Challenge link: <a href="http://34.135.223.176:7845/">Click here.</a></p>
<hr>
<p>I proceeded to use Burp Suite to capture the packets.</p>
<img src="./imgs/GivingUptheGame1.png">
<p>During the process, I found a strange endpoint. Upon closer inspection, I noticed a segment of the data was base64 encoded.</p>
<img src="./imgs/GivingUptheGame2.png">
<p>Decoding the base64-encoded segment revealed the flag.</p>
<h3>Flag: <code>poctf{uwsp_1_7H1nk_7H3r3r0_1_4m}</code></h3>
