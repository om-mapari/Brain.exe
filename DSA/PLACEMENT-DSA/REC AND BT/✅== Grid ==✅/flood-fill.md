
![image1](../../../resources/f2919df689a64f68b2721a2aa0bd351f.png)

*\#include* \<iostream\>
using namespace std;
*\#include* \<bits/stdc++.h\>
void floodfill(vector\<vector\<char\>\> &maze, int row, int col, string psf, vector\<vector\<bool\>\> &visited)
{
  *if* (row\<0 or col\<0 or row \>= maze.size() or col \>= maze\[0\].size()
or maze\[row\]\[col\] == '1' or visited\[row\]\[col\] == true)
    *return*;
  *if* (row == maze.size() - 1 and col == maze\[0\].size() - 1) {
    cout \<\< psf \<\< endl;
    *return*;
  }
  visited\[row\]\[col\] = true;
  floodfill(maze, row - 1, col, psf + 'U', visited);
  floodfill(maze, row , col - 1, psf + 'L', visited);
  floodfill(maze, row + 1, col, psf + 'D', visited);
  floodfill(maze, row, col + 1, psf + 'R', visited);
  visited\[row\]\[col\] = false;
}
int main()
{
  int row = 6, col = 7;
  vector\<vector\<char\>\> maze(row, vector\<char\> (col, '\*'));

  vector\<pair\<int, int\>\> vp = {
    {0, 1},
    {1, 1}, {1, 3}, {1, 4}, {1, 5},
    {3, 0}, {3, 2}, {3, 3}, {3, 5}, {3, 6},
    {4, 0}, {4, 2}, {4, 3}, {4, 5}, {4, 6},
    {5, 0},
  };
  cout \<\< endl;
  *for* (auto i : vp) maze\[i.first\]\[i.second\] = '1';
  *for* (auto && i : maze)
  {
    *for* (auto && j : i)
    {
      cout \<\< j \<\< " ";
    }
    cout \<\< endl;
  }
  cout \<\< endl;
  string psf = "";
  vector\<vector\<bool\>\> visited(row, vector\<bool\> (col, false));
  floodfill(maze, 0, 0, psf, visited);
  *return* 0;
}

Ans =

\* 1 \* \* \* \* \*
\* 1 \* 1 1 1 \*
\* \* \* \* \* \* \*
1 \* 1 1 \* 1 1
1 \* 1 1 \* 1 1
1 \* \* \* \* \* \*

DDRDDDRRRRR
DDRRUURRRRDDLLDDDRR
DDRRRRDDDRR
---------------------- Reduce Space ---------------------------

*\#include* \<iostream\>
using namespace std;
*\#include* \<bits/stdc++.h\>
void floodfill(vector\<vector\<char\>\> &maze, int row, int col, string psf)
{
  *if* (row\<0 or col\<0 or row \>= maze.size() or col \>= maze\[0\].size() or maze\[row\]\[col\] == 'x' or maze\[row\]\[col\] == '1') *return*;
  *if* (row == maze.size() - 1 and col == maze\[0\].size() - 1) {
    cout \<\< psf \<\< endl;
    *return*;
  }
  maze\[row\]\[col\] = 'x'; // mark visited
  floodfill(maze, row - 1, col, psf + 'U');
  floodfill(maze, row , col - 1, psf + 'L');
  floodfill(maze, row + 1, col, psf + 'D');
  floodfill(maze, row, col + 1, psf + 'R');
  maze\[row\]\[col\] = '\*'; // unmark visited
}
int main()
{
  int row = 6, col = 7;
  vector\<vector\<char\>\> maze(row, vector\<char\> (col, '\*'));
  *for* (auto && i : maze)
  {
    *for* (auto && j : i)
    {
      cout \<\< j \<\< " ";
    }
    cout \<\< endl;
  }

  vector\<pair\<int, int\>\> vp = {
    {0, 1},
    {1, 1}, {1, 3}, {1, 4}, {1, 5},
    {3, 0}, {3, 2}, {3, 3}, {3, 5}, {3, 6},
    {4, 0}, {4, 2}, {4, 3}, {4, 5}, {4, 6},
    {5, 0},
  };
  cout \<\< endl;
  *for* (auto i : vp) maze\[i.first\]\[i.second\] = '1';
  *for* (auto && i : maze)
  {
    *for* (auto && j : i)
    {
      cout \<\< j \<\< " ";
    }
    cout \<\< endl;
  }
  cout \<\< endl;
  string psf = "";
  vector\<vector\<bool\>\> visited(row, vector\<bool\> (col, false));
  floodfill(maze, 0, 0, psf);
  *return* 0;
}

