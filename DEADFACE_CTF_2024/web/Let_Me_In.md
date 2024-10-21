<h1>Let Me In (15 points)</h1>
<p> DEADFACE is running an e-commerce site in an attempt to scam victims and steal their data and their money! See if you can find a way to access the site. Submit the flag found on the main page.</p>
<p>Submit the flag as <code>flag{flag-text}</code>.</p>
<h3> Created by: <b>syyntax</b></h3>
<a href="https://trendytrove.deadface.io/">TrendyTrove</a>
<hr>
<p>TThe challenge begins with a login page.</p>
<img src="../imgs/lmi1.png">
<p>This challenge involves SQL Injection, and I used <code>' OR 1=1--</code> (Fill in both the username and password fields.). I successfully gained admin access.</p>
<img src="../imgs/lmi2.png">
<h3>Flag: <code>flag{Tr3ndy_Tr0v3_$QL_1nj3ct10n}</code></h3>
