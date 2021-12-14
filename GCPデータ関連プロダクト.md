# GCPにおけるデータ活用関連プロダクト

## データ管理

### Cloud Dataproc
よく聞くHadoopはクラウドサービス内に格納されている。
GCPでは、Dataprocに格納されている。
流れとしては、
Cloud Strage ⇒ Cloud Dataproc ⇒ Bigquery

#### クラウドに以降する強み
オンプレ環境では可用性を確保するために常に大きめの容量（オーバープロビジョニング）を確保しておく必要があるが、クラウドサービスを利用することで"必要な時に必要な分だけ"が可能になる。
よくある話「オンプレ環境で使用していたHadoopをGoogle Cloud（Dataproc）で管理したい。」

### Cloud SQL
Cloud SQLはRDBMSのフルマネージドサービスである。


### どんなデータをどんなサービスで管理するのかについては画像参照
![image](https://user-images.githubusercontent.com/86205382/145955705-62cc6c4e-6116-4e3d-ac7f-710f46aa64e2.png)

## Bigqueryアーキテクチャ
これが王道かつ完璧なアーキテクチャらしい
![image](https://user-images.githubusercontent.com/86205382/145955715-e45d1cd8-6058-4221-b0ac-dc4989a20580.png)

### Cloud Dataprep
GUIでBigqueryを使える便利サービス
GCPとは別料金

### Bigquery AutoML
Bigquery上でModelの作成が可能
数行で書けて簡単。だけでなく、上級者向けオプションとしてLn正則化やクロスバリデーションの設定なども可能

## データ変換からデータの可視化までをGCPで
よくあるアーキテクチャ画像
![image](https://user-images.githubusercontent.com/86205382/145955747-918d5b1f-abca-4b41-8d25-6096ee36634c.png)

### Pubsub
Pubsubには多様なデータが送られてくる。
その多様なデータを上手い具合に分割してくれるのがPubsub

### Dataflow
NoOpsのデータパイプラインを表現
（NoOps - サーバーレス、インフラを意識してなくても使えること）
サーバーレスのフルマネージド型データ処理
バッチ処理とストリーミング処理の統合＋オートスケーリング
Beamを使用したオープンソースのプログラミングモデル

### データポータル（Data Studio）
Dataflowで作成したデータをデータポータルにて可視化する。
GCPのBIツールで、最終アウトプットとなる。
共有・編集の権限設定がGoogleアカウントで可能
