---
title: Curl を使用して、SQL Server 2019 CTP 2.1 での HDFS にデータを読み込む |Microsoft Docs
description: ''
author: rothja
ms.author: jroth
manager: craigg
ms.date: 11/06/2018
ms.topic: conceptual
ms.prod: sql
ms.openlocfilehash: a5f580ab39ef7338f424975d9667745131ee748f
ms.sourcegitcommit: cb73d60db8df15bf929ca17c1576cf1c4dca1780
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "51221628"
---
# <a name="use-curl-to-load-data-into-hdfs-on-sql-server-2019-ctp-21"></a>Curl を使用して、SQL Server 2019 CTP 2.1 での HDFS にデータを読み込む

この記事は、使用する方法を説明します**curl** SQL Server 2019 CTP 2.1 での HDFS にデータを読み込みます。

## <a name="obtain-the-service-external-ip"></a>サービスの外部 ip アドレスを取得します。

配置が完了したらとそのアクセスを通過 Knox、WebHDFS が開始されます。 Knox エンドポイントは、Kubernetes サービスを介して公開されます (現在のところ) と呼ばれる**サービス-セキュリティ-lb**します。CURL を使用して、必要になるファイルのアップロード/ダウンロードする必要があります WebHDFS の URL を作成する、**サービス-セキュリティ-lb**サービスの外部 IP アドレスとクラスターの名前。 このコマンドを実行して、サービス-セキュリティ-lb サービスの外部 IP アドレスを取得できます。

```bash
kubectl get service service-security-lb -n <cluster name> -o json | jq -r .status.loadBalancer.ingress[0].ip
```

> [!NOTE]
> `<cluster name>` Mssqlctl を実行したときに指定したクラスターの名前は、クラスターを作成する。 ここでは`<cluster name>`します。

## <a name="construct-the-url-to-access-webhdfs"></a>WebHDFS へのアクセスに URL を構築します。

ここで、次のように、WebHDFS へのアクセスに URL を構築できます。

`https://<service-security-lb service external IP address>:30433/gateway/default/webhdfs/v1/`

以下に例を示します。

`https://13.66.190.205:30443/gateway/default/webhdfs/v1/`

## <a name="list-a-file"></a>ファイルを一覧表示します。

一覧のファイルに**hdfs:///airlinedata**次の curl コマンドを使用します。

```bash
curl -i -k -u root:root-password -X GET 'https://<service-security-lb IP external address>:30443/gateway/default/webhdfs/v1/airlinedata/?op=liststatus'
```

## <a name="put-a-local-file-into-hdfs"></a>ローカル ファイルを HDFS に入れる

新しいファイルを配置する**test.csv** airlinedata ディレクトリをローカル ディレクトリから (**Content-type**パラメーターが必要です)、次の curl コマンドを使用します。

```bash
curl -i -L -k -u root:root-password -X PUT 'https://<service-security-lb IP external address>:30443/gateway/default/webhdfs/v1/airlinedata/test.csv?op=create' -H 'Content-Type: application/octet-stream' -T 'test.csv'
```

## <a name="create-a-directory"></a>ディレクトリを作成します。

ディレクトリを作成する**テスト**`hdfs:///`次のコマンドを使用します。

```bash
curl -i -L -k -u root:root-password -X PUT 'https://<service-security-lb IP external address>:30443/gateway/default/webhdfs/v1/test?op=MKDIRS'
```

## <a name="next-steps"></a>次の手順

SQL Server のビッグ データ クラスターの詳細については、次を参照してください。[ビッグ データの SQL Server クラスターとは何ですか?](big-data-cluster-overview.md)します。