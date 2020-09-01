### セミナー開催アプリ
![session](https://github.com/nobou-g/study_app/blob/master/%E8%A1%A8%E7%B4%992.png)
<img src="https://github.com/nobou-g/study_app/blob/master/gyazo1.jpg" width="500" height="300">  

# :ledger:開発背景

友人が投資や株に関する勉強会を主催しており、[pando](https://pando.life/)や[ガクサー](https://gakucir.com/admins/login)といったWebサイトで募集をかけています。それらのWebサイトを利用した上で、彼が感じた不便な点や改良点を尋ねたことから、本アプリの作成に至りました。本アプリは、それらの問題点を補完することで、友人を含めたユーザーが抱える問題の解消の一助になることを望んだものとなります。  
  
<p>↓以下は具体的な問題点</p>  
<blockquote><strong>①参加者とのやりとりがメールのため、レスポンスに時間がかかり、それを1人1人相手しなければならない</strong><br>
<blockquote> →改善点：  
  この問題を補完するために「チャット機能」に着目した。まずチャットは、その手軽さにより参加者からのレスポンスの即時性が見込める。また、多人数相手にメッセージを送れるためメールよりも遥かに優位性を持つ。</blockquote>
</blockquote>
<blockquote><strong>②自分のセミナーから教材のようなものを出したい</strong><br>
<blockquote> →改善点：  
  この問題を補完するために「チャット機能」に着目した。まずチャットは、その手軽さにより参加者からのレスポンスの即時性が見込める。また、多人数相手にメッセージを送れるためメールよりも遥かに優位性を持つ。</blockquote>
</blockquote>



# :ledger:アプリ概要

# :ledger:開発環境
・Ruby  
・Rails  
・Javascript  
・jquery  
・MySQL  
・Payjp(クレジットカードのAPI)  
・VSCode  

# :ledger:アプリ機能
1.トップページ
--------
<img src="https://github.com/nobou-g/study_app/blob/master/toppage2.gif" width="800" height="400">  


2.投稿機能  
--------
<img src="https://github.com/nobou-g/study_app/blob/master/post.gif" width="800" height="400">  


3.フォロー機能  
--------
<img src="https://github.com/nobou-g/study_app/blob/master/follow.gif" width="800" height="400">
<img src="https://github.com/nobou-g/study_app/blob/master/timeline.gif" width="800" height="400">  


4.チャット機能  
--------
<img src="https://github.com/nobou-g/study_app/blob/master/chat.gif" width="800" height="400">  


5.購入機能  
--------
<img src="https://github.com/nobou-g/study_app/blob/master/mypage.gif" width="800" height="400">
<img src="https://github.com/nobou-g/study_app/blob/master/purchase.gif" width="800" height="400">  

# :ledger:苦労したポイント

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
- has_many :relationships
- has_many :followings, through: :relationships, source: :follow
- has_many :reverse_of_relationship, class_name: 'Relationship', foreign_key: follow_id
- has_many :followers, through: :reverse_of_relationship, source: :user

## Eventsテーブル

|Column|Type|Options|
|------|----|-------|
|title|string|null:false|
|discription|text|null:false|
|image|binary||
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

## Messagesテーブル

|Column|Type|Options|
|------|----|-------|
|content|text|null:false, unique:true|
|user_id|reference|foreign_key:true|
|event_id|reference|foreign_key|

### Association
- belongs_to :user
- belongs_to :event
