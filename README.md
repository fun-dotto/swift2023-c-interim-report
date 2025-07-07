# プロジェクト学習 グループ報告書 TeXサンプルファイル

## 概要

プロジェクト学習のグループ報告書用のTeXサンプルファイルである。

`main.tex` がメインファイル、その他の `.tex` ファイルは章ごとのファイルである。
章ごとのファイルへの分割はしなくても良い。
また、ファイルを削除したり追加したりしても良い。

## Overleafでの使い方

1. New Project > Upload Projectでzipファイルをアップロードする。
1. Menu > Settings > CompilerでLaTeXを選択する。

以上！

## ローカルでの使い方
1. TeXはあらかじめインストールされているものとする。
1. zipファイルを展開する。
1. 展開したディレクトリでターミナルを開く。
1. `latexmk main.tex`

以上！

## Docker+VS CodeでLaTeX環境構築

LaTeXをローカル環境に導入するのは手間が大きいが、Dockerを使えば比較的簡単に導入できる。
VS Codeを組み合わせれば比較的簡単にTeXを利用できるので、ローカル環境でTeXを使いたい人にはオススメする。

詳細な手順は[Qiitaに記事を書いた](https://qiita.com/pman0214/items/87f2ca587176146631a3)ので参照されたい。

Dockerは導入済みであるものとする。
まず、[このdockerイメージ](https://hub.docker.com/r/pman0214/alpine-texlive-ja-epspdf)をpullする。

```
docker pull pman0214/alpine-texlive-ja-epspdf
```

次に、[VS Code](https://code.visualstudio.com/)をインストールする。

そしてVS Codeを起動し、[LaTeX Workshopという拡張機能](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)を導入する。

VS Cocdeの `settings.json` に以下を追記する。

```
"latex-workshop.latex.recipe.default": "latexmk (latexmkrc)",
"latex-workshop.docker.enabled": true,
"latex-workshop.docker.image.latex": "pman0214/alpine-texlive-ja-epspdf",
"latex-workshop.latex.autoBuild.run": "onFileChange",
```

以上で環境構築は完了。

### コンパイル（タイプセット）方法

VS CodeでメインとなるTeXファイルを開き、`Cmd + Option + b` を押せばコンパイルされてPDFファイルが生成される。

## 参考文献を手動で編集するには

* bibtexを実行すると生成される`.bbl`ファイルを`ref.tex`などの名前に変更して`main.tex`の中で`\input`で読み込む。
* Overleafで`.bib`ファイルを取得するためにはPreviewの「Recompile」の横にあるLogs and output files > Other logs & filesとたどって`bbl`を選択する。
