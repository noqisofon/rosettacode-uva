
## 連想配列

連想配列を使うには `uva.collections` の `HashMap` を `import` します。

```
import uva.collections { HashMap };
```

連想配列の要素、ペアは `<key> => <value>` のように記述します。

```
variable Map<string, string> map = HashMap { "key1" => "hoge" };
```

右オペランドの `HashMap { "key1" => "hoge" }` の部分はマップリテラルです。  
`new`する場合はこのようにします:

```
variable Map<string, string> emptyMap = new HashMap<string, string>();
```

## キーに対応する要素に設定

あるキー `"key2"` に `"piyo"` を設定するにはこのようにします:

```
map["key2"] = "piyo";
```
