---
title: sysmail_sentitems (TRANSACT-SQL) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysmail_sentitems_TSQL
- sysmail_sentitems
dev_langs:
- TSQL
helpviewer_keywords:
- sysmail_sentitems database mail view
ms.assetid: 16eb2a44-cebb-4cec-93ac-e2498c39989f
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 57fee409bbaa286f052c2fa11e15a956fcd7d540
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47699230"
---
# <a name="sysmailsentitems-transact-sql"></a>sysmail_sentitems (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  データベース メールから送信されたメッセージごとに 1 行のデータを格納します。 使用**sysmail_sentitems**正常に送信されたメッセージを表示したい場合。  
  
 データベース メールで処理されたすべてのメッセージを表示する[sysmail_allitems &#40;TRANSACT-SQL&#41;](../../relational-databases/system-catalog-views/sysmail-allitems-transact-sql.md)します。 状態が失敗したメッセージのみを表示する[sysmail_faileditems &#40;TRANSACT-SQL&#41;](../../relational-databases/system-catalog-views/sysmail-faileditems-transact-sql.md)します。 未送信ののみを参照してください。 または、メッセージの再試行を使用する[sysmail_unsentitems &#40;TRANSACT-SQL&#41;](../../relational-databases/system-catalog-views/sysmail-unsentitems-transact-sql.md)します。 電子メールの添付ファイルを表示する[sysmail_mailattachments &#40;TRANSACT-SQL&#41;](../../relational-databases/system-catalog-views/sysmail-mailattachments-transact-sql.md)します。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**mailitem_id**|**int**|メール キュー内のメール アイテムの識別子。|  
|**profile_id**|**int**|メッセージを送信するために使用するプロファイルの識別子。|  
|**recipients**|**varchar(max)**|メッセージ受信者の電子メール アドレス。|  
|**copy_recipients**|**varchar(max)**|CC としてメッセージのコピーを受け取る受信者の電子メール アドレス。|  
|**blind_copy_recipients**|**varchar(max)**|BCC としてメッセージのコピーを受け取る受信者の電子メール アドレス。この受信者の名前は、メッセージ ヘッダーには表示されません。|  
|**subject**|**nvarchar(510)**|メッセージの件名。|  
|**body**|**varchar(max)**|メッセージの本文。|  
|**body_format**|**varchar(20)**|メッセージの本文の書式。 指定できる値は**テキスト**と**HTML**します。|  
|**importance**|**varchar(6)**|**重要度**メッセージのパラメーター。|  
|**sensitivity**|**varchar(12)**|**感度**メッセージのパラメーター。|  
|**file_attachments**|**varchar(max)**|電子メール メッセージに添付されたファイル名の、セミコロン区切りの一覧。|  
|**attachment_encoding**|**varchar(20)**|添付ファイルの種類。|  
|**query**|**varchar(max)**|メール プログラムによって実行されたクエリ。|  
|**execute_query_database**|**sysname**|メール プログラムによってクエリが実行されたデータベース コンテキスト。|  
|**attach_query_result_as_file**|**bit**|値が 0 の場合、クエリの結果が電子メール メッセージ本文内に取り込まれ、本文内容の後に追加されていることを示します。 値が 1 の場合、結果が添付ファイルとして返されたことを示します。|  
|**query_result_header**|**bit**|値が 1 の場合、クエリの結果に列のヘッダーが含まれていることを示します。 値が 0 の場合、クエリの結果に列のヘッダーが含まれていないことを示します。|  
|**query_result_width**|**int**|**Query_result_width**メッセージのパラメーター。|  
|**query_result_separator**|**char(1)**|クエリの出力で列の区切りに使用された文字。|  
|**exclude_query_output**|**bit**|**Exclude_query_output**メッセージのパラメーター。 詳細については、次を参照してください。 [sp_send_dbmail &#40;TRANSACT-SQL&#41;](../../relational-databases/system-stored-procedures/sp-send-dbmail-transact-sql.md)します。|  
|**append_query_error**|**bit**|**Append_query_error**メッセージのパラメーター。 0 は、クエリにエラーがあった場合、データベース メールで電子メール メッセージが送信されないことを示します。|  
|**send_request_date**|**datetime**|メッセージがメール キューに挿入された日時。|  
|**send_request_user**|**sysname**|メッセージを送信したユーザー。 これはメッセージの [差出人] フィールドに表示されるユーザーではなく、データベース メール プロシージャのユーザー コンテキストです。|  
|**sent_account_id**|**int**|メッセージの送信に使用されたデータベース メール アカウントの識別子。|  
|**sent_status**|**varchar(8)**|メールの状態。 常に**送信**この表示されます。|  
|**sent_date**|**datetime**|メッセージが送信された日時。|  
|**last_mod_date**|**datetime**|行が最後に変更された日時。|  
|**last_mod_user**|**sysname**|行を最後に変更したユーザー。|  
  
## <a name="remarks"></a>コメント  
 データベース メールのトラブルシューティングを行うとき、このビューでは送信が成功したメッセージの属性を確認できるので、問題の性質を特定するのに役立ちます。 データベース メールでは、SMTP メール サーバーへの送信が成功したメッセージが送信済みとしてマークされます。 通常、電子メールは数分のうちに相手側に届きますが、SMTP サーバーの問題が原因で遅れることもあります。 データベース メールでは、メッセージが SMTP メール サーバーで受信されたときに送信済みとしてマークされ、 受信者の電子メール アドレスに配信できないなど、SMTP メール サーバーで発生する電子メール エラーは、データベース メールには返されません。 したがって、エラーが発生した電子メールは、相手側に届かなくても送信済みとして記録されます。 この種のエラーは、SMTP サーバー側で解決を試みてください。 SMTP メール サーバーから、データベース メール アカウントの返信用電子メール アドレスに、メッセージを配信できなかったを示す通知が送信される場合があります。  
  
## <a name="permissions"></a>アクセス許可  
 与えられる**sysadmin**固定サーバー ロールと**databasemailuserrole**データベース ロール。 メンバーによって実行されると、 **sysadmin**固定サーバー ロールに、このビューにはすべてのメッセージを送信します。 その他のユーザーの場合は、自分が送信したメッセージだけを確認できます。  
  
## <a name="see-also"></a>参照  
 [データベース メール メッセージング オブジェクト](../../relational-databases/database-mail/database-mail-messaging-objects.md)  
  
  
