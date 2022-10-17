# Double Pointers
#### We already know that a pointer points to a location in memory and thus used to store the address of variables. So, when we define a pointer to pointer. The first pointer is used to store the address of the variable. And the second pointer is used to store the address of the first pointer. That is why they are also known as double pointers.
First of all, I will use a simple example to demonstrate double pointers:

int x = 5; // Simply 5

int* y = &x; // y holds the address of x

int** z = &y; // z holds the address of y

When y holds the address of x it means that no matter what is the value of x, y still points to it (points means 'holding the address of'). So, changing x also changes *y which is the syntax for accessing the value that y points to. The same is applied to z, but here we need to use * operator twice in order to access x value, because z points to y which points to x (meaning **z == *y == x).

Let's draw out to understand more better:

int q = 15;

int * p = &q;

int * * z = &p;

 ```           q   
          +----+  
    p --> | 15 |  
    ^     +----+  
    |  
    z  
```
In the above drawing, q is an integer variable with the value 15.

The pointer p points to the variable q.

The pointer z points to the pointer p.

The expression *z refers to the value in the pointer p.

The expression **z or rewritten as *(*z) refers to the variable q.

We know that (*z) is the pointer p, so let's replace:

*(*z) == *(p);

We can replace *(p) with q, from the above definitions: *(*z) == *(p) == q;.

#### Use of Double Pointer 

Double pointer is normally used when allocating memory.

```
#include <stdlib.h>
void new_malloc(void **p, size_t s) {
    *p = malloc(s);
    /* do something */
}

int main() {
  int *p;
  new_malloc((void **)&p, sizeof(int) * 10);
}
```
[try youself](https://onecompiler.com/cpp)

