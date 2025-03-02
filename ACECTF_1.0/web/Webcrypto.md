<h1> Webrypto (200 points)</h1>
<p> I think we can all agree that most of us grew up watching the iconic cartoon Tom & Jerry. Every kid would feel that surge of adrenaline during the thrilling chases and chaotic conflicts between the mischievous mouse and the ever-determined cat. The excitement of those scenes—the heart-pounding moments of escape—sometimes felt almost real.<br>But then, I heard a little rumor: what if all those chases were fake? What if Tom and Jerry were actually friends all along? That revelation shook me. I had no one to ask about this mind-bending twist, so I decided to take matters into my own hands—I created a web app to settle this question once and for all.<br>I know the truth now. Do you think you can uncover it too?</p>
<p>Challenge link: <a href="https://chal.acectf.tech/Webrypto/">Click here.</a></p>
<hr>
<p>When accessing the website, a code appears.</p>

```bash
<?php
include('flag.php');
highlight_file(__FILE__);

// Check if parameters 'tom' and 'jerry' are not equal
if ($_GET['tom'] != $_GET['jerry']) {
    echo "<br>Parameter 1 Met!<br>";

        if (md5('ACECTF' . $_GET['tom']) == md5('ACECTF' . $_GET['jerry'])) {
        echo $FLAG;  // If the condition is true, print the flag
    }
}
?>
```
<p>We need to find two values, tom and jerry, such that:</p>

- <code>tom ≠ jerry</code> (they are different).
- <code>md5('ACECTF' . tom) == md5('ACECTF' . jerry</code> (the MD5 hash values are equal).

<p>In PHP, when comparing two values using the == operator (loose comparison), if the values are of different data types, PHP will attempt to typecast them. The md5() function returns a string, but if the input to md5() is not a string (for example, an array), the function cannot process it and will return NULL. In this case:</p>

- <code>md5('ACECTF' . $_GET['tom'])</code> will return NULL if <code>$_GET['tom']</code> is an array.
- <code>md5('ACECTF' . $_GET['jerry'])</code> will return NULL if <code>$_GET['jerry']</code> is an array.
- <code>NULL == NULL</code> is true in PHP when using the == operator.
<p>However, the condition <code>$_GET['tom'] != $_GET['jerry']</code> still needs to be satisfied, meaning that these two arrays must differ in content or structure.</p>
<p>Instead of passing a string for tom and jerry, we pass an array using the query string syntax as follows: <code>?tom[]=1&jerry[]=2</code> </p>
<p>Explain:</p>

- <code>$_GET['tom']</code> will be the array [1].
- <code>$_GET['jerry']</code> will be the array [2].
<p>In this case:</p> 

- <code>$_GET['tom'] != $_GET['jerry']</code> because [1] is different from [2] (different element values).
- <code>md5('ACECTF' . $_GET['tom'])</code> and <code>md5('ACECTF' . $_GET['jerry'])</code> will both result in an error because PHP cannot concatenate the string "ACECTF" with an array, causing md5() to return <code>NULL</code>.
- <code>NULL == NULL</code> is true.

<h3>Flag: <code>ACECTF{70m_4nd_j3rry_4r3_4ll135}</code></h3>
