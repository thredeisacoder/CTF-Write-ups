<h1> SkyWave 4: Longest Run (120 points)</h1>
<p> We need to determine which device had the longest running connection out of the towers with the following coordinates:<div>&middot; (41.639642, -79.220682)<br> &middot; (40.598271, -78.801089)<br> &middot; (41.045892, -79.068358)<br> &middot; (41.257279, -77.529468)</div></p>
<p>Additionally, let’s focus on only finding the longest running connection with a dBm greater than -100.</p>
<p>Submit the flag as flag{device_imei}. Example: flag{123456789012345}.</p>
<blockquote><strong>Note:</strong> Access the database from <b>High Tower</b>.</blockquote>
<h3> Created by: <b>syyntax</b></h3>
<hr>

```query
SELECT * FROM Towers WHERE (latitude = 41.639642 AND longitude = -79.220682) OR (latitude = 40.598271 AND longitude = -78.801089) OR (latitude = 41.045892 AND longitude = -79.068358) OR (latitude = 41.257279 AND longitude = -77.529468);
```
```query
SELECT * FROM Connections WHERE signal_strength > -100 AND tower_id IN (105, 123, 187, 200) ORDER BY connection_duration DESC;
```
<h3>Flag: <code>flag{845303290931675}</code></h3>
