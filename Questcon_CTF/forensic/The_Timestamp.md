<h1>The Timestamp (100 points)</h1>
<p>Scenario:<br>The Professor and his crew have pulled off their biggest heist yet, but the police are hot on their trail. During their digital forensics investigation, the authorities have stumbled upon a critical file, malware.exe, on a suspect's computer. The timestamps on the file could reveal key details about the heist timeline, but it seems that the crew has altered them to cover their tracks!<br>The investigators suspect that Berlin, the mastermind behind the digital side of the operation, used a tool called Timestomp to manipulate the timestamps and throw the authorities off their trail. But with the right tools, you, as a digital forensics expert, can uncover the truth.<br>The $MFT (Master File Table) has been exported from the system, and the police have analyzed it using the AnalyzeMFT tool. Now it’s up to you to figure out whether Berlin tampered with the file's timestamps and uncover the real modification time of the file.</p>
<blockquote><strong>Flag: </strong>QUESTCON{YYYY-MM-DD_HH:MM:SS}</blockquote>
<a href="../files/analyze_mft_output.txt">analyze_mft_output.txt</a><br>
<a href="../files/malware_mft.json">malware_mft.json</a>
<hr>


<h3>Flag: <code>QUESTCON{2023-01-17_09:30:45}</code></h3>
