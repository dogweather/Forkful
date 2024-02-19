---
aliases:
- /ja/clojure/using-a-debugger/
date: 2024-01-26 03:48:29.507864-07:00
description: "\u30C7\u30D0\u30C3\u30AC\u3092\u4F7F\u7528\u3059\u308B\u3068\u3044\u3046\
  \u3053\u3068\u306F\u3001\u30B3\u30FC\u30C9\u3092\u7CBE\u67FB\u3059\u308B\u305F\u3081\
  \u306E\u62E1\u5927\u93E1\u3092\u81EA\u5206\u306B\u88C5\u5099\u3059\u308B\u3068\u3044\
  \u3046\u3053\u3068\u3067\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3053\
  \u308C\u3092\u884C\u3044\u3001\u30D0\u30B0\u3092\u6F70\u3057\u3001\u30D5\u30ED\u30FC\
  \u3092\u7406\u89E3\u3057\u3001\u30ED\u30B8\u30C3\u30AF\u304C\u671F\u5F85\u901A\u308A\
  \u306B\u5C55\u958B\u3055\u308C\u308B\u304B\u3092\u78BA\u304B\u3081\u307E\u3059\u3002"
lastmod: 2024-02-18 23:08:54.608108
model: gpt-4-0125-preview
summary: "\u30C7\u30D0\u30C3\u30AC\u3092\u4F7F\u7528\u3059\u308B\u3068\u3044\u3046\
  \u3053\u3068\u306F\u3001\u30B3\u30FC\u30C9\u3092\u7CBE\u67FB\u3059\u308B\u305F\u3081\
  \u306E\u62E1\u5927\u93E1\u3092\u81EA\u5206\u306B\u88C5\u5099\u3059\u308B\u3068\u3044\
  \u3046\u3053\u3068\u3067\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3053\
  \u308C\u3092\u884C\u3044\u3001\u30D0\u30B0\u3092\u6F70\u3057\u3001\u30D5\u30ED\u30FC\
  \u3092\u7406\u89E3\u3057\u3001\u30ED\u30B8\u30C3\u30AF\u304C\u671F\u5F85\u901A\u308A\
  \u306B\u5C55\u958B\u3055\u308C\u308B\u304B\u3092\u78BA\u304B\u3081\u307E\u3059\u3002"
title: "\u30C7\u30D0\u30C3\u30AC\u30FC\u306E\u4F7F\u3044\u65B9"
---

{{< edit_this_page >}}

## 何となぜ？
デバッガを使用するということは、コードを精査するための拡大鏡を自分に装備するということです。プログラマーはこれを行い、バグを潰し、フローを理解し、ロジックが期待通りに展開されるかを確かめます。

## 方法：
ClojureはJava Virtual Machine（JVM）に依存しているため、多くのデバッグはJavaツールで行われます。そのようなツールの一つが`CIDER`で、Emacs内でのClojure開発のためのパワーハウスパッケージであり、堅牢なデバッグ機能を持っています。さあ、潜りましょう：

```clojure
;; まず、Emacs内でCIDERを使用してClojureプロジェクトに接続します
M-x cider-jack-in

;; ブレークポイントを設定
;; 検査したいClojureコードの行に移動し、
;; "C-c M-b"を押すか、次を実行します：
M-x cider-debug-defun-at-point

;; コードが実行されると、ブレークポイントに到達します。CIDERは以下を求めます：
;; 1. n は実行の次の論理ステップに進むため、
;; 2. c は次のブレークポイントまで実行を続けるため、
;; 3. q はデバッグを終了するため。

;; ブレークポイントでローカル変数を検査
;; ブレークポイントにいる間、次のようにタイプします：
locals

;; minibufferにローカル変数とその値のリストが表示されます。
```
サンプル出力は次のようになるかもしれません：
```clojure
{:x 10, :y 20, :result 200}
```

## 深掘り
デバッガは、コンピューティング用語で言えば古き良き時代からあるツールです。「バグ」という用語は、実際の昆虫が機械の回路をショートさせてエラーを引き起こしたコンピューティングの初期の日々に遡ります。

`CIDER`はEmacs愛好者には素晴らしいですが、Clojureデバッグのための代替手段もあります。たとえば、IntelliJとCursiveプラグインを使用すると、よりGUI駆動のデバッグ体験を得ることができます。さらに、組み込みのLeiningenやtools.depsを使用してデバッグ時のプロセスフローを制御することができます。

内部では、これらのデバッガはしばしばバイトコードを操作し、専用のnREPLセッションで評価を行い、スタックトレースの検査を提供します。彼らはJVMの下層の機能を活用し、Javaのデバッグフレームワークの豊富なリソースにアクセスしています。

## 参照
- [CIDERデバッガドキュメント](https://docs.cider.mx/cider/debugging/debugger.html)
- [Cursiveデバッガ](https://cursive-ide.com/userguide/debugging.html)
- [自動化とデバッグのためのLeiningen](https://leiningen.org/)
- [より多くの制御のためのtools.deps.alpha](https://github.com/clojure/tools.deps.alpha)
