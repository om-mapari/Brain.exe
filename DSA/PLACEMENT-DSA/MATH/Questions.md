AM

1\. Extract numbers

  int n = 3567;

  *while* (n)
  {
    int rem = n % 10;
    cout \<\< rem \<\< " ";
    n = n / 10;
  }

2\. Reverse the number

  int n = 3567;
  int rev = 0;
  *while* (n)
  {
    int rem = n % 10;
    n = n / 10;
    rev = rev \* 10 + rem;
  }
  cout \<\< rev;

 
3\. Armstrong

  taking sum of cube of every digit in num then *if* (sum == num)

  int n = 371, sum = 0;
  *while* (n)
  {
    int rem = n % 10;
    sum += pow(rem, 3);
    n = n / 10;
  }
  cout \<\< sum \<\< endl;

 
4\. Print all factors / divisors

  int n = 36;
  *for* (int i = 1; i \<= 36; i++) * // O(n)*
  {
    *if* (n % i == 0) {
      cout \<\< i \<\< " ";
    }
  }
  cout \<\< endl;
  *for* (int i = 1; i \* i \<= 36; i++) *// O(n^0.5)*
  {
    *if* (n % i == 0)
    {
      cout \<\< i \<\< " ";
      *if* (n / i != i)
        cout \<\< n / i \<\< " ";
    }
  }
  1 2 3 4 6 9 12 18 36
  1 36 2 18 3 12 4 9 6

 
5\. Prime No. = No. that has exactly 2 factors 1 and itself

  1 is not prime number

  int n = 17;
  bool flag = true;
  *for* (int i = 2; i \< n; i++) *// 2 -\> n*
  {
    *if* (n % i == 0) *// if only one factor found then not prime*
    {
      flag = false;
      *break*;
    }
  }
  cout \<\< flag \<\< endl; *// ans = true*
*  // but we can check all factors even if we loop till n^0.5*
  *for* (int i = 2; i \* i \<= n; i++) 
  {
    *if* (n % i == 0)
    {
      flag = false;
      *break*;
    }
  }
  cout \<\< flag \<\< endl;

6\. GCD = largest common divisor
  \_\_gcd(9, 12) -\> 3
  \_\_gcd(9, 13) -\> 1
  \_\_gcd(20, 40) -\> 20

  int n1 = 9, n2 = 12;
  *for* (int i = min(n1, n2); i \>= 1; i--) *// O(n)*
  {
    *if* (n1 % i == 0 && n2 % i == 0) {
      cout \<\< i \<\< endl;
      *break*;
    }
  }
7\. Euclidean Algorithm = to quickly find GCD

  gcd(a,b) = gcd(a-b,b); *// a \> b // proof is hard*
  ex. gcd(20,15) = gcd(5,15) = gcd(5,10) = gcd(5,5) = gcd(0,5) =\> 5
  same as
  gcd(a,b) = gcd(a%b,b);
  ex. gcd(20,15) = gcd(5,15) = gcd(5,0) =\> 5
*  // final algorithm*
  gcd(a,b) = gcd(greater % smaller, smaller);

  int a = 9, b = 12;
  *while* (a \> 0 && b \> 0)
  {
    *if* (a \> b) a = a % b;
    *else* b = b % a;
  }
  *if* (a != 0) cout \<\< a;
  *else* cout \<\< b;
