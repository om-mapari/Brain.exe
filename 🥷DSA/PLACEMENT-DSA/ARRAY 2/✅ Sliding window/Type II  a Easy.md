
While reducing those are not our ans : read below example
While reducing those can be possible ans : [Link](onenote:#Type%20II%20%20level%202&section-id={0561D0A3-CBFE-49B1-A9DD-DE8B099423FA}&page-id={89A235C9-683A-4A97-BA88-E5B749C59FD0}&end&base-path=https://d.docs.live.net/488d82fe7a9fef0f/Documents/PLACEMENT-DSA/ARRAY%202.one)

=========================================================================
Basic template of such problems is basically 3 steps.

**Step1**: Have a counter or hash-map to count specific array input and keep on increasing the window toward right using outer loop.

**Step2**: Have a while loop inside to reduce the window side by sliding toward right. Movement will be based on constraints of problem. Go through few examples below

**Step3**: Store the current maximum window size or minimum window size or number of windows based on problem requirement.

map \| set \| cnt // To store window
int j = 0;
for(int i=0;i\<n;i++){
map insert // increment window from back

// let's make window valid

while(invalid) {

map reduce // decrement window from front

j--;

}

store ans // calculate ans
}

==========================================================================

<table>
<colgroup>
<col style="width: 51%" />
<col style="width: 48%" />
</colgroup>
<thead>
<tr class="header">
<th><p>![image1](../../../resources/344178b193944b34932d909d29430a46.png)</p>
<p></p></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/max-consecutive-ones/">485. Max Consecutive Ones</a></p>
<p></p>
<p><strong>Input:</strong> nums = [1,0,1,1,0,1]<br />
<strong>Output:</strong> 2</p>
<p></p>
<p>![image2](../../../resources/26fe41864d0f48478ad3947379cf1a11.png)</p>
<p></p>
<p></p></td>
<td><p><a href="https://leetcode.com/problems/number-of-substrings-with-only-1s/">1513.Number of Substrings With Only 1s</a></p>
<p><strong>Input:</strong> s = "0110111"<br />
<strong>Output:</strong> 9</p>
<p></p>
<p>![image3](../../../resources/f2e066465b1641ebbd021018e041dac9.png)</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><a href="https://leetcode.com/problems/max-consecutive-ones-iii/">1004. Max Consecutive Ones III</a></p>
<p></p>
<p>We can flip k 0 to 1 so find l(mac cons.. 1's)</p>
<p></p>
<p>![image4](../../../resources/f5d547a329e2458a82d8e846237c1380.png)</p>
<blockquote>
<p></p>
</blockquote>
<ol type="1">
<li><p>always aquire num</p></li>
<li><p>release untill become valid</p></li>
</ol>
<blockquote>
<p>: while(inValid) untill = valid</p>
</blockquote>
<ol start="3" type="1">
<li><p>cnt ans always</p></li>
</ol>
<blockquote>
<p></p>
</blockquote>
<p></p>
<p></p>
<p>// Think about it if min asked you have to add</p>
<p>// min in while loop and cnt while reducing window</p>
<p>// check level2</p>
<p></p></td>
<td><p>![image5](../../../resources/f1e34f047f8a4fbe99a888a4be001eee.png)</p>
<p></p></td>
</tr>
</tbody>
</table>

------------------------------------------------------------------------------------------
[1493. Longest Subarray of 1's After Deleting One Element](https://leetcode.com/problems/longest-subarray-of-1s-after-deleting-one-element/)

same but changes
We need : question
Must delete one element (therefore flag)
if no zero then delete one
& max(Len, i-j+1-cnt0) // cnt0 there needed

![image6](../../../resources/d5b637c764d142bfa9fa27da53fe6164.png)

[3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

![image7](../../../resources/bcbec9f40e32444fa4694901260c60bb.png)

![image8](../../../resources/8e8163619d194382bc425202c5ed9bf7.png)

[713. Subarray Product Less Than K](https://leetcode.com/problems/subarray-product-less-than-k/)

![image9](../../../resources/dde9d14c05094f94b9f0f1c177779906.png)

[1695. Maximum Erasure Value](https://leetcode.com/problems/maximum-erasure-value/)

![image10](../../../resources/aa6b634859fe4cdc91ded237f08dfb31.png)

[1438. Longest subArr with max - min \<= k](https://leetcode.com/problems/longest-continuous-subarray-with-absolute-diff-less-than-or-equal-to-limit/)

![image11](../../../resources/a1ed3c0403194a4684fce7ba15f66a60.png)

![image12](../../../resources/afaaa0567a38481096852a618326c6b9.png)

// just more optimised with deque
![image13](../../../resources/865480e695754a86bdfa49cf5bfa2d09.png)

![image14](../../../resources/47dcaa9f32924bf583e90e8c22ff9786.jpg)

