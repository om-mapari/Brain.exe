AM
1.  Identical

bool isSameTree(TreeNode \*p,TreeNode \*q)

{

  if(!p and !q ) return true; *//left & right node is NULL*

  if(!p \|\| !q) return false; *//one of them is Not NULL*

  if(p-\>val != q-\>val) return false;

  return isSameTree(p-\>left,q-\>left) && isSameTree(p-\>right,q-\>right);

}

*// comparing left subtree's left child with right subtree's right child*

*// --AND-- comparing left subtree's right child with right subtree's left child*

![image1](../../resources/02e10126581345b4ac2daa121210d4d0.png)

![image2](../../resources/473c853d84b949a482f3177fc4734ce0.png)

![image3](../../resources/eec1165e23814b2e98d47a93d0f4f6b3.png)

bool checkMirror(btree \*a,btree \*b){
*  //if both the nodes*
  if(!a && !b)
    return true;

  if(!a \|\| !b \|\| a-\>data != b-\>data)
    return false;

  return checkMirror(a-\>left,b-\>right) && checkMirror(a-\>right,b-\>left);
}

![image4](../../resources/ca1b7132464f4bd3ab5d6656dbcb0467.png)

![image5](../../resources/d0e23ec25d60416482af7df4809a1ac4.png)
![image6](../../resources/d15a74dcce4d4e1aa540172cd7e0b747.png)
