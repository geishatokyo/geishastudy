# SBT のインストール

Scala 開発を行うために以下をインストールします。

1. JDK (Java Development Kit)
2. SBT (Simple Build Tool)

## Windows

### JDK のインストール

2014年9月現在ではバージョン7以下のJDKをインストールしてください。
JDK8以上ではSBTが正常に動作しない可能性があります。

1. Webブラウザで以下にアクセスする。  
http://www.oracle.com/technetwork/java/javase/downloads/index.html
2. JDK　の下の "Download" をクリックする。  
3. "Accept License Agreement" にチェックを入れて、Windows x64 の .exe をダウンロードする。  
もし 32bit OS を使っている場合には、x86 の方を使う。
4. ダウンロードしてきたインストーラを起動し、jdk をインストールする。
5. 動作確認をする。  
コマンドプロンプトを開いて javac コマンドが実行できることを確認する。  
もし実行できなかった場合には javac コマンドへの PATH が正常に指定されていることを確認する。 

### SBT のインストール

1. Webブラウザで以下にアクセスする。  
http://www.scala-sbt.org/release/docs/Getting-Started/Setup.html
2. sbt 0.13.x のインストーラをダウンロードする。  
sbt.msi
3. ダウンロードしてきたインストーラを起動し、sbt をインストールする。
4. 動作確認をする。
    sbt --version

## Mac OS X 

Mac では sbt-extras を使ってインストールを行います。

### JDK のインストール

1. Webブラウザで以下にアクセスする。  
http://www.oracle.com/technetwork/java/javase/downloads/index.html
2. JDK　の下の "Download" をクリックする。  
3. "Accept License Agreement" にチェックを入れて、Mac OS X x64 の .dmg をダウンロードする。
4. ダウンロードしてきた .dmg をクリック(マウント)して表示される .pkg をダブルクリックして jdk をインストールする。
5. 動作確認をする。  
ターミナルを開いて javac コマンドが実行できることを確認する。  
もし実行できなかった場合には javac コマンドへの PATH が正常に指定されていることを確認する。 


### SBT のインストール

1. ターミナルから以下のコマンドを実行する。  
    curl -s https://raw.githubusercontent.com/paulp/sbt-extras/master/sbt > ~/bin/sbt && chmod 0755 ~/bin/sbt  
2. 動作確認をする。  
    sbt --version


#### brew install で sbt を インストールした場合

brew install で sbt をインストールすると、コンパイル時にメモリ不足の例外が発生することがあります。
次のように環境変数を設定すると多くの場合に問題が解決します。
```
SBT_OPTS="-Xms512M -Xmx2G -Xss1M -XX:+CMSClassUnloadingEnabled -XX:MaxPermSize=512M"
```

## 注意点

* 環境変数の設定  
    * JAVA_HOME  
http://www.javadrive.jp/install/jdk/index4.html
* 参考資料  
http://scalajp.github.io/sbt-getting-started-guide-ja/setup/
