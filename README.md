### セミナー開催アプリ
![session](https://github.com/nobou-g/study_app/blob/master/%E8%A1%A8%E7%B4%992.png)
<img src="https://github.com/nobou-g/study_app/blob/master/gyazo1.jpg" width="500" height="300"> 

# :ledger:本番環境
https://gg-session-app.herokuapp.com/  <br><br>
ログインID: test@t.t  <br><br>
パスワード: testtest  <br><br>
クレジットカード情報  
<blockquote><strong>カード番号：</strong>
4242424242424242
</blockquote>
<blockquote><strong>有効期限：</strong>
11/24
</blockquote>
<blockquote><strong>CVC番号：</strong>
111
</blockquote>
<blockquote><strong>名前：</strong>
TEST TEST
</blockquote>
<br><br>

# :ledger:開発環境
・Ruby  
・Rails  
・Javascript  
・jquery (Ajaxのため)  
・Payjp (クレジットカードのWebAPI)  
・Devise (ログイン機能)  
・MySQL  
・Heroku  
・AWS (HerokuとS3を繋げて、画像をバケット保管)  
・VSCode  
<br><br>

# :ledger:開発背景

友人が投資や株に関する勉強会を主催しており、[pando](https://pando.life/)や[ガクサー](https://gakucir.com/admins/login)といったWebサイトで募集をかけています。それらのWebサイトを利用した上で、彼が感じた不便な点や改良点を尋ねたことから、本アプリの作成に至りました。本アプリは、それらの問題点を補完することで、友人を含めたユーザーが抱える問題の解消の一助になることを望んだものとなります。  
  
<p>↓以下は具体的な問題点と改善点</p>  
<blockquote><strong>①参加者とのやりとりがメールのため、レスポンスに時間がかかり、それを1人1人相手しなければならない</strong><br>
<blockquote>→改善点：  
  この問題を補完するために「チャット機能」に着目した。まずチャットは、その手軽さにより参加者からのレスポンスの即時性が見込める。また、多人数相手にメッセージを送れるためメールよりも遥かに高い優位性を持つ。</blockquote>
</blockquote>
<blockquote><strong>②自分のセミナーから教材のようなものを出したい</strong><br>
<blockquote> →改善点：  
  本アプリでは主催者が商品を出品でき、そしてクレジットカードでの購入機能が搭載されている。そのため主催者が勉強会以外にも教材を提供ができ、上記のチャット機能と併用することで、参加者と主催者、参加者と参加者でリアルタイムにやりとりができるため、教材だけを提供されるだけではない細かいケアをしてもらえるという、オンラインサロンに似た体系を望める。</blockquote>
</blockquote>
<br><br>

# :ledger:アプリ機能
1.トップページ
--------
<strong><blockquote>•「Session List」に逐一最新のイベントが先頭にリストアップされるため、ユーザーは興味を持った勉強会に参加可能<br><br>
            • サイドバーにチャット中の勉強会が表示されるため、ユーザーはすぐにレスポンスすることができる<br><br>
            • 同じくサイドバーに主催している勉強会が表示されるようになっている<br>
</blockquote></strong>
<br><br>
<img src="https://github.com/nobou-g/study_app/blob/master/toppage2.gif" width="1000" height="600">  
<br><br>

2.ユーザー新規登録(+ログイン機能)  
--------
<strong><blockquote>Deviseを用いたユーザー新規登録機能<br>
</blockquote></strong>
<br><br>
<img src="https://github.com/nobou-g/study_app/blob/master/%E3%83%A6%E3%83%BC%E3%82%B5%E3%82%99%E3%83%BC%E6%96%B0%E8%A6%8F%E7%99%BB%E9%8C%B2.png" width="800" height="400">  
<br><br>


3.勉強会の登録機能  
--------
<strong><blockquote>テーマ、詳細内容、開催場所、開催日時などを登録して、勉強会を主催する<br>
</blockquote></strong>
<br><br>
<img src="https://github.com/nobou-g/study_app/blob/master/post.gif" width="800" height="400">  
<br><br>


4.フォロー機能  
--------
<strong><blockquote>興味を持った勉強会ホストをフォローすることができる<br>
</blockquote></strong>
<br><br>
<img src="https://github.com/nobou-g/study_app/blob/master/follow.gif" width="800" height="400">
<br><br>
<strong><blockquote>フォローしているユーザーの開催する勉強会のみを「Timeline」で逐一確認ができる<br>
</blockquote></strong>
<br><br>
<img src="https://github.com/nobou-g/study_app/blob/master/timeline.gif" width="800" height="400">  
<br><br>


5.チャット機能  
--------
<strong><blockquote>• 各勉強会にはチャットスペースがあり、そこでホストまたは他の参加者と情報共有ができる<br><br>
                    • ユーザーのメッセージは、Ajaxを用いて送信される<br>
</blockquote></strong>
<br><br>
<img src="https://github.com/nobou-g/study_app/blob/master/chat.gif" width="800" height="400">  
<br><br>


6.購入機能(+商品出品機能)  
--------
<strong><blockquote>• ユーザーはマイページから商品を出品することができる<br><br>
                    • 出品中の商品はマイページの下部に表示される<br><br>
                    • (マイページでは当該ユーザーの主催するイベントが確認できる)<br>
</blockquote></strong>
<br><br>
<img src="https://github.com/nobou-g/study_app/blob/master/mypage.gif" width="800" height="400">
<br><br>
<strong><blockquote>購入したい商品は、WebAPIの「Payjp」を用いてクレジットカード決済ができる
</blockquote></strong>
<br><br>
<img src="https://github.com/nobou-g/study_app/blob/master/purchase.gif" width="800" height="400">  
<br><br>

# :ledger:今後実装したい機能
<blockquote><strong>①カテゴリ機能+検索機能</strong><br>
<blockquote>→ ユーザーが自分の興味ある分野の勉強会により手軽にたどり着けるようにするために必要な機能</blockquote>
</blockquote>
<br>
<blockquote><strong>②クレジットカードの売上の細分化</strong><br>
<blockquote> → 商品が購入された際に、テナント側（出品者）に入る売上と、プラットホーム側（本アプリ）に入る売上が振り分けられていない状況のため実装していきたい</blockquote>
</blockquote>
<br><br>


# DB設計

## Usersテーブル

|Column|Type|Options|
|------|----|-------|
|name|string|null:false, unique:true|
|email|text|null:false, unique:true|
|affiliation|text|null:false|

### Association

- has_many :messages
- has_many :events
- has_many :active_relationships,         class_name: 'Relationship',
            foreign_key: 'user_id',
              dependent: :destroy
- has_many :followings, through: :active_relationships, source: :follow
- has_many :passive_relationships, class_name: 'Relationship',
              foreign_key: 'follow_id',
              dependent: :destroy
- has_many :followers, through: :passive_relationships, source: :user

## Eventsテーブル

|Column|Type|Options|
|------|----|-------|
|title|string|null:false|
|discription|text|null:false|
|image|binary|null:false|
|place|string|null:false|
|date|string|null:false|
|user_id|reference|foreign_key:true|

### Association
- belong_to :user
- has_many :messages

## Relationshipテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|reference|foreign_key:true|
|follow_id|reference|foreign_key:true|

### Association
- belong_to :user
- belongs_to :follow, class_name: 'User'

## Messagesテーブル

|Column|Type|Options|
|------|----|-------|
|content|text|null:false, unique:true|
|user_id|reference|foreign_key:true|
|event_id|reference|foreign_key|

### Association
- belongs_to :user
- belongs_to :event

## Itemsテーブル

|Column|Type|Options|
|------|----|-------|
|title|string|null:false|
|discription|text|null:false|
|price|string|null:false|
|image|binary|null:false|
|user_id|reference|foreign_key:true|

### Associations
- belongs_to :user
