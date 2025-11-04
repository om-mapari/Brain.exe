
![image1](../../resources/907ac388de9a46dc9a43e93a959da2cf.png)

Find How much extra element bigger list has
move head by that much node

![image2](../../resources/9053fe1425844beabcd7cdf2eb1fdd4c.png)

class Solution {

public:

ListNode \*getIntersectionNode(ListNode \*headA, ListNode \*headB) {

ListNode \*a = headA, \*b = headB;

while (a != b) {

a = !a ? headB : a-\>next;

b = !b ? headA : b-\>next;

}

return a;

}

};
