## 階乗をイテレートで計算する関数

階乗を for-in を使って計算する関数は以下のようになります:

```
shared int factorial(int n) {
    variable int accumulator = 1;
    
    for ( auto factor in 1..n ) {
        accumulator *= factor;
    }
    return accumulator;
}
```

このように呼び出せます:

```
println( factorial( 10 ) );
```
