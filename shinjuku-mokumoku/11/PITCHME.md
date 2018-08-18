# Pythonで簡単なSlackAppを作る

Takesso([@TaKesso_tw](https://twitter.com/TaKesso_tw))

『やっていくぞ！』

---

## その前に...

---

# え、これ(GitPitch)
# すごくない...!?

---

### ~~Pythonで簡単なSlackAppを作る~~

# GitPitchのススメ

Takesso([@TaKesso_tw](https://twitter.com/TaKesso_tw))

『おススメしていくぞ！』

---

## GitPitchとは

<a href='https://gitpitch.com/'><img src='https://gitpitch.com/gpimg/logo.png' width=200/></a>

- **GitHubだけで高機能なスライドが作れるWebアプリケーション**
- https://gitpitch.com/
- [ググると最初に出てくる記事](https://paiza.hatenablog.com/entry/2017/06/22/GitHub%E3%81%A0%E3%81%91%E3%81%A7%E8%B6%85%E9%AB%98%E6%A9%9F%E8%83%BD%E3%81%AA%E3%82%B9%E3%83%A9%E3%82%A4%E3%83%89%E8%B3%87%E6%96%99%E3%81%8C%E4%BD%9C%E3%82%8C%E3%82%8B%E3%80%8CGitPitch%E3%80%8D%E3%81%AE)

---

## GitPitchとの出会い

---

### shinjuku mokumoku #10 
### [@threetreeslight](https://github.com/threetreeslight)さんが使っていた

---

## なんだろうこの気持ち...
## 運命かもしれない...

---

# 使ってみた

---

#### ①GitHubにrepository作る
#### ② `PITCHME.md` を作る
#### ③URLにアクセスする

# 以上！！

---

# お手軽かよ
# ...最高かよ...

---

## アクセスURLはこちら

```
https://gitpitch.com/GitHubのユーザー名/リポジトリ名
```

---

## ブランチやディレクトリを指定することもできます

```
https://gitpitch.com/GitHubのユーザー名/リポジトリ名/ブランチ名?p=ディレクトリPath
```

---

## 設定のカスタマイズもできます

- (まだやってないからよく分からない)
- `PITCHME.yaml` を作るらしい

---

# ぜひ使ってみてください！

---
(本題)
# Pythonで簡単なSlackAppを作る

Takesso([@TaKesso_tw](https://twitter.com/TaKesso_tw))

『(GitPitchでお腹いっぱい感はあるけど)やっていくぞ！』

---

## 実現したいことのイメージ
#### [自作の　WebApp] <-> [SlackApp] <-> [SlackWorkspace]

---

## 左から右
- 自作のWebApp内での操作をトリガーとして、
- SlackAppを経由して
- SlackWorkspaceにリクエストを投げる

---

## 右から左
- SlackWorkspace内での操作をトリガーにして、
- SlackAppを経由して
- 自作のWebAppにリクエストを投げる

---

## 今回やりたいこと
- Workspaceにインストールする形のSlackAppを作る
- 特定のチャンネルに通知を送ることができる
- いくつかのWorkspaceで動作検証する

---

## Google先生でブログ探しタイム
- [SlackAppの作り方について](https://qiita.com/yuukiw00w/items/94e4495fc593cfbda45c) #Qiita
- [BotkitでのSlackアプリ開発方法とデプロイ方法](https://seri.hatenablog.com/entry/2018/01/14/022251) #はてなブログ
- **なんかイマイチしっくりこないな〜**
- その後のググりながらいろんな記事を眺める
- 全然関係ない面白そうな記事とか読んじゃう
- **お腹減ったな。え、もう14時...！？**
- 『結局公式のドキュメント見るのが一番ええやろ』 14:12
- 一旦サクッとお昼に行く

## 公式ドキュメント読む
- https://api.slack.com/bot-users 
