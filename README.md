# Twitter Scraper

Scraping twitter content from [twitter streaming API](https://dev.twitter.com/streaming/overview), in python3.

このレポジトリは，[Marsam-Ma-zz/twitter_scraper](https://github.com/Marsan-Ma-zz/twitter_scraper)を日本語リプライ収集用に独自改良したものです．

ChatBot，クソリプ収集目的等にご利用ください．

## 環境
- Twitter Streaming API
- Python 3.6+

## 使い方
### Set up

1. Twitter API tokens を[入手](https://apps.twitter.com/)．
1. `config.yml.default` をコピーして `config.yml` を作成．
1. `config.yml` に 1. で入手した自分の tokens をそれぞれ記入．
1. `pip install -r requirments.txt`

### 実行
`screen`コマンド等を用いると便利です．
```sh
python twitter.py
```
`corpus/ja_YYYYMMDD_HHMMSS.txt`に保存されます．


**また，このスクリプトは問題が発生する限り半永久的に収集しますのでご注意ください．**  

### 出力
(例)　実際には日本語

Line number | Sentences
------------|---------
1 | 誕生日おめでとう!
2 | ありがとう！
3 | おはようー
4 | おは！

それぞれ
Line number(1,2),(3,4)  がそれぞれ独立した会話のペアになっており，  
奇数行が発言，偶数行がそれに対する返信となっています．

### フィルター
[stream.filter](https://developer.twitter.com/en/docs/tweets/filter-realtime/guides/connecting)を用いて監視を行います．  

`track`に指定した文字列により，指定の検索ワードでストリーミングが行えます．
デフォルトでは，

```python
track=['私','あなた','俺','ー','する','です','ます','けど','何','@', '#', '＃', '。', '，', '！','？','…', '.', '!','?', ',', ':', '：', '』', ')', '）', '...']
```

という適当な文字列を指定しています．



さらに自分でフィルターを改良することができます．  
詳しくは[公式ガイド](https://developer.twitter.com/en/docs/tweets/filter-realtime/guides/connecting)を参照ください．
