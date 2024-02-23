---
title:                "新プロジェクトの開始"
date:                  2024-02-22T17:30:27.950806-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-02-22, dogweather, reviewed
  - 2024-02-22, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## 何を、なぜ？

Pythonで新しいプロジェクトを始めるということは、初めから構造を持たせて、メンテナンスがしやすいフレームワークを設定することについてです。プログラマーは、コードが読みやすく、デバッグしやすく、特にプロジェクトや作業しているチームが時間とともに成長するにつれて、共同作業がしやすいようにするためにこれを行います。

## どうやって：

### 仮想環境の作成
仮想環境は、Pythonプロジェクトが必要とするパッケージを使用するための実行可能ファイルがすべて含まれている自己完結型のディレクトリです。プロジェクト依存関係間の衝突を避けるために、各プロジェクトに対して仮想環境を作成することが望ましいです。標準Pythonライブラリの一部である`venv`モジュールを使用してください。

```shell
# 'myproject'をあなたのプロジェクトの名前に置き換えてください
python3 -m venv myproject-env
```

仮想環境をアクティブにするには：

Windowsの場合：
```shell
myproject-env\Scripts\activate.bat
```

UnixまたはMacOSの場合：
```shell
source myproject-env/bin/activate
```

サンプル出力（出力はOSによって若干異なる場合があります）：
```shell
(myproject-env) $
```

### パッケージのインストール
Pythonのパッケージインストーラーである`pip`を使用して、パッケージをインストール、アップグレード、および削除します。ここでは、HTTPリクエストを行うための人気のあるサードパーティライブラリ`requests`をインストールする方法を示します：

```shell
pip install requests
```

サンプル出力：
```shell
Collecting requests
  Downloading requests-2.25.1-py2.py3-none-any.whl (61 kB)
     |████████████████████████████████| 61 kB 1.3 MB/s
Installing collected packages: requests
Successfully installed requests-2.25.1
```

### プロジェクト構造の設定
典型的なPythonプロジェクトは、このような形になるかもしれません：

```
myproject/
│
├── myproject-env/    # 仮想環境
├── docs/             # ドキュメント
├── tests/            # ユニットおよび統合テスト
│   └── __init__.py
├── myproject/        # プロジェクトのソースコード 
│   ├── __init__.py
│   └── main.py
├── setup.py          # プロジェクト設定ファイル
└── README.md         # プロジェクト概要
```

### 最初のプログラムを作成する
`myproject`ディレクトリ内に`main.py`ファイルを作成します。ここにシンプルなプログラムの例を示します：

```python
# myproject/myproject/main.py
def greet(name):
    return f"Hello, {name}!"

if __name__ == "__main__":
    print(greet("World"))
```

プログラムを実行する：

```shell
python myproject/main.py
```

サンプル出力：
```shell
Hello, World!
```

### より大きなプロジェクトのためのフレームワークを使用する
特にウェブアプリケーションの場合、DjangoやFlaskのようなフレームワークは非常に貴重です。Flaskをインストールして、シンプルな「Hello, World」ウェブアプリケーションを作成する方法はこちらです：

```shell
pip install Flask
```

次の内容で`app.py`ファイルを作成します：

```python
# app.py
from flask import Flask
app = Flask(__name__)

@app.route("/")
def hello_world():
    return "<p>Hello, World!</p>"

if __name__ == "__main__":
    app.run(debug=True)
```

Flaskアプリケーションを実行する：

```shell
flask run
```

サンプル出力：
```shell
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

ウェブブラウザで`http://127.0.0.1:5000/`にアクセスすると、「Hello, World!」のメッセージが表示されます。
