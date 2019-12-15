<h1 align="center">世界を変えるdojyoを作ろう</h1>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/d/total.svg" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/v/stable.svg" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/license.svg" alt="License"></a>
</p>

## ブランチの使い分け

master：本番環境<br>
release:（本来は本番に放り込む前にテストしてこれをmasterにpushするはずなのですが、）今回は、正しく動作しているチェックポイントとしてバックアップに使いたいと思います。
develop:開発環境、機能が完成したら、作業用のブランチからここにプルリクエストを飛ばしてください。
feat/???:新規機能を作成中に使用するブランチ。４人別々の作業をすると思うので、各自作成してください。
fix/???:少しバグを修正したい時に使用するブランチ。４人別々の作業をすると思うので、各自作成してください。

## 基本的な流れ

①各自featかfixブランチのローカルで作業して、作業の経過をcommitしておく（この辺りは個人作業なので報告不要）
　　※commitメッセージに関しては下記でルールを記載します。

②作業がひと段落して、機能が完成したら、ローカルで作業しているブランチからremoteの同ブランチへpushする。

③developへプルリクエスト→マージする（報告必須！）
　コンフリクト発生時は慌てず騒がず。コンフリクトに関しては下記でルールを記載します。
 
④developからpullしてブランチを最新の状態にして作業を再開

※ややこしいのですが、履歴は全てgithub上で見れるので、ミスがあったら巻き戻れば良いだけなのでガンガン使っていきましょう。
※開発段階ではデータベースに情報が溜まらないので大惨事にはならないはずです！

## commitメッセージについて

１行目に、何の作業をしたのか他の人に伝わりやすく書きましょう。
２行目以降は自由に伝えたいこと、自分のメモなど。

## コンフリクト発生時の注意

深呼吸する。
ギットクラーケンの赤文字は基本的にノリでOKを押さない方が良いかもです。
コンフリクト発生時は、Github上で正しい方を残して更新する方法が一番簡単だと思います。

作業が多い場合は、一度ローカルのdevelopでpullをして最新状態にします。
ローカルdevelop→作業したブランチへマージ。
コンフリクトが起きるので修正をしてブランチをステージング→pushする。
もう一度remote上でdevelopへプルリクエストするとmergeされて成功！

コンフリクトが発生したとき他の人が何の作業をしたのか確認をして修正するようです。


## ファイル名とファイルの分け方

完全に表示されるページを分けた方が分かりやすいと思います。
もちろん、usersの中にフォルダを作成して見やすくしてもOKです！

【View】
resouces→view→users→???.blade.php
resouces→view→clients→???.blade.php
resouces→view→admin→???.blade.php

【CSS】
public→css→users→???.css
public→css→clients→???.css
public→css→admin→???.css

【JS】
public→js→users→???.js
public→js→clients→???.js
public→js→admin→???.js

対応するViewとCSSとJSは【同じ名称にする】

layouts.appには絶対に共通になるであろうheadタグだけ記載し、
CSSやJSはViewごとに読み込むファイルを記載する。


##composerの利用について

composerで追加した機能は共有していきましょう。
コマンドを叩いて導入したものは、まとめておいて、いざというときの復元作業で使うことがあるようです。
（Qiitaの本番環境でやらかした記事より）


##どんどんルールの追記お願いします。
