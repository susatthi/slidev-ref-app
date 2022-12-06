---
theme: apple-basic
title: 'リファレンスアプリで実践的なスキルを身につける方法'
download: true
layout: intro-image
image: 'https://meideru.com/wp-content/uploads/2020/06/coder_1591104127-e1591104158891.jpg'
fonts:
  sans: M PLUS 1p
---

<div class="absolute top-10">
  <span class="font-700">
    2022/12/7 すさ ＠Flutter大学勉強会
  </span>
</div>

<div class="absolute bottom-10">
  <h1>リファレンスアプリで実践的なスキルを身につける方法</h1>
  <p>小さいアプリで大きく学ぼう</p>
</div>

---
layout: statement
---

# 今日のゴール

<br>

自分もリファレンスアプリを作ってみよう！

と思って頂けるとうれしいです。

<style>
p {
  font-size: 30px;
}
</style>

---

# 自己紹介

<img src="https://pbs.twimg.com/profile_images/3229257541/0f3a5a42716a230e07619abc86d67b8d_400x400.png" class="rounded shadow absolute  bottom-10 right-10" width="160" >

すさ

都内在住 ２児のパパ兼フリーランスエンジニア（6年目）<br>
Flutter大学 2020年7月〜、 Flutter 歴は約 2 年半<br>
近況１：Flutter 実務経験が半年になりました！<br>
近況２：共同開発 10（スタンプラリー）でテックリードやってます！<br>
2021年6月に個人アプリ「医療費を管理して賢く節税」をリリースしています！<br>

<img src="/images/medical-deduction.png" class="rounded shadow absolute" width="340" >

---

# もくじ

<div grid="~ cols-2 gap-4">
<div>

- はじめに

- リファレンスアプリとは？

- なぜリファレンスアプリを作ると良いか？

- おすすめのリファレンスアプリの要件


</div>
<div>

- リファレンスアプリで学べる実践的なスキル
  - アーキテクチャ／Firebase 連携 ／ 環境分け（Flavor 対応）／アプリアイコンの作り方／スプラッシュ画面の作り方／ロガーの選定／カスタムフォントの導入方法／多言語対応／ローカル DB の選定／画像のキャッシュ／ go_router を使った画面遷移／ダークモード対応／レスポンシブ対応／Lottie を使ったアニメーション／ REST API の実装方法／単体テスト／ Widget テスト／ CI ／ CD

- さいごに


</div>
</div>

---
layout: image-right
image: '/images/codewithandrea.png'
---

# はじめに

<br>

リファレンスアプリを作ろうとしたきっかけは 1 つの記事でした。

https://codewithandrea.com/articles/flutter-app-architecture-riverpod-introduction/

それまでアーキテクチャは MVVM + Repository を採用していましたが、ぶっちゃけ雰囲気で書いてました。2022 年 3 月、たまたま見つけたこの記事を読んで衝撃を受けました。Riverpod を使ったアーキテクチャの正解にたどり着いた気がしたからです。

そこで、当時話題になっていた [株式会社ゆめみの Flutter エンジニアコードチェック](https://github.com/yumemi-inc/flutter-engineer-codecheck) を題材にして、最適なアーキテクチャとは何か試してみることにしました。

---

# はじめに

<br>

リファレンスアプリを作りはじめて 8 ヶ月が経ちました（延べ 420 時間使いました）。

やってみたら、アーキテクチャはもちろん、Flutter アプリをリリースするために、あるいは Flutter で仕事をするための様々な実践的なスキルを学ぶことができました。加えて、2022 年 7 月から Flutter × Firebase の実務経験も積むことが出来ています。 

<br>

これらの経験を踏まえて、今日の勉強会では、次のことをお伝えできればと思います！

- なぜリファレンスアプリを作ると良いか？
- おすすめのリファレンスアプリの要件
- どんな実践的スキルがが学べるのか

---
layout: section
---

# リファレンスアプリとは？

---

# リファレンスアプリとは？

<br>

## アプリ開発を進めるときに参考にするアプリ・コード


- 一般的な単語ではありません

- アーキテクチャのアイデアを思いついたり、新しいパッケージがでたり、パッケージのバージョンが上がったときの実験場として使っています

- 破壊的な変更が短時間で出来るように**十分に小さいアプリ**が望ましいです

- 新しいアプリを作るときにリファレンスアプリのコードを**流用したり参考にします**
  - 「共同開発 10 スタンプラリー」は、私のリファレンスアプリの実装をベースにしました

---

# なぜリファレンスアプリを作ると良いか？

<br>

- ## 基本的で実践的なスキルがつきます
### 座学ではなく実際に手を動かすから

- ## 知識が定着します
### 自分なりに考え、体現して、手を動かすから

- ## 技術記事を書くきっかけになります
### アウトプットは重要です・・・

- ## 新しいアプリが速くリリース出来るようになります
### リファレンスアプリのコードを参考にできるから

---

# リファレンスアプリの紹介

https://github.com/susatthi/github-search

<div grid="~ cols-2 gap-4">
<div>

<img src="/images/github-search-1.png" class="rounded shadow absolute" width="380">

</div>
<div>

<img src="/images/github-search-2.png" class="rounded shadow absolute" width="380">

</div>
</div>

---
layout: section
---

# おすすめのリファレンスアプリの要件

---

# 非機能要件

<div grid="~ cols-2 gap-4">
<div>

- Flutter × Firebase
  - 私は GitHub API を題材にしたリファレンスアプリを作りましたが、REST API と Firebase では実装が変わってくるので、Firebase を使うことをおすすめします。
- Navigator 2.0 対応 (go_router)
- Flavor 対応 ( dev / prod )
- Android / iOS / Web
- CI (継続的インテグレーション）

</div>
<div>

- できたら
  - CD (継続的デリバリー)
  - 単体テスト／ Widget テスト
  - Integration テスト

</div>
</div>

---

# 機能要件

<div grid="~ cols-2 gap-4">
<div>

- TODO 機能
  - TODO の一覧表示／検索
  - TODO の詳細表示
  - TODO の登録／編集／削除
  - TODO を完了できる
  - 理由: CURD を実践できるから

- お知らせ機能
  - 運営からのお知らせを配信
  - プッシュ通知
  - 未読 / 既読
  - 理由: クライアントサイドジョインを実践できるから

</div>
<div>

- 匿名認証
- レスポンシブ対応
  - 理由: Auto Layout を意識するため
- ダークモード対応
  - 理由: 適切に Theme を使えるようにするため
- アプリアイコン対応
- スプラッシュ画面対応
- カスタムフォント
- できたらなお良し
  - 多言語対応 (英語対応)
  - その他の認証 ( password, google, etc... )
  - ストアリリース

</div>
</div>

---
layout: section
---

# リファレンスアプリで学べる実践的なスキル

---

# アーキテクチャ

世の中には様々なアーキテクチャがあります。よさそうなアーキテクチャを自分なりに試してより理解を深めましょう。

- MVC（Model-View-Controller）
- MVP（Model-View-Presenter）
- MVVM（Model-View-ViewModel）
- The Clean Architecture
- Flux
- BloC

2021 年 4 月 14 日の Flutter 大学の勉強会で、[「私の考える MVVM + Repository アーキテクチャについて意見がほしい」](https://docs.google.com/presentation/d/1ZCTJHgjfO1ig-4VGnJb1ulJNSY3M4yhFV21COIivEZA/edit?usp=share_link) を発表しました。

あれから約 1 年半経過し、Riverpod への理解も深まり、自分なりになかなか良いアーキテクチャになってきました。リファレンスアプリを作る前と後のアーキテクチャを少し紹介します。

---

# アーキテクチャ ( 1 年半前 )

画面毎に View + ViewModel を作成、BasePage や BaseViewModel で共通化

DI が出来ていないためテストが出来ない、Repository 同士が呼び合ってカオス、複数の ViewModel に同じような実装がたくさん

<img src="/images/mvvm-repository.png" class="rounded shadow absolute" width="640">

---

# アーキテクチャ（現在）

<div grid="~ cols-2 gap-4">
<div>

<img src="/images/arch.png" class="rounded shadow absolute" width="240">


</div>
<div>

- DDD / CQRS / CodeWithAndrea に影響を受けたオリジナルのレイヤードアーキテクチャ
- Riverpod のリアクティブ・キャッシングとデータバインディングという強みを活かした構成
- まだ試行錯誤中

<br>
<img src="/images/riverpod.png" class="rounded shadow absolute" width="400">


</div>
</div>

---

<img src="/images/kaosu.png" class="rounded shadow absolute" width="550">

---

# Firebase 連携／環境分け（Flavor 対応）

- Flutter × Firebase は多くのケースで利用されています
- 実案件では必ず環境分け ( dev / stg / prod ) が必要です
- Flutter × Firebase のシステム構成の例（共同開発 10 スタンプラリーから）

<br>

<div grid="~ cols-2 gap-4">
<div>

<img src="/images/flutter-firebase-system-arch.png" class="rounded shadow absolute" width="380">


</div>
<div>

<img src="/images/firestore-functions.png" class="rounded shadow absolute" width="450">

</div>
</div>


---

# 技術記事で紹介

<div grid="~ cols-2 gap-4">
<div>

学んだことは技術記事として公開しています。

https://zenn.dev/susatthi

- アプリアイコンの作り方
- スプラッシュ画面の作り方
- ロガーの選定
- カスタムフォントの導入方法
- 多言語対応
- ローカル DB の選定
- 画像のキャッシュ
- flutterfire_cli

</div>
<div>

<img src="/images/zenn.png" class="rounded shadow absolute" width="260">

</div>
</div>

---

# go_router を使った画面遷移

- 画面遷移が楽になる
  - 基本は何でも `go()`
  - A => B => C とあるとき、A で `go(C)` と実行するだけで、
  
  B も自動でスタックされる
  - 独自にスタックに積みたければ `push()` もある
  - 特に直接 URL 指定で任意の画面を表示出来てしまう Flutter Web で便利
- バージョンアップが早く、破壊的変更が多く、よくデグレってる
- 最近 go_router_builder も使いはじめました。便利です！
  - 記事 →  [【Flutter】go_router をタイプセーフに使う方法【go_router_builder】](https://zenn.dev/susatthi/articles/20220801-135028-flutter-go-router-builder)


<img src="/images/go-router-bug.png" class="rounded shadow absolute top-10 right-10" width="330" >


---

# ダークモード対応

- ダークモード対応自体は超簡単！
- ただし、各Widgetで `color` を直指定せず、`Theme.of(context).colorScheme` を使うこと

```dart
// App
final lightTheme = ref.watch(themeProvider(Brightness.light));
final darkTheme = ref.watch(themeProvider(Brightness.dark));
return MaterialApp.router(
  theme: lightTheme,
  darkTheme: darkTheme,
);
```

```dart
// ThemeData
final themeProvider = Provider.family<ThemeData, Brightness>(
  (ref, brightness) => ThemeData(
    colorScheme: ColorScheme.fromSwatch(
      brightness: brightness,
      primarySwatch: Colors.grey,
    ),
  ),
);
```

---

# レスポンシブ対応

- いろいろ探したけど [responsive_framework](https://pub.dev/packages/responsive_framework) がオススメです → [デモサイト](https://gallery.codelessly.com/flutterwebsites/minimal/#/)


```dart
return MaterialApp.router(
  builder: (context, child) {
    return ResponsiveWrapper.builder(
      child,
      //    0 ----- AUTOSCALE ----- 320
      //  320 -----   RESIZE  ----- 768(MOBILE)
      //  768 -----   RESIZE  ----- 1024(TABLET)
      // 1024 -----   RESIZE  ----- ∞(DESKTOP)
      breakpoints: [
        const ResponsiveBreakpoint.resize(320, name: MOBILE),
        const ResponsiveBreakpoint.resize(768, name: TABLET),
        const ResponsiveBreakpoint.resize(1024, name: DESKTOP),
      ],
      minWidth: 320,
      maxWidth: 1600,
      defaultScale: true,
      background: Container(
        color: Theme.of(context).colorScheme.surface,
      ),
    );
  },
);
```
---

# Lottie を使ったアニメーション

<div grid="~ cols-2 gap-4">
<div>

- [LottieFiles](https://lottiefiles.com/) から json ファイルをダウンロード
- コードはこれだけ

```dart
Lottie.asset(
  'assets/lottie/download.json',
  width: 200,
),
```

<br>

<img src="/images/lottie-files.png" class="rounded shadow absolute" width="400">


</div>
<div>

<img src="/images/lottie-demo.gif" class="rounded shadow absolute" width="320">


</div>
</div>

---

# 【参考】REST API の実装方法

- [http](https://pub.dev/packages/http) を使いました
- [http2](https://pub.dev/packages/http2) なんてあるみたい（試してない）
- [dio](https://pub.dev/packages/dio) は有名です（試してない）
- [chopper](https://pub.dev/packages/chopper) も人気ありそうです（試してない）
- [retrofit](https://pub.dev/packages/retrofit) は Kotlin でよく使われていますが、Dart にもありました（試してない）

<div class="absolute bottom-10">
  <p>他にもあるかも、比較記事が求められる。。</p>
</div>

---

# http のサンプルコード

```dart
Future<T> get<T>({
  required Uri uri,
  required T Function(Map<String, dynamic> data) responseBuilder,
}) async {
  try {
    final response = await client.get(uri, headers: _headers);
    switch (response.statusCode) {
      case 200:
        final data = json.decode(response.body) as Map<String, dynamic>;
        return responseBuilder(data);
      case 400:
        throw NetworkException.badRequest();
      case 404:
        throw NetworkException.notFound();
      case 503:
        throw NetworkException.serviceUnavailable();
      default:
        throw NetworkException.unknown();
    }
  } on SocketException catch (e) {
    throw NetworkException.noInternetConnection();
  }
}
```

---

# 単体テスト／ Widget テスト

- Riverpod で DI しておくと、単体テストが書きやすいことがわかりました
- 単体テスト／ Widget テストのメンテナンスが精神的にしんどい。。。
- 思ったお通りに動かず、都度調べて、時間が溶ける
- やる場合は覚悟が必要
- 呪文コードが多くなりがち

```dart
// pumpAndSettle() だと途中で止まる
// pump() を 2回実行するとうまくいく
// await tester.pumpAndSettle();
await tester.pump();
await tester.pump();
```

```dart
// テストは遅延処理が空振りするが、runAsync() で囲めばうまくいく
await tester.runAsync(() async {
  ・・・
}
```

---

#  CI ( 継続的インテグレーション )

- 2022/5/18 に勉強会で発表しました
https://flutteruniv.com/materials/lecture_videos/8Fqw9i9coeXS3yJZWp7Z

<br>

<img src="/images/ci.png" class="rounded shadow absolute" width="470">

---

# CD (継続的デリバリー）

- 自動デプロイや自動リリースのこと
- GitHub Actions, Bitrise, Circle CI, など様々な CI サービスがある
- 具体例としては、main ブランチに push したら、自動で Web 版をデプロイしたり、GooglePlay や AppStore に自動アップロードをします。
- 必須とは思いませんが、やっておくと面倒なルーティーンから解放されるし、リリース事故が起こりにくくなります。

- 実際、私は実案件で GitHub Actions を使って次の CD を構築しました
  - Flutter Web を Firebase Hosting に自動デプロイ
  - Flutter Android をリリースビルドして Google Play Console に自動アップロード
  - Flutter iOS をリリースビルドして AppStore に自動アップロード
  - Firebase の各サービス (Firestore Indexes / Firestore Rules / Storage Rules / Functions / Remote Config ) を自動デプロイ

---

# さいごに

<br>

『リファレンスアプリで実践的なスキルを身につける方法』ということで、

- なぜリファレンスアプリを作ると良いか？
- おすすめのリファレンスアプリの要件
- どんな実践的スキルがが学べるのか

を紹介してきました。

<br>


今日の勉強会が共同開発、個人開発、お仕事に少しでもお役にたてれば幸いです。

<div class="absolute bottom-10 right-10">
  <p>おわり</p>
</div>

