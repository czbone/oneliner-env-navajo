# 1行で環境構築
サーバに`root`ログインし１行のコマンドを実行するだけでMagic3の動作環境構築できるスクリプトです。
Magic3のインストーラが起動できるところまでを一気に構築します。

Magic3運用に必要なソフトウェアがすべて1台のサーバに納まるようにパッケージ化されています。
環境構築は難しい、たいへん時間がかかるという問題を解決します。

## 対象OS
- CentOS 7, Ubuntu18

## ライセンス

[![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)](https://lbesson.mit-license.org/)

# 実行内容
ローカルにAnsibleをインストールし、Ansible GalaxyのPlaybookを基本に少しカスタマイズして環境構築しています。
次の特色があります。

- 最新のソフトウェア環境
- 日本語最適化

# 使い方
新規にOSをインストールしたサーバに`root`でログインし、構築したい環境のスクリプトを実行します。
完了後は一旦サーバを再起動してください。

## Webサーバ(LEMP)環境構築 (所要時間: 約10分)
Linux(L),Nginx(N),MariaDB(M),PHP(P)のLEMP環境を作成します。

### バージョン
- Nginx 1.14.2
- PHP 7.3
- MariaDB 5.5.60(CentOS),MySQL 5.7.24(Ubuntu)

```
$ curl https://raw.githubusercontent.com/czbone/oneliner-env-navajo/master/script/build_magic3.sh | bash
```

### 環境構築後の作業
環境構築後はMagic3のインストール作業が終わっていない状態です。  
WebブラウザでMagic3のインストーラを実行しインストールを完了させます。

IPアドレス等でドキュメントルートにアクセスします。
```
http://localhost
```

DBへの接続情報が必要になります。  
デフォルトで作成されているDBの情報は以下の通りです。

- DB名：testdb
- DBユーザ：testuser
- パスワード：test

# 検証環境
- Vagrant Box CentOS7「centos/7」, Ubuntu18「ubuntu/bionic64」
- さくらVPS 「CentOS7」(標準OS), 「Ubuntu18.04 amd64」(カスタムOS)
