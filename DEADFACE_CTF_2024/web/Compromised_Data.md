<h1>Compromised Data (300 points)</h1>
<p> Several victims provided credit card information to TrendyTrove. We believe DEADFACE kept this information on the web server somewhere. See if you can find the flag associated with this data.</p>
<p>Submit the flag as <code>flag{flag-text}</code>.</p>
<h3> Created by: <b>syyntax</b></h3>
<a href="https://trendytrove.deadface.io/">TrendyTrove</a>
<hr>
<p>This challenge is similar to the Yalonda challenge, but instead of accessing the <code>db-init</code> folder, I navigate to the <code>outputs</code> folder.</p>
<img src="../imgs/compromised_data2.png" >
<p>There, I find a suspicious <code>customers.csv</code> file, and just as I suspected, the flag was inside.</p>
<img src="../imgs/compromised_data1.png" >

<h3>Flag: <code>flag{C0MM4ND_1NJ3CT10N_3XP0S3D_D4T4}</code></h3>
