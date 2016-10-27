
範囲リテラルもシーケンスなので、シーケンスのメソッド(`map` とか `first`、`reduce` とか)が使えます。

```
shared int factorial(int n) {
    return ( 1..n ).reduce( (int accumulator, int factor) => accumulator * factor );
}
```
