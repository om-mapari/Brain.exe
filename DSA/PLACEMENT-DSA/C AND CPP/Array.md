
IN a\[5\]
1.  value = a\[i\] or \*(a+i) both same
2.  address = &a\[i\] or (a+i) both same

![image1](../../resources/f810f9195ee44e54822b4860df8acc0d.png)

![image2](../../resources/a3b4925f14dd49078d2e3e8a3c92c7c4.png)

1.  Array as Fun Arguments

int fun(int a\[\]) // int \*a similar to a\[\]

2.  create dynamic array in c++

int main()

{

int size;

std::cin \>\> size;

int \*array = new int\[size\];

delete \[\] array;

return 0;

}
![image3](../../resources/48b415ffb1334a21a07654f0dd75fd2d.png)
