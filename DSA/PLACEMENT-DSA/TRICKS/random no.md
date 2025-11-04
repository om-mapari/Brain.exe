AM

int randomInt(int mn, int mx) {
  *return* mn + rand() % (mx - mn);
}

--------------------------------------------
to genrate random no
srand(time(0)); *// seed time*
then genrate random no
int n = rand(); *// will always diff*
