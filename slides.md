---
theme: apple-basic
title: '明日から構築できる Flutter CI 入門'
download: true
layout: intro-image
image: 'https://i.pinimg.com/564x/35/5d/d8/355dd88362d2b72ff4f84b3041b516a4.jpg'
fonts:
  sans: M PLUS 1p
---

<div class="absolute top-10">
  <span class="font-700">
    2022/5/18 すさ ＠Flutter大学勉強会
  </span>
</div>

<div class="absolute bottom-10">
  <h1>明日から構築できる<br>Flutter CI 入門</h1>
  <p>GitHub Actions で CI を構築する方法を徹底解説</p>
</div>

---
layout: statement
---

# 今日のゴール

<br>

<v-click>

🌱 CI の必要性を理解する

</v-click>

<v-click>

✨ CI を自力で構築できるようになる

</v-click>

<v-click>

🔥 復習

</v-click>

<style>
p {
  font-size: 30px;
}
</style>

---

# 自己紹介

<img src="https://pbs.twimg.com/profile_images/3229257541/0f3a5a42716a230e07619abc86d67b8d_400x400.png" class="rounded shadow absolute  bottom-10 right-10" width="160" >

すさ

Twitter: [@susatthi](https://twitter.com/susatthi) / GitHub: [@susatthi](https://github.com/susatthi) / #times_すさ

都内在住 ２児のパパ兼フリーランスエンジニア（５年目）、自動化大好きマン<br>
Flutter大学 2020年7月〜、 Flutter 歴は約 2 年、<br>
最近の仕事は Swift / PHP、個人開発で Flutter を使っています。<br>
個人アプリ「医療費を管理して賢く節税」をリリースしています！

<img src="/images/medical-deduction.png" class="rounded shadow absolute" width="340" >

---

# もくじ

<div grid="~ cols-2 gap-4">
<div>

- はじめに

- CI
  - CI とは何か？
  - CI の位置づけ
  - CI 導入のメリットとデメリット
  - CI の構築方法

- GitHub Actions
  - GitHub Actions とは
  - YAML とは
  - ワークフローの構成
  - ワークフローの定義方法
  - 実例

</div>
<div>

- Tips
  - ローカルテストを楽にしよう
  - リファレンスアプリの紹介

- コラム

- さいごに

発表時間 55 分（質疑 5 分）

</div>
</div>

---

# はじめに

<br>

想像してください。あなたはスタートアップの Flutter エンジニアです。

アプリをリリースして半年が経ちユーザ数も伸びてきたところで次の課題に直面しています。

- ユーザからのバグ報告が増えてきた
  - 「バージョンアップしたらアプリが落ちるようになりました😡」
  - 「昨日から通知が来ません😅」

- バグを修正するたびに別のバグが発生して新機能の開発が進まない

<div class="absolute bottom-10">
  <p>継続してアプリを成長させていくためには品質を維持する必要がありました。</p>
  <p>そこで、リリース前のテストを導入しました。</p>
</div>

---

テストシナリオを作って、テスターを雇い、リリース前テストを導入しました。

するとユーザからのバグ報告は減り、新機能の開発が進むようになりました。

しかし、しばらくするとまた新たな課題が見つかります。

- アプリが成長するにつれリリース前テストが増えて工数が増えてきた
- リリース毎にほぼ同じテストをしている
- リリース前にしかテストをしないのでバグの発見が遅い

<div class="absolute bottom-10">
  <p>解決策を調べていると "CI" というものを導入するとよさそうなのでもっと調べてみることにしました。</p>
  <p align="right">つづく</p>
</div>

---
layout: section
---

# CI
## Continuous Integration (継続的インテグレーション)

---

# CI とは何か？

<br>

## 短いサイクルで自動テストをして品質を維持しながら開発をすること

ここで言う『テスト』とは次の 3 つのことを指しています。

① コードフォーマット

② 静的解析

③ テスト

<div class="absolute bottom-10">
  <p>なお、今回 CD (継続的デリバリー) は扱いません。</p>
  <p>CD とは、自動的にデプロイやストア配信をしていち早くユーザにプロダクトを届けることです。</p>
</div>

---

# さいごに

<br>

『明日から構築できる Flutter CI 入門』ということで

- CI の必要性、メリット、デメリット
- GitHub Actions で CI を構築する方法

を紹介してきました。

<br>

それぞれの事情もあると思うのですぐの構築ができないとしても、少なくとも CI の必要性は理解しておき、いざというときに構築できるようにしておくことは大事だと思います。

<br>

今回の勉強会が共同開発、個人開発、お仕事に少しでもお役にたれれば幸いです。

<p class="absolute right-10">
おわり
</p>


