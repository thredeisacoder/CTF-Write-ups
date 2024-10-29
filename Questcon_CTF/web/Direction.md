<h1>Direction (100 points)</h1>
<p>Something seems off with the plan displayed on this site. Can you uncover what's hidden behind the scenes and find the way out? The Professor always has a trick up his sleeve.</p>
<h3>Author: <b>TheProfessor </b></h3>
<a href="https://questcon-misdirect.chals.io">https://questcon-misdirect.chals.io</a>
<hr>
<p>I found a <code>robots.txt</code> file containing the <code>/start</code> endpoint.</p>
<img src="../imgs/misdirection1.png">
<p>Attempting to access it with the GET method was blocked, so I tried using the POST method instead.</p>
<img src="../imgs/misdirection2.png">
<p>After accessing, it continuously redirects through <code>/redirect0</code>, <code>/redirect1</code>, <code>/redirect2</code>, <code>/redirect3</code>, and finally stops at <code>/redirect4</code>.</p>
<img src="../imgs/misdirection3.png">
<img src="../imgs/misdirection4.png">
<img src="../imgs/misdirection5.png">
<img src="../imgs/misdirection6.png">
<img src="../imgs/misdirection7.png">
<p>Each redirection provides a part of the flag.</p>
<h3>Flag: <code>QUESTCON{mi3d1r3ct10n_15_4n_4r}</code></h3>
