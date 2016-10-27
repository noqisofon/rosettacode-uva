# 括弧の対応をチェックするやつ

## クラスなどのインポート

テスト用のデータを生成するために `Random` クラスをインポートします。

```
import uva.random { Random };
```

## シングルトン・オブジェクトの宣言

ここでは括弧のペアとして角括弧を使います:

```
object bracketChars {
    shared variable char open  = ?[;
    shared variable char close = ?];
}
```

文字は `?` を前に付けます。

## テストデータの生成

```
shared string generate(Rabdom rnd, int count) {
    if ( count == 0 ) {
        return "";
    }
    
    int length = 2 * count;
    
    return string.join( string.empty, new string( bracketChars.open, count ) + new string( bracketChars.close, count ) )
        .orderBy( ch => rnd.next() );
}
```

## 括弧の対応のチェック

```
shared bool balanced(string text) {
    variable int level = 0;
    
    for ( auto ch in text ) {
        if ( ch == bracketChars.close ) {
            if ( level == 0 ) {
                
                return false;
            }
            
            -- level;
        }
        
        if ( ch == bracketChars.open ) {
            ++ level;
        }
    }
    
    return level == 0;
}
```


```
shared void main() {
    auto rnd = new Random();

    for ( auto count in 0..9 ) {
        auto text = generate( rnd, count );
        
        println( "\"${text}\" is ${balanced( text ) ? string.empty : "not "}" );
    }
}
```
