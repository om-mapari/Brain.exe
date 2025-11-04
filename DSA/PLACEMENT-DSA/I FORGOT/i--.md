AM

1.  i-- :

![image1](../../resources/64defebd48464b6f9f62d94d242e2544.png)

2.  Spilling mistake :

3.  finding min forget to update

int mn_cnt = INT_MAX, ele = -1;

for(auto i: um)

{

if(i.second\<mn_cnt){

ele = i.first;

mn_cnt = i.second;

}

}

4.  um.insert ( {a,b} );
