Demo video ---> https://www.youtube.com/watch?v=PZouwE_45x4

**複数のライブ配信を行っているCHの場合は調子悪い気がする(クルクル回る)**

**体感で3秒以内に再生できない場合かな?? "I guess it's when you can't play it within 3 seconds? "**

# youtube-hls-live-m3u8

this page is tested.
This test may end without notice.

Redirects to an HLS streaming feed of a YouTube video,
responding with a "302 Found" status code if successful.

## hou to use. live channel ID
### ex..japan ONE PIECE (Youtube)
## https://hls.chew.jp/youtube/?channel=UCdAHaWcKdpbT5XkN2Er6BUQ

### or first "@" ID

## https://hls.chew.jp/youtube/?channel=@onepieceofficial

### or  if video id offer
### If there are multiple live streams, specify the video ID.
### ex..japan avex 24/7 Music Live (Youtube)
## https://hls.chew.jp/youtube/?video=tr77RbnfYIU

### https://hls.chew.jp/youtube/?channel=
### https://hls.chew.jp/youtube/?video=

If there are multiple live streams, choose the one with the most viewers.

Existing issues
Playback may not start.
Frequent shudders occur.

Please understand that this is a test.

#### 
#### 動作の仕組みについて。
#### リクエストを受け取る毎にyoutubeへアクセスを行っています。
#### 瞬間的に高速リクエストを行うソフトやアプリで実行しないで下さい。
#### 
#### 
#### [チャンネルID]or[動画ID]を受け取った際に
#### 各ページへアクセスを行い、HTMLを取得/解析しています。
#### 
#### チャンネルIDでの指定の場合の動作について
#### 1.チャンネルページを取得します。
####  その際に、複数配信の確認の為 [X本のストリーム] の文字列を検索します。
####  見つかった場合、更に検索にて視聴人数の最も多い動画を割り出します。
####  視聴人数の最も多い[動画ID]を取得します。
####  [X本のストリーム]が見つからなかった場合は、[チャンネルID]の後ろに[/live]
####  の文字を追加する事で、ライブ配信の[動画ID]の取得としています。
#### 
#### 2.動画IDを取得出来た後の処理
####  [動画ID]を元に[APIリクエスト]を行います。
####  2024.12.16頃にyoutubeで大きな変更が加えられました。
####  それまでは出来ていた[APIリクエスト]のパラメーターが変更されたのです。
####  研究に研究を重ねる事で、突破出来る事を突き止めました。
#### 
#### 3.「2」での事を踏まえて、新方式の[APIリクエスト]を行っています。
####  json形式で送信する項目が約60種類にも及んでいます。
#### 　1度セットしてしまえば、動画IDだけを変更してOKな状態になっているため、
####  プログラム的には問題ありませんでした。
####  PHPプログラムで行数にして約200行、容量10KB程度です。
#### 
