# shinjuku<br>mokumoku #31

tanaken0515([@tanaken0515](https://twitter.com/tanaken0515))

---

# 自己紹介

<img width="1215" alt="2018-10-20 16 34 24" src="https://user-images.githubusercontent.com/26683960/47252844-2407d780-d486-11e8-9a52-bd3789628865.png">

---

# やること

---

SlackでログインするだけのWebアプリ
を作る

--- 

# やること（細分化）

1. dockerで環境を作る
2. `rails new` する
3. ユーザモデルとログイン画面を作る
4. Slackログインボタンを置く
5. ログインが許可された後の処理を書く


---

# 1. dockerで環境を作る
- Dockerfile, docker-compose.yml いい感じに書く
  - ruby2.5.3, rails5.2.2, postgres10.5
- `docker-compese build`

---

# 2. `rails new` する
- `docker-compose run --rm web bash`
- コンテナ内
  - `cd ..`
  - `rails new slack-auth-app`

---

# 3. ユーザモデルとログイン画面を作る

ガッっとやる。
SlackワークスペースIDとSlackユーザIDがあれば良さそう

---

# 4. Slackログインボタンを置く

---

<img width="926" alt="2019-01-19 16 32 05" src="https://user-images.githubusercontent.com/26683960/51423746-e55df680-1c07-11e9-894a-5b9094195f74.png">

---

置いた。

---

## 手順

- slackアプリを作る
  - https://api.slack.com/apps でアプリを作る
- slackログインボタンの飛び先のURLを作る
- ボタンを置く
  - https://api.slack.com/docs/slack-button にボタンある

---

## slackログインボタンの飛び先のURLを作る

```ruby
  def redirect_to_slack_oauth
    scope = 'XXXX'  # https://api.slack.com/docs/oauth-scopes にあるscope
    client_id = 'XXXXXX.XXXXXXXX'   # https://api.slack.com/apps/:your_app_id のAppCredentialsに書いてある
    uri = return_from_slack_oauth_url
    redirect_to "https://slack.com/oauth/authorize?scope=#{scope}&client_id=#{client_id}&redirect_uri=#{uri}"
  end
```

---

## slackログインボタンを押すと、こうなる

---

<img width="868" alt="2019-01-19 16 36 23" src="https://user-images.githubusercontent.com/26683960/51423785-6d440080-1c08-11e9-8b02-50b5bbb780c4.png">

---

---
# 5. ログインが許可された後の処理を書く

- getパラメータにcodeがついてくる
- https://api.slack.com/methods/oauth.access
- セッションに突っ込む

---

# おしまい
