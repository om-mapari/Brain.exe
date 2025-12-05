
Keyword : subarray, sum

BF : Generate all subarray

OS : Prefix Sum

sum\[0,j\] = sum\[0,i\] + sum\[i+1,j\]

property\[0,j\] = property\[0,i\] + property\[i+1,j\]
& we have to find property\[i+1,j\]

======================================== Questions on This Concept ================================================================

<table>
<colgroup>
<col style="width: 53%" />
<col style="width: 46%" />
</colgroup>
<thead>
<tr class="header">
<th><ol type="1">
<li><p>Largest SubArray with sum = 0</p></li>
</ol>
<blockquote>
<p>Largest SubArray with sum = k</p>
<p>Smallest check how to do ?</p>
<p></p>
<p>![image1](../../resources/45ba6f1ab58743ab8f8a876f8ed18076.jpg)</p>
<p></p>
<p>Sum = 0</p>
<p>![image2](../../resources/e1a7b21476054df186c25f5c7bfab970.png)</p>
<p></p>
<p>Ans :</p>
<p>0 3 || -1 5 || 2 7 || 1 9 || 2 10 || maxLen 8</p>
<p></p>
<p>Sum = 2</p>
<p>![image3](../../resources/972c121e1dd64e90967f3c5d383ed07b.png)</p>
<p></p>
<p>Ans :</p>
<p>-1 0 || -1 3 || 0 4 || 4 6 || 2 8 || maxLen 6</p>
<p></p>
</blockquote></th>
<th><p><em>#include</em> &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p><em>#include</em> &lt;bits/stdc++.h&gt;</p>
<p>void sumEquals0(vector&lt;int&gt; &amp;A)</p>
<p>{</p>
<p>  int n = A.size(), sum = 0, maxLen = 0;</p>
<p>  unordered_map&lt;int, int&gt; um;</p>
<p>  um[0] = -1; <em>// {sum,index} default</em></p>
<p>  <em>for</em> (int i = 0; i &lt; n; i++)</p>
<p>  {</p>
<p>    sum += A[i];</p>
<p>    <em>if</em> (um.count(sum)) {</p>
<p>      cout &lt;&lt; um[sum] &lt;&lt; " " &lt;&lt; i &lt;&lt; " || ";</p>
<p>      maxLen = max(maxLen, i - um[sum]);</p>
<p>    } <em>else</em> {</p>
<p>      um.insert({sum, i});</p>
<p>    }</p>
<p>  }</p>
<p>  cout &lt;&lt; "maxLen " &lt;&lt; maxLen &lt;&lt; endl;</p>
<p>}</p>
<p>void sumEqualsK(vector&lt;int&gt; &amp;A, int k)</p>
<p>{</p>
<p>  int n = A.size(), sum = 0, maxLen = 0;</p>
<p>  unordered_map&lt;int, int&gt; um;</p>
<p>  um[0] = -1; <em>// {sum,index} default</em></p>
<p>  <em>for</em> (int i = 0; i &lt; n; i++)</p>
<p>  {</p>
<p>    sum += A[i];</p>
<p>    <em>if</em> (um.count(sum - k))</p>
<p>    {</p>
<p>      cout &lt;&lt; um[sum - k] &lt;&lt; " " &lt;&lt; i &lt;&lt; " || ";</p>
<p>      maxLen = max(maxLen, i - um[sum - k]);</p>
<p>    }</p>
<p>    <em>if</em> (!um.count(sum)) um[sum] = i;</p>
<p>  }</p>
<p>  cout &lt;&lt; "maxLen " &lt;&lt; maxLen &lt;&lt; endl;</p>
<p>}</p>
<p>int main()</p>
<p>{</p>
<p>  vector&lt;int&gt; A = {2, 8, -3, -5, 2, -4, 6, 1, 2, 1, -3};</p>
<p>  sumEquals0(A);</p>
<p>  sumEqualsK(A, 2);</p>
<p>  <em>return</em> 0;</p>
<p>}</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p>
<ol start="2" type="1">
<li><p>Count No SubArray Whose Sum = k</p></li>
</ol>
<p></p>
<p>There can be multiple (sum - k) therefore count track</p>
<p></p>
<p>![image4](../../resources/129dbcd78a294c639525ac7a5d18bd17.jpg)</p>
<p></p></td>
<td><p><em>#include</em> &lt;iostream&gt;</p>
<p>using namespace std;</p>
<p><em>#include</em> &lt;bits/stdc++.h&gt;</p>
<p>void CountsumEqualsK(vector&lt;int&gt; &amp;A, int k)</p>
<p>{</p>
<p>  int n = A.size(), sum = 0, cnt = 0;</p>
<p>  unordered_map&lt;int, int&gt; um;</p>
<p>  um[0] = 1; <em>// {sum,cnt} default</em></p>
<p>  <em>for</em> (int i = 0; i &lt; n; i++)</p>
<p>  {</p>
<p>    sum += A[i];</p>
<p>    <em>if</em> (um.count(sum - k))</p>
<p>    {</p>
<p>      cout &lt;&lt; i &lt;&lt; " " &lt;&lt; sum - k &lt;&lt; " " &lt;&lt; um[sum - k] &lt;&lt; endl;</p>
<p>      cnt += um[sum - k];</p>
<p>    }</p>
<p>    um[sum]++;</p>
<p>  }</p>
<p>  cout &lt;&lt; "cnt " &lt;&lt; cnt &lt;&lt; endl;</p>
<p>}</p>
<p>int main()</p>
<p>{</p>
<p>  vector&lt;int&gt; A = {3, 7, -5, 5, 3, 2};</p>
<p>  CountsumEqualsK(A, 5);</p>
<p>  <em>return</em> 0;</p>
<p>}</p></td>
</tr>
<tr class="even">
<td><p></p>
<ol start="3" type="1">
<li><p><a href="https://leetcode.com/problems/subarray-sums-divisible-by-k/">Count No. of subArray Divisible by k</a></p></li>
</ol>
<p></p>
<p>div = div*qu + rem</p>
<p>sum = k.m + r;</p>
<p>S1 = k.n + r;</p>
<p></p>
<p>S2 = sum - S1;</p>
<p>sum - S1 = k(m-n) + 0 ;</p>
<p>therefore S2 % k = 0;</p>
<table>
<colgroup>
<col style="width: 46%" />
<col style="width: 53%" />
</colgroup>
<thead>
<tr class="header">
<th><p>![image5](../../resources/7f1da0a32fec40ebb4cbd22f9e0ebb4b.png)</p>
<p></p></th>
<th>![image6](../../resources/e9a868f8b2a14fad8de15a5397d24403.png)</th>
</tr>
</thead>
<tbody>
</tbody>
</table>
<p></p>
<p>dont' forget um[0] = 1</p>
<p>for rem = 0 cnt = 1</p>
<p></p></td>
<td><p>![image7](../../resources/3bc87d7672d641f08fcc44d572456628.png)</p>
<p></p></td>
</tr>
<tr class="odd">
<td><ol start="4" type="1">
<li><p><a href="https://leetcode.com/problems/continuous-subarray-sum/">Largest SubArray with sum divisible by k</a></p></li>
</ol></td>
<td><p>class Solution {</p>
<p>public:</p>
<p>  bool checkSubarraySum(vector&lt;int&gt;&amp; nums, int k) {</p>
<p>    unordered_map&lt;int,int&gt; um;</p>
<p>    int sum = 0;</p>
<p>    um[0]=-1;</p>
<p>    <em>for</em>(int i=0;i&lt;nums.size();i++)</p>
<p>    {</p>
<p>      sum+=nums[i];</p>
<p>      int rem = (sum%k);</p>
<p>     </p>
<p>      <em>if</em>(rem&lt;0) rem+=k;</p>
<p>      <em>if</em>(um.count(rem))</p>
<p>        <em>if</em>(i-um[rem]&gt;1) <em>// imp</em></p>
<p>          <em>return</em> true;</p>
<p>      <em>else</em> um[rem]=i;</p>
<p>    }</p>
<p>    <em>return</em> false;</p>
<p>  }</p>
<p>};</p></td>
</tr>
<tr class="even">
<td><ol start="5" type="1">
<li><p><a href="https://leetcode.com/problems/contiguous-array/">Largest SubArray with Equal 0's and 1's</a></p></li>
</ol>
<blockquote>
<p></p>
<p>![image8](../../resources/cae92b64013b4f7ca3257db0b82fcda7.png)</p>
<p></p>
<p></p>
<p>i/p = 0 0 1 0 1 0 1 1 0 0 1 1 1</p>
<p></p>
</blockquote></td>
<td><p>class Solution {</p>
<p>public:</p>
<p>  int findMaxLength(vector&lt;int&gt;&amp; nums) {</p>
<p>    unordered_map&lt;int,int&gt; um;</p>
<p>    int sum = 0,maxLen=0;</p>
<p>    um[0]=-1;</p>
<p>    <em>for</em>(int i=0;i&lt;nums.size();i++)</p>
<p>    {</p>
<p>      sum+=(nums[i]==0? -1 : 1);</p>
<p>      <em>if</em>(um.count(sum))</p>
<p>        maxLen = max(maxLen,i-um[sum]);</p>
<p>      <em>else</em> um[sum]=i;</p>
<p>    }</p>
<p>    <em>return</em> maxLen;</p>
<p>  }</p>
<p>};</p></td>
</tr>
<tr class="odd">
<td><ol start="6" type="1">
<li><p><a href="https://practice.geeksforgeeks.org/problems/count-subarrays-with-equal-number-of-1s-and-0s-1587115620/1/">Count Subarrays with equal 1s and 0s</a></p></li>
</ol>
<blockquote>
<p></p>
<p>class Solution{</p>
<p> public:</p>
<p>  long long int countSubarrWithEqualZeroAndOne(int nums[], int n)</p>
<p>  {</p>
<p>    unordered_map&lt;int,int&gt; um;</p>
<p>    int sum = 0,cnt=0;</p>
<p>    um[0]=1;</p>
<p>    <em>for</em>(int i=0;i&lt;n;i++)</p>
<p>    {</p>
<p>      sum+=(nums[i]==0? -1 : 1);</p>
<p>      <em>if</em>(um.count(sum))</p>
<p>        cnt+=um[sum];</p>
<p>      um[sum]++;</p>
<p>    }</p>
<p>    <em>return</em> cnt;</p>
<p>  }</p>
<p>};</p>
<p></p>
<p>follow up : Largest subArray with Equal 0, 1 and 2</p>
</blockquote></td>
<td></td>
</tr>
<tr class="even">
<td><ol start="7" type="1">
<li><p><a href="https://practice.geeksforgeeks.org/problems/equal-0-1-and-23208/1/">Count SubArray with Equal 0, 1 and 2</a></p></li>
</ol>
<blockquote>
<p></p>
<p>![image9](../../resources/08b456577de64f1b82d3aee8e74d4699.png)</p>
<p></p>
</blockquote></td>
<td><p>// Prefix key</p>
<p></p>
<p>class Solution {</p>
<p> public:</p>
<p>  long long getSubstringWithEqual012(string str) {</p>
<p>    int z=0,o=0,t=0; <em>// 0's 1's 2's count</em></p>
<p>    int cnt = 0;</p>
<p>    unordered_map&lt;string,int&gt; um;</p>
<p>    string key = to_string(z-o)+"#"+to_string(o-t);</p>
<p>    um[key]=1;</p>
<p>    <em>for</em>(int i=0;i&lt;str.size();i++)</p>
<p>    {</p>
<p>      int ch = str[i];</p>
<p>      <em>if</em>(ch=='0') z++;</p>
<p>      <em>else if</em>(ch=='1') o++;</p>
<p>      <em>else</em> t++;</p>
<p>      key = to_string(z-o)+"#"+to_string(o-t);</p>
<p>      <em>if</em>(um.count(key))</p>
<p>        cnt+=um[key];</p>
<p>      um[key]++;</p>
<p>    }</p>
<p>    <em>return</em> cnt;</p>
<p>  }</p>
<p>};</p></td>
</tr>
</tbody>
</table>
