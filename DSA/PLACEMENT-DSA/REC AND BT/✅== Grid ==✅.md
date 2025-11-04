AM

\- use vector to move in all 8 direction

vector\<int\> dx = {1,1,1,-1,-1,-1,0,0};
vector\<int\> dy = {1,0,-1,1,0,-1,1,-1};

for(int k=0;k\<8;k++){
  int x=i+dx\[k\],y=j+dy\[k\];
  if(isValid(x,y,row,col) && condi){
*    // do this*
  }
}
