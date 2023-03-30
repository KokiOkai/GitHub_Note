# GitHub_Note
GitHub作業用のメモ


## 目次
- [git コマンド](#git-コマンド)
  - [clone](#clone)
    - [基本的な操作](#基本的な操作)
    - [リポジトリのリンク取得方法](#リポジトリのリンク取得方法)
- [研究用ツール](#研究用ツール)
  - [JavaVariableExtractor](#JavaVariableExtractor)
    - [基本的な使い方](#基本的な使い方) 
  - [RefactoringMiner](#RefactoringMiner) 


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


## 研究用ツール
### JavaVariableExtractor
#### 基本的な使い方
1. リポジトリに公開されているjavaファイルをまとめた「jarファイル」を、Visual Studio Codeにダウンロードする。<br>
2. コマンドで実行
```
// コマンド「-v」：コマンドラインに処理内容を表示する
$ sudo java -jar JavaVariableExtractor.jar -v <java-file | java-file-directory>
```


### RefactoringMiner
