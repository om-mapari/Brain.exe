AM

<table>
<colgroup>
<col style="width: 73%" />
<col style="width: 26%" />
</colgroup>
<thead>
<tr class="header">
<th><a href="https://leetcode.com/problems/maximum-product-of-splitted-binary-tree/description/">1339. Maximum Product of Splitted Binary Tree</a></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Given the root of a binary tree, split the binary tree into two subtrees by removing one edge such that the product of the sums of the subtrees is maximized.</p>
<p></p>
<p>Return the maximum product of the sums of the two subtrees. Since the answer may be too large, return it modulo 109 + 7.</p>
<p></p>
<p>Note that you need to maximize the answer before taking the mod and not after taking it.</p>
<p></p>
<p>![image1](../../resources/afe92a9a1c64451786775133708da11a.png)</p>
<p>Input: root = [1,null,2,3,4,null,null,5,6]</p>
<p>Output: 90</p>
<p>Explanation: Remove the red edge and get 2 binary trees with sum 15 and 6.Their product is 90 (15*6)</p>
<p></p></td>
<td><p>class Solution {</p>
<p>public:</p>
<p>  long long prod = LLONG_MIN, totelSum ;</p>
<p>  int sum(TreeNode *root)</p>
<p>  {</p>
<p>    if(!root) return 0;</p>
<p>    return root-&gt;val = root-&gt;val + sum(root-&gt;left) + sum(root-&gt;right);</p>
<p>  }</p>
<p>  void tri(TreeNode* root)</p>
<p>  {</p>
<p>    if(!root) return;</p>
<p>    long long left_part = root-&gt;left ? root-&gt;left-&gt;val : 0, right_part = root-&gt;right ? root-&gt;right-&gt;val : 0;</p>
<p>    long long root_node = root-&gt;val - left_part - right_part;</p>
<p>    long long above_root = totelSum - root-&gt;val;</p>
<p>    // root goes with left part</p>
<p>    long long l = root_node + left_part + above_root;</p>
<p>    long long r = right_part;</p>
<p>    // root goes with right part</p>
<p>    long long ll = left_part;</p>
<p>    long long rr = root_node + right_part + above_root;</p>
<p>    prod = max(prod, max(l * r , ll * rr));</p>
<p>    tri(root-&gt;left);</p>
<p>    tri(root-&gt;right);</p>
<p>  }</p>
<p>  int maxProduct(TreeNode* root) {</p>
<p>    int s = sum(root);</p>
<p>    totelSum = root-&gt;val;</p>
<p>    tri(root);</p>
<p>    return prod% 1000000007;</p>
<p>  }</p>
<p>};</p>
<p></p></td>
</tr>
</tbody>
</table>

