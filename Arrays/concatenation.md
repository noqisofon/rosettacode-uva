# 配列を結合する

`Array#concat()` を使ってください。

```
auto hoge = [ 1, 2, 3 ];
auto piyo = [ 4, 5, 6 ];

auto fuga = hoge.concat( piyo );

println( fuga );
```

## 暗黙的に型指定する

`auto` は変数の型の替わりに使います。  
暗黙的に型指定されたローカル変数は型を宣言した場合と同様に厳密に型指定されますが、コンパイラが型を決定します。

以下の `foo` と `bar` は機能的に同じです:

```
int[] foo = [ 1, 2, 3 ];
auto  bar = [ 1, 2, 3 ];
```
