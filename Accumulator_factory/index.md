## Ceylon 風

アキュームレーターを生成する関数を定義します:

```
int|float accumulator
    (variable int|float n)
    (int|float i)
  => match ( i )
     is int   => n = n.succ( i )
     is float => n = i + swich ( prev = n )
                         is float => prev
                         is int   => prev.asFloat()
```

めっちゃわかりにくいですが、`type alias` とかできないんですかね？

さて、`accumulator` の引数は `n` と `i` の 2 つです。  
以下のように引数を 1 つだけ与えると、`x` にはカリー化されて引数が 1 つの関数が設定されます。

```
auto x = accumulator( 1 );
```

## C# 風

カリー化？なにそれ？って感じのとっても単純な `accumulator` です。

```
Func<int|float> accumulator(int|float n) {
    return i => n += i;
}
```

`Func<?>` はなんか `delegate` とかで定義すればいいかもだ。

## 使い方

どちらでもこんな感じに使います。

```
println( x( 5 ) );             // => 6
println( accumulator( 3 ) );   // => int|float -> int|float
println( x( 2.3 ) );           // => 8.3
```
