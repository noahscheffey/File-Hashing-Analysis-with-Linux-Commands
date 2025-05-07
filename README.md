<h1>File Hashing Analysis with Linux Commands</h1>

<h2>Objective:</h2>

To rigorously verify file integrity by creating and evaluating SHA-256 hash values for two files using Linux commands, identify any discrepancies, and definitively determine whether the files are identical. This process demonstrates the practical application of cryptographic hashing for file comparison and highlights its importance in ensuring data integrity.

<h2>Procedure</h2>

**File Content Display:**

The contents of two files, file1.txt and file2.txt, were displayed using the cat command. This initial visual inspection suggested that the files were identical.


<img src="https://i.imgur.com/uzsJue6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   

**SHA-256 Hash Generation:**

The SHA-256sum command, a standard Linux utility, was employed to generate unique cryptographic hash values for each file. SHA-256 was chosen for its strong collision resistance, meaning it is highly improbable that two different files will produce the same hash.

The command was executed as follows:

sha256sum file1.txt

sha256sum file2.txt

<img src="https://i.imgur.com/sWUkV9B.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<h2>Hash Value Storage:</h2>

To facilitate comparison, the generated SHA-256 hash values were redirected to separate files: file1hash.txt and file2hash.txt. This was achieved using output redirection (>).

sha256sum file1.txt > file1hash.txt

sha256sum file2.txt > file2hash.txt

<h2>Hash Comparison and Difference Identification:</h2>

The cmp command, a byte-by-byte file comparison utility, was used to identify any differences between the stored hash values in file1hash.txt and file2hash.txt.

The cmp command outputted the first differing byte position, confirming that the SHA-256 hashes, and therefore the original files, were indeed different.

<img src="https://i.imgur.com/mN9vIzP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<h2>Findings:</h2>

The cmp command revealed a difference between the SHA-256 hashes of file1.txt and file2.txt, despite their seemingly identical content upon initial visual inspection. This demonstrates that even a minor modification to a file will result in a completely different hash value.

<h2>Conclusion</h2>

This analysis demonstrates the effectiveness of cryptographic hashing, specifically SHA-256, in verifying file integrity. The use of Linux commands (SHA-256sum, cmp) provided a robust and efficient method for comparing file contents. The results confirm that file1.txt and file2.txt are distinct files, despite their apparent similarity. This technique is crucial in various applications, including data integrity verification, file authenticity checks, and change detection.
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
