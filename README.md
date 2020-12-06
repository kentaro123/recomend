# 気分にあった音楽レコメンドシステム
## 概要
入力された気分や事象などから感情をAIで読み取り，読み取った感情に応じて音楽をレコメンドするシステム！

[レコメンドページへ](https://master.d13kgn6n4if7g7.amplifyapp.com/)

## システムの説明
* 気分や出来事を入力すると，入力された文の感情をAIが読み取り感情に応じた音楽をレコメンドする
  （例）今日はいい買い物ができた！，溝に落ちてしまった
* 検索結果にはレコメンドする曲と入力された文から読み取った感情が表示される
* 読み取る感情は「Positive」「Negative」「Neutral」「Mixed」の4種類

## システムの内容
* 主にAWSを利用
* システム構成図
* ![](https://github.com/kentaro123/recomend/blob/master/images/system.png?raw=true)

* AWSの中でもAmplify, API Gateway, Lambda, S3, Comprehendを利用
* レコメンドの仕組みは，4つの感情それぞれのデータセットを作成し，読み取った感情のデータセットの中からランダムに曲を選択しレコメンドする

## 作ってみた感想
AWSを用いたWebアプリケーションを作ってみたいと思い取り組んでみました．AWSの中でも私が研究で学んでいる機械学習を用いた機能を利用したくてComprehendの利用を決めました．数ある機械学習の機能の中でComprehendを利用した理由は，過去のインターンで自然言語処理について少し学んだのでその知識が活かせると感じたためです．レコメンドはこれからの世の中でより活発に用いられる機能だと思うのでこのテーマで取り組めて勉強になったし楽しかったです．ただ，レコメンドが進みすぎてフィルターバブルのような問題が起こる世界は少し怖いですね．

## 今後の展望

現在は，識別できる4つの感情それぞれでデータセットを作成し，推薦する曲はデータセットの中からランダムに選択している．これだけだと，適切なレコメンドには遠いと感じているため，入力された文をベクトルで表現し，データセットに存在する曲名とベクトルが近い曲をレコメンドするような機能を追加したいと考えている．また，レコメンドに対する満足度フィードバックがほしいため紹介したあとに満足度に関するアンケートを表示する機能も追加したい．このどちらの機能もAWSを上手に利用することができれば実現できそうなので取り組んでいこうと考えている（ElasticSearch? DynamoDB?）．