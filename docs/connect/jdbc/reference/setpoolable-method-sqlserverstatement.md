---
title: setPoolable メソッド (SQLServerStatement) |Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: f0f798c8-cafb-4acc-b85d-2e0059c91d92
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 809e16fce7cac83b6ba09fcef676c8da920b0dc3
ms.sourcegitcommit: 61381ef939415fe019285def9450d7583df1fed0
ms.translationtype: MTE75
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2018
ms.locfileid: "47759680"
---
# <a name="setpoolable-method-sqlserverstatement"></a>setPoolable メソッド (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  ステートメントをプールすること、またはプールしないことを要求します。  
  
## <a name="syntax"></a>構文  
  
```  
  
public void setPoolable(boolean poolable) throws SQLException  
```  
  
#### <a name="parameters"></a>パラメーター  
 *プール*  
  
 **true** の場合、ステートメントをプールすることを要求します。 **false** の場合、ステートメントをプールしないことを要求します。  
  
## <a name="exceptions"></a>例外  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Remarks  
 *poolable* パラメーターに指定する値は、アプリケーションでステートメントをプールする必要があるかどうかをステートメント プールの実装に示すヒントです。 そのヒントを使用するかどうかは、ステートメント プール マネージャーによって決定されます。  
  
 ステートメントのプール値は、ドライバーによって実装される内部ステートメント キャッシュと、アプリケーション サーバーや他のアプリケーションによって実装される外部ステートメント キャッシュの両方に適用されます。  
  
 既定では、SQLServerStatement オブジェクトはプールの作成時にではありません。 SQLServerPreparedStatement や SQLServerCallableStatement オブジェクトは作成時にプールします。  
  
 このメソッドを閉じたステートメントで呼び出すと、[SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md) がスローされます。  
  
 [isPoolable](../../../connect/jdbc/reference/ispoolable-method-sqlserverstatement.md) は、オブジェクトをプールできるかどうかを示す値を返します。  
  
## <a name="see-also"></a>参照  
 [SQLServerStatement のメンバー](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement クラス](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
