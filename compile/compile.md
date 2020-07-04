## watchコマンドを使って自動コンパイルを行う
```
tsc index.ts -w(--watch)
```
コンパイルエラーの場合はコンパイルされない

## 全てのファイルを一括コンパイルする
```
tsc --init
```
`tsconfig.json`が作成される
```
tsc
```
上記のコマンドを叩くだけで全てのファイルがコンパイルされる

### watxhと併用できる
```
tsc -w
```

## コンパイルしないファイルを設定する
`tsconfig.json`に以下を追加する
```
  "exclude": [
    "sample.ts",
    "*.spec.ts"
  ]
```
どのフォルダにあってもコンパイルさせたくない場合は
`**`をつける
```
  "exclude": [
    "**/sample.ts",
    "*.spec.ts"
  ]
```

よく使われるのは`node_modules`を省く

## 特定のファイルだけコンパイルさせたい場合
`tsconfig.json`に以下を追加する
```
 "include": [
     ファイル名
 ]
```

なお、`include`、 `exclude`の両方を定義した場合は`exclude`の方が強い

## ブラウザでTSを確認する方法
`tsconfig.json`の以下コメントアウトを外す
```
"sourceMap": true
```
sourceMapを使用することによって
ブラウザのデベロッパーツールでTSファイルが生成され
確認できる。