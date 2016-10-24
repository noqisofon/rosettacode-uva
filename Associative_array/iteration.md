# 連想配列のイテレート

連想配列も `Iteratable<?>` インターフェイスを実装しているため、for-in でイテレートすることが可能です。

```
variable Map<string, int> assocs = new HashMap<string, int>();
```

こんな風に追加します:

```
assocs.add( "one", 1 );
assocs["two"] = 2;
assocs.add( "three" -> 3 );
```

## 普通のイテレート

連想配列の要素はキーとバリューの 2 つのメンバーのペアとなっています。  
通常通り for-in すると `key` と `value` というプロパティを持つオブジェクトとしてイテレートすることができます。

```
for ( auto pair in assocs ) {
    println( "(${pair.key} . ${pair.value})" );
}
```

あるいはマッチ式？を使って例えば `key` と `value` という変数に分けてイテレートすることもできます。  
この時、変数の型を表す `auto` を付ける必要は無いということに注意してください。

```
for ( key -> value in assocs ) {
    println( "(${key} . ${value})" );
}
```

## キーだけのイテレート

連想配列は `Map<_Key, _Value>` インターフェースを実装しているので、`keys` プロパティを持っています。  
これは、キーのコレクションを返します。

```
for ( auto key in assocs.keys ) {
    println( "${key}" );
}
```

## バリューだけのイテレート

`Map<_Key, _Value>` インターフェースでは `values` というバリューのコレクションを返すプロパティを持っているため、
バリューだけイテレートすることができます。

```
for ( auto value in assocs.values ) {
    println( "${value}" );
}
```

