<h1>Wild Wild West (50 points)</h1>
<p>Woah, our network has been lighting up like the fourth of a July on steroids, I tell you HWHAT. Now, given that we had a user call in complaining about weird stuff happening, I think it is about time you cowboy up and figure out what is happening in our here network.</p>
<p>Submit the flag as <code>flag{flag-text}</code>.</p>
<h3> Created by: <b>RP-01?</b></h3>
<hr>

```bash
tshark -r wildwildwest.pcapng -Y 'frame contains "flag"'
```
<img src="../imgs/www1.png">
<img src="../imgs/www2.png">
<h3>Flag: <code>flag{kerbrute_finding_users}</code></h3>
