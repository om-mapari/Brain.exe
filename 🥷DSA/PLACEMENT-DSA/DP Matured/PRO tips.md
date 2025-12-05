AM

1\. To find min path : *return* max INT_MAX so that the path should not get considered

2\. Most IMP =\> *for* tabulation
  I) always start i from end (n-1) and decrease it till (i == 0)
  II) In Recursive Code : never send -ve values 
  -\> just write *if* (condition) before calling recursion

3\. Define dp\[\]\[\] && memset(dp,-1,sizeof dp);
