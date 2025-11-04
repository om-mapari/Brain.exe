AM

Allocation = new keyword

Deallocation = delete keyword

1.  single varibale

![image1](../../resources/a7d912a034e84cd4aa34d7e3e7261679.png)

2.  contigious allocation

![image2](../../resources/882dc5e62ecc4e28942dc181d49c240f.png)

![image3](../../resources/d14a59e29d2741dfad1bd1d5e7351b0e.png)

==Memory Leak :==

In lang like jave garbage is atomatically cleard from heap

But in c/cpp we have to clear it by ourself

else we are wasting memory

==Dangling Pointer :==

A pointer pointing to a memory location that has been deleted (or freed)

int \*p = new int; // request memory

\*p = 5; // store value

delete p; // free up the memory

// now p is a dangling pointer

![image4](../../resources/6a9f81bb1f1c44edbb65e5bc9dd05d95.png)

![image5](../../resources/75f5f63fabc94cdda1e7f27b34e057f6.png)

![image6](../../resources/adb0e0346fb6440bbb3fe73022b9aeed.png)
