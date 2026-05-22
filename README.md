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

## 参考文献を手動で編集するには

* bibtexを実行すると生成される`.bbl`ファイルを`ref.tex`などの名前に変更して`main.tex`の中で`\input`で読み込む。
* Overleafで`.bib`ファイルを取得するためにはPreviewの「Recompile」の横にあるLogs and output files > Other logs & filesとたどって`bbl`を選択する。
