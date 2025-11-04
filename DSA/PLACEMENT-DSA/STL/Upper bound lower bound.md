AM

4\. Binery Search

  lower_bound()

  upper_bound()

LOWER BOUND =\> *return* (*if* value present *return* iterator of that value

           *else return* iterator of just next grater value)

UPPER BOUND =\> ruturn (*if* value present *return* iterator of just grater value)

===========Vectors==========

4 5 5 7 8 25

LB OF 6 =\> 7

LB OF 5 =\> 5

LB OF 2 =\> 4

LB OF 26 not found

============================

UB OF 6 =\> 7

UB OF 5 =\> 7

UB OF 2 =\> 4

UB OF 26 not found

\> need sorted vector/array

Vector = \*(lower_bound(arr.begin(), arr.end(), 5))

Array = \*(lower_bound(arr, arr + n, 5))

Map = s.lower_bound(num); *//? apply on key only*

Set = m.lower_bound(num);

\> it return it of the element

4 5 5 7 8 25

auto it = upper_bound(v.begin(),v.end(),(5));

1.  Value of Element
if (it != v.end()) cout\<\< \*it; // 7

2.  Index of Element
if (it != v.end()) idx = (it - v.begin()); // 3
