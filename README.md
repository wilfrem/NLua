NLua
====

NLuaをAndroid用にプロジェクト設定したもの。KeraLuaと一緒に使います

使い方
=====

これとKeraLuaをそのままプロジェクトに追加し、KeraLuaにあるShared Library(.so)をAndroidNativeLibraryとして追加します


このリポジトリを作るメモ
=========

* NLuaのLuaネイティブコード(本家Luaのコードとは違います)をAndroid-NDKを使ってビルドする(Android-NDKのサンプルをまねましょう
* ビルドしたファイルをlibs/{ターゲットCPU名}/hoge.soとかいう感じに置きます。Android-NDKのサンプルをまねるとビルド結果にlibsが出てきます
* libsを「Androidアプリケーションプロジェクト本体に」置き(KeraLuaじゃないです)、かつ.soのビルド設定をAndroidNativeLibraryとするとDllImport("hoge")で読めるようになる
* KeraLuaがLuaのポートになっており.soファイルを読み込む設定になっているので、.csファイルを追加して、KeraLuaおよびNLuaプロジェクトを作る
