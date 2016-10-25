# クロージャー

クロージャーはラムダ式とも呼ばれ、動的に関数を書けるとかそーいった感じの機能です。

## クロージャのインターフェイス

クロージャに限らず、全ての呼び出し可能なオブジェクトは以下の `Callable` インターフェースを実装しています:

```
shared interface Callable<out Return, in Arguments>
    given Arguments satisfies Anything... {}
```

### クロージャの型

以下の関数の型は `Callable<int, (int, int)>` です。

```
auto sum(int a, int b) => a + b;
```

なので、`sum` という関数を `plus` に束縛する時の型は以下のようになります:

```
Callable<int, (int, int)> plus = sum;
```

あるいはこう書くこともできます:

```
int(int, int) plus = sum;
```

## クロージャ((関数内関数かも？))の書き方

`main` 関数の中で `sum` という関数を定義してみます:

```
shared void main() {
    auto sum(int x, int y) => x * y;
    
    println( sum( 1, 6 ) );
}
```

ここで `sum` は `main` スコープの中でしか呼び出すことができません。  
また、`sum` はこのように書くこともできます:

```
shared void main() {
    auto sum(int x, int y) { 
        return x * y;
    }
    
    println( sum( 2, 7 ) );
}
```

このような書き方は、クロージャの中身が複数行に渡る場合に便利です。  
おそらく多くのクロージャがこの形で書かれることになるでしょう。
