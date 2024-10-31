<h1>Theadmin (100 points)</h1>
<p>The Professor has left a vulnerable authentication system. Can you exploit it and gain admin not just using admin? Sometimes the simplest loopholes can lead to the biggest breakthroughs. Its simple but none of you could figure out.</p>
<h3>Author: <b>TheProfessor </b></h3>
<a href="https://questcon-theadmin.chals.io">https://questcon-theadmin.chals.io</a>
<hr>
<p>This challenge demonstrates how to interact with the API.</p>
<img src="../imgs/Theadmin0.png">
<p>First, we request a token for the admin username. The token is a JWT, so after obtaining it, I examine its contents using <a href="https://jwt.io">jwt.io</a>.</p>
<img src="../imgs/Theadmin4.png">
<p>This is my token: <code>eyJhbGciOiJhZG1pbiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImFkbWluIiwiaWF0IjoxNzMwMDM0NDgyfQ.ekhw1pem09SKzTbfNC8XYnto89HUthKaFFT2XNqztc0</code></p>
<img src="../imgs/Theadmin2.png">
<p>Although the username is admin, the token lacks a signature. However, this isn't an issue. I attempt to modify the token header by changing the algorithm from <code>HS256</code> to <code>none</code>.</p>
<img src="../imgs/Theadmin3.png">
<p>Here is my token then <code>eyJhbGciOiJub25lIiwidHlwIjoiSldUIn0.eyJ1c2VybmFtZSI6ImFkbWluIiwiaWF0IjoxNzMwMDM0NDgyfQ.ekhw1pem09SKzTbfNC8XYnto89HUthKaFFT2XNqztc0</code></p>
<img src="../imgs/Theadmin1.png">
<p>And you can guess what happened next.</p>

<h3>Flag: <code>QUESTCON{J3T_4lg0r1thm_15_vuln3r4bl3_70_n0n3}</code></h3>
