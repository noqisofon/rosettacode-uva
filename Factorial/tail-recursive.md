
```
shared int factorial(int n) {
    return factorial( n, 1 );
}
```

```
shared int factorial(int n, int accumulator) {
    return n == 0
        ? accumulator
        : factorial( n - 1, n * accumulator );
}
```
