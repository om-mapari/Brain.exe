
vector\<pair\<string, string\>\> s_to_d = { *// triverlling*
    {"Chennai", "Banglore"},
    {"Bombay", "Delhi"},
    {"Goa", "Chennai"},
    {"Delhi", "Goa"}
};
Ans = Bombay -\> Delhi -\> Goa -\> Chennai -\> Banglore
==================================================================

*\#include* \<iostream\>
using namespace std;
*\#include* \<bits/stdc++.h\>
void solve(vector\<pair\<string, string\>\> &vp)
{
  unordered_map\<string, string\> forword;
  unordered_map\<string, bool\> isstartpoint;
  string start_point = "";
  *for* (auto &i : vp) forword\[i.first\] = i.second; *// making hashmap*
  *for* (auto &i : forword) {
    isstartpoint\[i.second\] = false; *// fix*
    *if* (!isstartpoint.count(i.first)) {
      isstartpoint\[i.first\] = true;
    }
  }
  *for* (auto i : isstartpoint) {
    *if* (i.second == true) start_point = i.first;
    cout \<\< i.first \<\< " " \<\< i.second \<\< endl;
  }
  cout \<\< "start_point =\> " \<\< start_point \<\< endl;
  string path = "";
  *while* (forword.count(start_point)) {
    path += (start_point + " -\> " );
    start_point = forword\[start_point\];
  }
  path += start_point;
  cout \<\< path \<\< endl;
}
int main()
{
  vector\<pair\<string, string\>\> s_to_d = { *// triverlling*
    {"Chennai", "Banglore"},
    {"Bombay", "Delhi"},
    {"Goa", "Chennai"},
    {"Delhi", "Goa"}
  };
  solve(s_to_d);
  *return* 0;
}

output :
Bombay 1
Delhi 0
Chennai 0
Banglore 0
Goa 0
start_point =\> Bombay
Bombay -\> Delhi -\> Goa -\> Chennai -\> Banglore

