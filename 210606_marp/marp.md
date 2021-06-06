---
marp: true
paginate: true
theme: uncover
footer: ![w:36px](https://i.gyazo.com/7349baee99e4a7b315f9af14f2bea8ba.png)

style: |
    section.title {
        justify-content: center;
        text-align: center;
    }
    section {
        justify-content: start;
        text-align: left;
    }
    section footer {
        text-align: left;
    }
    section ul,
    section ol {
        margin: 15px 0 30px;
    }

    section.split {
        overflow: visible;
        display: grid;
    }
    section.split.col2 {
        grid-template-columns: 570px 570px;
        grid-template-rows: 120px 100px auto 100px auto;
    }
    section.split.col3 {
        grid-template-columns: 380px 380px 380px;
        grid-template-rows: 120px 100px auto;
    }

    section.split h2,
    section.split h3 {
        grid-row: 1 / 2;
    }
    section.split.col2 h2,
    section.split.col2 h3 {
        grid-column: 1 / 3;
    }
    section.split.col3 h2,
    section.split.col3 h3 {
        grid-column: 1 / 4;
    }

    section.split.col2 h4:nth-of-type(n+1):nth-of-type(-n+2),
    section.split.col3 h4:nth-of-type(n+1):nth-of-type(-n+3) {
        grid-row: 2 / 3;
    }
    section.split.col2 h4:nth-of-type(n+3):nth-of-type(-n+4) {
        grid-row: 4 / 5;
    }

    section.split h4:nth-of-type(1) + :not(h4) {
        grid-column: 1 / 2;
        grid-row: 3 / 4;
    }
    section.split h4:nth-of-type(2) + :not(h4) {
        grid-column: 2 / 3;
        grid-row: 3 / 4;
    }
    section.split.col3 h4:nth-of-type(3) + :not(h4) {
        grid-column: 3 / 4;
        grid-row: 3 / 4;
    }
    section.split.col2 h4:nth-of-type(3) + :not(h4) {
        grid-column: 1 / 2;
        grid-row: 5 / 6;
    }
    section.split.col2 h4:nth-of-type(4) + :not(h4) {
        grid-column: 2 / 3;
        grid-row: 5 / 6;
    }
---
<!-- _class: title -->

# テキストでスライドを作れるようになるまで

---

## Marp導入しました

- Markdown記法でスライドを生成できるやつ
- VSCodeで書ける
    - 拡張入れるとプレビューも出る
- HTMLで出力される
    - CSS等で改造できる
- PDFにも変換できる

---

### 前回のスライドはMarp製です

![h:450px](prev_slide.png)

---

## 実際に出力できるまでの道程

1. VSCode の拡張入れる
1. marp-cli 入れる　←　？？？
1. serve(node.js) 入れる　←　？？？
1. レイアウト調整

---

## 1. VSCodeの拡張入れる

左のメニューから`marp`で検索してインストールするだけ

![h:350px](vscode.png)

---

## 2. marp-cli入れる

コマンドで`$ npm install -g @marp-team/marp-cli`するだけなんだけどどうしてそんなことしてるかというと……

- MarpはHTMLを吐く
    - PDF出力はHTMLを変換するのでブラウザが要る
- VSCodeをWSL2上で動かしていたのでMarpもWSL2上
    - WSL2上にブラウザなんてない
    - **PDF出力できない！！**

---

### この工程は本当に必要だったのか……

そもそもVSCodeをWindows側から起動していればよかったのでは？

とにかく急いでいたので余裕がなかった

---

## 3. serve(node.js)入れる

コマンドで`$ serve`と打つだけでカレントディレクトリをホームとするサーバーが立ち上がる便利なやつ
なんでそんなものが必要になったかというと……

- セキュリティ的にブラウザがローカルのファイル参照するのは規制される
    - 出力したら画像が消えてしまった……
- 画像アップロードしてリンクし直すのは面倒だったので

---

### この工程は本当に必要だったのか……

そもそもPDF出力する必要性はあったのか？　tackmanさんのようにHTML形式でアップして公開すれば良かったのでは？

とにかく急いでいたので余裕がなかった

---

## 4. レイアウト調整

CSS を編集してやりたいようにした

4-1. 中央寄せと左寄せ
4-2. 縦割り

---

### 4-1. 中央寄せと左寄せ

- レイアウトの設定はページ全体に反映されてしまう
- ページ毎に`class`を設定できるのでそこを変えて対応
![h:350px](prev_slide2.png)


---

### 4-2. 縦割り

- Marp は **Markdown の"文章の構造化"という理念を守っている** :thumbsup:
  - 代償として**2次元配置の概念が無い**
- 最近の HTML にはグリッドレイアウトというものがあるのでそれを活用
  - グリッドレイアウトはパーツ毎にZ字の順で埋まっていくので工夫が必要
  - H4タグをタイトルとして特別扱いすることで解決

---

<!-- _class: title -->

### 完全勝利

![h:350px](prev_slide3.png)
(他にも3列割も出来る)

---

#### こんな感じ
![w:400px](prev_slide4-1.png) ![w:400px](prev_slide4-2.png)


---

<!-- _class: title -->

## 以上です
