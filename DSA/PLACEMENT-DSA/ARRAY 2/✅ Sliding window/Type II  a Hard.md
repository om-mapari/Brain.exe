
[424. Longest Repeating Character Replacement](https://leetcode.com/problems/longest-repeating-character-replacement/)

<table>
<colgroup>
<col style="width: 39%" />
<col style="width: 60%" />
</colgroup>
<thead>
<tr class="header">
<th><p><a href="https://leetcode.com/problems/maximize-the-confusion-of-an-exam/">2024. Maximize the Confusion of an Exam</a></p>
<p></p>
<p></p>
<p>concept used;</p>
<p>No of replacement to make SubArr equal:</p>
<p>SubarrSize - freq of char occer max time</p>
<p></p>
<p>![image1](../../../resources/6ea7e37aefce45778e410992c10a246c.png)</p>
<p></p>
<p></p></th>
<th><p>![image2](../../../resources/74f806cdb5eb42028c7058abcc81e2f2.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>concept used;</p>
<p>No of replacement to make SubArr equal:</p>
<p>SubarrSize - freq of char occer max time</p>
<p></p>
<p>ex. "AABABBA" k=2 //1 replacement possible</p>
<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 79%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>replacemnt to make array equal</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>A</td>
<td>rep = 0</td>
</tr>
<tr class="even">
<td>AA</td>
<td>rep = 0</td>
</tr>
<tr class="odd">
<td>AAB</td>
<td>rep = 3-2 = 1</td>
</tr>
<tr class="even">
<td>AABA</td>
<td>rep = 4-3 = 1</td>
</tr>
<tr class="odd">
<td>AABAB</td>
<td><p>rep = 5-3 = 2 invalid -&gt; ABAB</p>
<p>rep = 4-2 = 2 invalid -&gt; BAB</p>
<p>rep = 3-2 = 1 valid</p></td>
</tr>
<tr class="even">
<td>-BABBA</td>
<td>rep = 5-3 = 2 invalid --&gt; BBA</td>
</tr>
</tbody>
</table>
<p></p>
<p>![image3](../../../resources/0e07b8cd31404776aa3d073d20744ba9.png)</p>
<p></p></td>
<td><p></p>
<p>![image4](../../../resources/e63852929439471495939753e251452b.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/frequency-of-the-most-frequent-element/">1838. Frequency of the Most Frequent Element</a></p>
<p></p>
<p>![image5](../../../resources/5b859ec50e2f42f2975c366fb05082c0.png)</p>
<p></p></td>
<td><p></p>
<p>Sort is imp</p>
<p></p>
<p>![image6](../../../resources/5cf4d79a77cc456cbe5ab4a7a4436711.png)</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/get-equal-substrings-within-budget/">1208. Get Equal Substrings Within Budget</a></p>
<p></p>
<p>![image7](../../../resources/f97eb696a22143788cca6839d7df27d6.png)</p>
<p></p></td>
<td><p></p>
<p>![image8](../../../resources/35a9c2feb0644aa6b6911e8bee33a1f7.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/fruit-into-baskets/">904. Fruit Into Baskets</a></p>
<p></p>
<p>![image9](../../../resources/210738ecc7524dce8b31c69df635fc04.png)</p>
<p>![image10](../../../resources/5dfd84cc94004c32b941abf2a92be4ac.png)</p>
<p></p></td>
<td><p></p>
<p><strong>Word Problem</strong></p>
<p></p>
<p>Questino seems defficult but conversion of it into simpler one is this</p>
<p></p>
<p>What is the length of longest subarray that contains up to two distinct integers?</p>
<p></p>
<p>![image11](../../../resources/c4a7372a37c548ed958f39d586d96d83.png)</p>
<p></p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Sliding Window + "At Most to Equal" trick To Find Exactly contain Element count</strong></p>
<p></p>
<p>It's because "number of windows with exactly k something in it" = "number of windows with at most k something in it" - "number of windows with at most k - 1 something in it".</p>
<p></p>
<p>Base Problem <a href="onenote:#Type%20II%20%20a%20string&amp;section-id={0561D0A3-CBFE-49B1-A9DD-DE8B099423FA}&amp;page-id={A4CC7B82-FC48-4B7E-8C49-64D8302D083A}&amp;object-id={98A5B1E9-5A4F-4936-B7AF-CA99E0637487}&amp;86&amp;base-path=https://d.docs.live.net/488d82fe7a9fef0f/Documents/PLACEMENT-DSA/ARRAY%202.one">Link</a></p>
<p></p></td>
<td><p>The following problems are also solvable using the shrinkable template with the "At Most to Equal" trick</p>
<p></p>
<p>930. Binary Subarrays With Sum (Medium)</p>
<p>992. Subarrays with K Different Integers</p>
<p>1248. Count Number of Nice Subarrays (Medium)</p>
<p>2062. Count Vowel Substrings of a String (Easy)</p></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/subarrays-with-k-different-integers/submissions/">992. Subarrays with K Different Integers</a></p>
<p></p>
<p>![image12](../../../resources/b8c558b941d54aa08c827d8b0e2a0432.png)</p>
<p></p></td>
<td><p>![image13](../../../resources/7428239d89014d708cfc36663e40c5d8.png)</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/binary-subarrays-with-sum/">930. Binary Subarrays With Sum</a></p>
<p></p>
<p>Can be solved in both way</p>
<ol type="1">
<li><p>atmostSum(k) - atmostSum(k-1) = Exactly sum k</p></li>
</ol>
<blockquote>
<p>O(1) space</p>
</blockquote>
<ol start="2" type="1">
<li><p>Prefix Sum = O(n) space</p></li>
</ol>
<p></p>
<p>![image14](../../../resources/19b94faa0fc94d868bc7cff953a783c6.png)</p>
<p></p></td>
<td><p>![image15](../../../resources/52a92e882e374e3d9f8ecc02d2bca8ef.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><a href="https://leetcode.com/problems/count-number-of-nice-subarrays/submissions/">1248. Count Number of Nice Subarrays</a></p>
<p></p>
<p><a href="onenote:#no%20releation&amp;section-id={0561D0A3-CBFE-49B1-A9DD-DE8B099423FA}&amp;page-id={A98248C7-3EFA-49A4-866C-9C727DE2B224}&amp;object-id={730F1010-044C-4F7B-AD93-BD6AC4C5C097}&amp;40&amp;base-path=https://d.docs.live.net/488d82fe7a9fef0f/Documents/PLACEMENT-DSA/ARRAY%202.one">PrefixSum Soluation</a> = With Extra Space O(n)</p>
<p></p>
<p>![image16](../../../resources/494c7f533a114d43a869e0a68fa5d7c4.png)</p></td>
<td>![image17](../../../resources/e4eebdd0cef64895a2472f8d4a43bb43.png)</td>
</tr>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/count-vowel-substrings-of-a-string/">2062. Count Vowel Substrings of a String</a></p>
<p></p>
<p>Count No. of substring Must contain all Vowels</p>
<p></p>
<p>![image18](../../../resources/01b2e5d7027d40ea910f43fcf0ead611.png)</p>
<p></p></td>
<td>![image19](../../../resources/b1691c503ee54c2b95f65d7c61e88c1a.png)</td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>

