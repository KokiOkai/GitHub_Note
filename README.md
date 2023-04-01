# GitHub_Note
GitHub作業用のメモ


## 目次
- [git コマンド](#git-コマンド)
  - [clone](#clone)
    - [基本的な操作](#基本的な操作)
    - [リポジトリのリンク取得方法](#リポジトリのリンク取得方法)
- [Linux コマンド](#Linux-コマンド)
  - [ディレクトリ操作](#ディレクトリ操作)
    - [cd](#cd)
  - [ファイル検索](#ファイル検索)
  - [テキスト処理](#テキスト処理)
- [研究用ツール](#研究用ツール)
  - [JavaVariableExtractor](#JavaVariableExtractor)
    - [基本的な使い方（JavaVariableExtractor）](#基本的な使い方JavaVariableExtractor) 
    - [ファイルへの書き出し方法](#ファイルへの書き出し方法)
  - [RefactoringMiner](#RefactoringMiner) 
    - [基本的な使い方（RefactoringMiner）](#基本的な使い方RefactoringMiner) 


## git コマンド
### clone
gitコマンドでcloneを使用することで、リポジトリをローカルのディレクトリにクローンしてくることができる。

#### 基本的な操作
```
// コマンド
$ git clone <git web URL>

// 例
$ git clone https://github.com/amanhirohisa/JavaVariableExtractor.git
```

#### リポジトリのリンク取得方法
1. clone対象となるリポジトリ画面から、「<> Code」を開く。<br>
2. 「HTTPS」のweb URLを取得。<br>
<img src="https://user-images.githubusercontent.com/105481222/228757235-0040642c-9975-4950-b0d6-ca1088985202.jpg" width="80%">


## Linux コマンド
### ディレクトリ操作
#### cd
| コマンド | 説明 |
| :--- | :--- |
| cd ~/ | ホームディレクトリに移動する |
| cd ../ | 1つ上の階層のファイルに移動する |
| cd ../../ | 2つ上の階層のファイルに移動する |

### ファイル検索
| コマンド | 説明 |
| :--- | :--- |
| find (ディレクトリ) | 指定ディレクトリ以下のファイルを列挙 |
| find -name "文字列" | 指定した文字列に一致するファイル・ディレクトリを検索 |

### テキスト処理
| コマンド | 説明 |
| :--- | :--- |
| less (ファイル) | ファイルの内容表示（スクロール操作できる） |
| head (ファイル) | ファイルの先頭10行を表示 |
| head (ファイル) -(行数) | ファイルの先頭指定行数を表示 |
| tail (ファイル) | ファイルの末尾10行を表示 |
| tail (ファイル) -(行数) | ファイルの末尾指定行数を表示 |


## 研究用ツール
### JavaVariableExtractor
#### 基本的な使い方（JavaVariableExtractor）
1. リポジトリに公開されているjavaファイルをまとめた「jarファイル」を、Visual Studio Codeにダウンロードする。<br>
2. コマンドを実行

```
// コマンド「-v」：コマンドラインに処理内容を表示する
$ sudo java -jar JavaVariableExtractor.jar -v <java-file | java-file-directory>

// 例
$ sudo java -jar JavaVariableExtractor.jar -v dubbo
```

#### ファイルへの書き出し方法
UNIXコマンドによって、標準出力をファイルに書き出す。

| コマンド | 使い方 | 説明 |
| :--- | :--- | :--- |
| > | (コマンド) > (ファイル) | コマンドの結果（標準出力）をファイルに書き出す |
| 2> | (コマンド) 2> (ファイル) | コマンドの結果（標準エラー出力）をファイルに書き出す |
| &> | (コマンド) &> (ファイル) | コマンドの結果（標準出力、標準エラー出力）をファイルに書き出す |

```
// コマンド
$ sudo java -jar JavaVariableExtractor.jar dubbo &> <保存先の指定・保存するファイル名・識別子>

// 例
$ sudo java -jar JavaVariableExtractor.jar dubbo &> ./output.txt
```

### RefactoringMiner
#### 基本的な使い方（RefactoringMiner）
1. ホームディレクトリからzipファイルを解凍した場所まで指定または移動して、sudoでコマンドを実行。<br>
2. コマンド「`-a <git-repo-folder> <branch> -json <path-to-json-file>`」を実行。

```
// 例
$ sudo ./RefactoringMiner/build/distributions/RefactoringMiner-2.3.2/bin/RefactoringMiner -a dubbo 3.2 -json ./test.json
```
