AM

Majority Element \| Leetcode
Moose Voting Algo

==freq (ele) \> n/2==

int maj ;

for(auto i: arr)
{
if(cnt == 0) maj = i;

if(i == maj) cnt++; // as maj ele \> n/2

else cnt--;
}

![image1](../../resources/0baac4dbe00940a4a086e81806079191.png)

