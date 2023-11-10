# GitHub_Note
GitHub作業用のメモ


## 目次
- [git コマンド](#git-コマンド)
  - [clone](#clone)
    - [基本的な操作（git clone）](#基本的な操作gitclone)
    - [リポジトリのリンク取得方法](#リポジトリのリンク取得方法)
  - [log](#log)
    - [基本的な操作（git log）](#基本的な操作gitlog)
    - [出力フォーマットのオプション指定](#出力フォーマットのオプション指定)
    - [ログ出力のフィルタリング](#ログ出力のフィルタリング)
- [Linux コマンド](#Linux-コマンド)
  - [ディレクトリ操作](#ディレクトリ操作)
  - [ファイル検索](#ファイル検索)
  - [テキスト処理](#テキスト処理)
- [研究用ツール](#研究用ツール)
  - [JavaVariableExtractor](#JavaVariableExtractor)
    - [リンク（JavaVariableExtractor）](#リンクJavaVariableExtractor)
    - [基本的な使い方（JavaVariableExtractor）](#基本的な使い方JavaVariableExtractor) 
    - [ファイルへの書き出し方法](#ファイルへの書き出し方法)
  - [RefactoringMiner](#RefactoringMiner)
    - [リンク（RefactoringMiner）](#リンクRefactoringMiner)
    - [基本的な使い方（RefactoringMiner）](#基本的な使い方RefactoringMiner)
  - [git-stein](#git-stein)
    - [リンク（git-stein）](#リンクgit-stein)
    - [基本的な使い方（git-stein）](#基本的な使い方git-stein)
    - [メソッド抽出方法（git-stein）](#メソッド抽出方法git-stein)


## git コマンド
### clone
gitコマンドで`clone`を使用することで、リポジトリをローカルのディレクトリにクローンしてくることができる。

#### 基本的な操作（git clone）
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

### log
gitコマンドで`log`を使用することで、過去のコミット履歴を表示することができる。

#### 基本的な操作（git log）
コミット履歴を表示したいリポジトリに移動して実行する。

```
// コマンド
$ git log

// 例（リポジトリ：dubbo）
$ cd dubbo
/dubbo$ git log
```

オプションを指定しなかった場合、`git log`はコミットを新しい順に表示する。<br>
表示される内容は上から順に<br>
- コミットハッシュ：コミットを一意に識別するためのハッシュ値
- 著者：コミットを作成したユーザーの名前とメールアドレス
- コミット日時：コミットが行われた日時
- コミットメッセージ：コミットに関する説明やコメント

#### 出力フォーマットのオプション指定
コミット履歴について、出力したい情報をオプションにより指定する。
| コマンド | 説明 |
| :--- | :--- |
| -p | 各コミットのパッチ（コミット情報・変更内容）を表示する |
| --stat | 各コミットで変更されたファイルの統計情報（ファイル名・変更/追加/削除 の行）を表示する |
| --shortstat | --stat コマンドのうち、変更/追加/削除 の行だけを表示する |
| --name-only | コミット情報と変更されたファイルの一覧を表示する |
| --name-status | --name-only コマンドの出力に、変更(M)/追加(A)/削除(D) の情報を追加表示する |
| --pretty=oneline | 各コミットを1行で表示する |

#### ログ出力のフィルタリング
コミット履歴は、期間・編集者名・ファイル名・ディレクトリ名などでフィルタリングすることができる。
| コマンド | 説明 |
| :--- | :--- |
| -(n) | 直近のn件のコミットを表示 |
| --since="(期間)" | 指定した期間のコミットを表示 |
| --after="(日時)" | 指定した日時以降のコミットを表示 |
| --before="(日時)" | 指定した日時以前のコミットを表示 |
| --author="(名前)" | 編集者名から指定した名前にマッチするコミットを表示 |
| --grep="(文字列)" | 指定した文字列がコミットメッセージに含まれているコミットを表示 |
| -S"(文字列)" | 指定した文字列をコードに追加・削除したコミットを表示 |


## Linux コマンド
### ディレクトリ操作
| コマンド | 説明 |
| :--- | :--- |
| cd ~/ | ホームディレクトリに移動する |
| cd ../ | 1つ上の階層のファイルに移動する |
| cd ../../ | 2つ上の階層のファイルに移動する |

### ファイル検索
| コマンド | 説明 |
| :--- | :--- |
| find (ディレクトリ) | 指定ディレクトリ以下のファイルを列挙 |
| find -name "(文字列)" | 指定した文字列に一致するファイル・ディレクトリを検索 |

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
#### リンク（JavaVariableExtractor）
GitHubリンク：[https://github.com/amanhirohisa/JavaVariableExtractor](https://github.com/amanhirohisa/JavaVariableExtractor)

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
$ sudo java -jar JavaVariableExtractor.jar <java-file | java-file-directory> &> <保存先の指定・保存するファイル名・識別子>

// 例
$ sudo java -jar JavaVariableExtractor.jar dubbo &> ./output.txt
```

### RefactoringMiner
#### リンク（RefactoringMiner）
GitHubリンク：[https://github.com/tsantalis/RefactoringMiner](https://github.com/tsantalis/RefactoringMiner)

#### 基本的な使い方（RefactoringMiner）
1. ホームディレクトリからzipファイルを解凍した場所まで指定または移動して、`sudo`でコマンドを実行。<br>
2. コマンド「`-a <git-repo-folder> <branch> -json <path-to-json-file>`」を実行。

```
// 例
$ sudo ./RefactoringMiner/build/distributions/RefactoringMiner-2.3.2/bin/RefactoringMiner -a dubbo 3.2 -json ./test.json
```

### git-stein
#### リンク（git-stein）
GitHubリンク：[https://github.com/sh5i/git-stein](https://github.com/sh5i/git-stein)

#### 基本的な使い方（git-stein）
1. クローンしてからbuildする必要がある。

```
// プロジェクト「git-stein」をcloneする
$ git clone https://github.com/sh5i/git-stein.git
// プロジェクト「git-stein」に移動
$ cd git-stein
// 実行に必要なファイル作成
$ ./gradlew executableJar
// jarファイルを実行しやすい場所にコピーする
$ cp /path/to/git-stein/build/libs/git-stein.jar
```

2. 「git-stein」のコマンドは、*General Option*と*Subcommand*を指定して実行する。

```
java -jar git-stein.jar [General Option] <repo> [Subcommand]
```

#### メソッド抽出方法（git-stein）
- *General Option*で'-o'コマンドを使用して、変換後のリポジトリのパスを指定して生成する。
- '<path/to/target-repo>'は変換後のリポジトリのパス、'<path/to/source-repo>'は変換したい元リポジトリである。
- 注意点として、'<path/to/target-repo>'に指定する変換後のフォルダを事前に作成する必要はない。
- *Subcommand*で'@historage-jdt'を指定して、メソッド抽出のコマンド'--no-classes --no-fields'を使用する。

```
// コマンド
$ java -jar git-stein.jar -o <path/to/target-repo> <path/to/source-repo> @historage-jdt --no-classes --no-fields

// 例
$ java -jar git-stein.jar -o ./Java-Snake-Game_git-stein ./Java-Snake-Game @historage-jdt --no-classes --no-fields
```
