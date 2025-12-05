
for humen = infix
( it's not easy to parse and evaluate infix exp )

so for computer scientist invented = postfix, prefix

| infix | postfix | prefix |
|-------|---------|--------|
| p-q   | pq-     | -pq    |

![image1](../../resources/9e90c5b56c4b4fd59ac6e6c11eeb51cf.png)

Evaluation of prefix and postfix

postfix = 2 3 \* 5 4 \* + 9 -

\| \| 1.pop
\| 3 \| 2.pop
\|\_2\_\| 3.evaluate
4.push

\| \|
\| \|
\|\_6\_\|

*\#include* \<iostream\>
using namespace std;
*\#include* \<bits/stdc++.h\>
int calc(char opr, int op1, int op2)
{
  *if* (opr == '+') *return* (op1 + op2);
  *else if* (opr == '-') *return* (op1 - op2);
  *else if* (opr == '\*') *return* (op1 \* op2);
  *else return* (op1 / op2);
}

void postfixEval(string postfix)
{
  stack\<int\> st;
  *for* (auto i : postfix)
  {
    *if* (isdigit(i)) st.push(i - '0');
    *else* {
      int op2 = st.top(); st.pop();
      int op1 = st.top(); st.pop();
*// cout \<\< op1 \<\< " " \<\< op2 \<\< " " \<\< calc(i, op1, op2) \<\< endl;*
      st.push(calc(i, op1, op2));
    }
  }
  cout \<\< st.top() \<\< endl;
}
void prefixEval(string prefix)
{
  reverse(prefix.begin(), prefix.end()); *// "945\*32\*+-"*
  stack\<int\> st;
  *for* (auto i : prefix)
  {
    *if* (isdigit(i)) st.push(i - '0');
    *else* {
      int op1 = st.top(); st.pop(); *// change op1*
      int op2 = st.top(); st.pop(); *// change op2*
*// cout \<\< op1 \<\< " " \<\< op2 \<\< " " \<\< calc(i, op1, op2) \<\< endl;*
      st.push(calc(i, op1, op2));
    }
  }
  cout \<\< st.top() \<\< endl;
}

int main()
{
  string postfix = "23\*54\*+9-";
  postfixEval(postfix);

  string prefix = "-+\*23\*549";
  prefixEval(prefix);
*  // 2 3 6*
*  // 5 4 20*
*  // 6 20 26*
*  // 26 9 17*
*  // ans = 17*

*  // 5 4 20*
*  // 2 3 6*
*  // 6 20 26*
*  // 26 9 17*
*  // ans = 17*

  *return* 0;
}

