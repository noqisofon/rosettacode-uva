
```
for ( int total in (0..100).reverse() ) {
    match ( total ) {
        ( 0 ) -> {
            println( "No more bottles of beer on the wall, no more bottles of beer." );
            println( "Go to the store and by some more, 99 bottles of beer on the wall." );
        }
    
        ( 1 ) -> {
            println( "${total} bottle of beer on the wall, ${total} bottle of beer." );
            println( "Take one down and pass it around, no more bottles of beer on the wall." );
            println();
        }
        
        else {
            println( "${total} bottle of beer on the wall, ${total} bottle of beer." );
            println( "Take one down and pass it around, ${total - 1} bottles of beer on the wall." );
            println();
        }
    }
}
```

## `match` キーワード

`match` 式は C 言語や Java 言語においての `switch` 文と同じような役割を持っていますが、`match` 式の方が機能的には強力です。

```
void switchOnEnumTypes(Hoge|Fuga|Piyo that) {
    match ( that ) {
        ( is Hoge ) -> {
            print( "Hoge" );
        }
        
        ( is Fuga ) -> {
            print( "Fuga" );
        }
        
        ( is Piyo ) -> {
            print( "Piyo" );
        }
    }
}
```

Uva には複合型というものがありますが、`if-is` ガード句でガードするまでは複合型に含まれる型に共通するプロパティやメソッドしか使うことができません。  
しかし `match` 式を使えば、複合型に含まれるそれぞれの型について、処理を切り替えることができます。
