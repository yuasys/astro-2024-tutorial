---
# 📌各項目はnullは禁止されています
layout: ../../layouts/MarkdownPostLayout.astro
title: Docker Desktop for MacからOrbStackへの移行手順
author: 湯浅信彦
description: Docker Desktop for MacからOrbStackへの移行手順について説明します。
image: 
  url: 
  alt: 
pubDate: 2025-01-29
tags: ["OrbStack", "Docker"]
---
※この記事は、生成AI Gemineに手伝ってもらいました

Docker Desktop for MacからOrbStackへの移行をご検討いただきありがとうございます。以下に、移行の手順を詳しくご説明します。

### **1\. Docker Desktop for Macのアンインストール**

* **アプリケーションフォルダから削除:** Docker Desktop for Macのアプリケーションをアプリケーションフォルダからゴミ箱に移動し、ゴミ箱を空にします。  
* **関連ファイルの削除:** Docker Desktop for Macの設定ファイルやキャッシュファイルも削除することをおすすめします。これらのファイルは、通常、ユーザーのホームディレクトリの隠しファイルとして保存されています。ターミナルで以下のコマンドを実行することで、関連ファイルを削除できます。

| rm \-rf \~/.docker |
| :---- |

**注意:** 上記のコマンドを実行すると、Dockerに関するすべての設定がリセットされます。

### **2\. OrbStackのインストール**

* **Homebrewによるインストール (推奨):** Homebrewがインストールされている場合は、以下のコマンドでOrbStackをインストールできます。

| brew install orbstack |
| :---- |

* **手動インストール:** Homebrewを使用していない場合は、OrbStackの公式サイトからインストーラーをダウンロードして、指示に従ってインストールしてください。

### **3\. OrbStackの起動と初期設定**

* **ターミナルで起動:** ターミナルで以下のコマンドを実行してOrbStackを起動します。

| orbstack start |
| :---- |

* **初期設定:** 初めてOrbStackを起動すると、初期設定画面が表示されます。必要に応じて設定を行い、「Finish」をクリックします。

### **4\. Dockerイメージとコンテナの移行**

* **Dockerイメージ:** Dockerイメージは、Docker Hubなどのレジストリに保存されているため、OrbStackでもそのまま使用できます。  
* **Dockerコンテナ:** Dockerコンテナは、OrbStack上で新しく作成する必要があります。Docker Composeを使用している場合は、Composeファイルを修正してOrbStackで実行できるようにする必要があります。

### **5\. 確認とトラブルシューティング**

* **Dockerコマンドの使用:** ターミナルで通常のDockerコマンドを使用できます。

| docker run hello-world |
| :---- |

* **トラブルシューティング:** 問題が発生した場合は、OrbStackの公式ドキュメントやコミュニティフォーラムを参照してください。

### **その他**

* **OrbStackの主な特徴:**  
  * 高速かつ軽量  
  * Docker Desktopとの高い互換性  
  * Linux仮想マシンも実行可能  
* **注意点:**  
  * OrbStackはベータ版であり、機能が今後変更される可能性があります。  
  * 無料版と有料版があります。

### **まとめ**

上記の手順に従って、Docker Desktop for MacからOrbStackへの移行が完了します。OrbStackは、Docker Desktopよりも高速かつ軽量なため、より快適な開発環境を構築できるでしょう。

**さらに詳しい情報が必要な場合は、お気軽にご質問ください。**

**参考:**

* OrbStack公式サイト: [https://orbstack.dev/](https://orbstack.dev/)  
* OrbStackドキュメント: [https://docs.orbstack.dev/](https://docs.orbstack.dev/)