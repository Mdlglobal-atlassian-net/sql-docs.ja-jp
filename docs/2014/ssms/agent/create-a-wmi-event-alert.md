---
title: WMI イベント警告の作成 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI event alerts [SQL Server Management Studio]
ms.assetid: b8c46db6-408b-484e-98f0-a8af3e7ec763
author: stevestein
ms.author: sstein
manager: craigg
ms.openlocfilehash: 5af4472d80e74c9d2845e6397f815ffb1c27f4d8
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2020
ms.locfileid: "68211435"
---
# <a name="create-a-wmi-event-alert"></a>Create a WMI Event Alert
  このトピックでは、 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] で [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] または [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] を使用して、WMI Provider for Server Events によって監視されている特定の [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] イベントが発生したときに通知される [!INCLUDE[tsql](../../includes/tsql-md.md)]エージェントの警告を作成する方法について説明します。  
  
 WMI プロバイダーを使用したイベントの監視[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]の詳細については、「 [Wmi Provider for Server events の概念](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md)」を参照してください。 WMI イベント警告の通知を受信するために必要な権限の詳細については、「 [SQL Server エージェント サービスのアカウントの選択](select-an-account-for-the-sql-server-agent-service.md)」を参照してください。 WQL の詳細については、「 [WMI Provider for Server Events と WQL の使用](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md)」を参照してください。  
  
 **このトピックの内容**  
  
-   **作業を開始する準備:**  
  
     [制限事項と制約事項](#Restrictions)  
  
     [セキュリティ](#Security)  
  
-   **WMI イベント警告を作成する方法:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> はじめに  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> 制限事項と制約事項  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] は、警告システム全体を簡単に管理できるグラフィカルなツールです。警告の基本構成を設定するには、SQL Server Management Studio を使用することをお勧めします。  
  
-   **xp_logevent** で生成されたイベントは master データベースで発生します。 このため、 **xp_logevent** では、警告の **@database_name** が **'master'** または NULL になっていないと、警告が起動されません。  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] エージェントが実行されているコンピューター上の WMI 名前空間だけがサポートされます。  
  
###  <a name="security"></a><a name="Security"></a> セキュリティ  
  
####  <a name="permissions"></a><a name="Permissions"></a> Permissions  
 既定では、 **sp_add_alert** を実行できるのは、 **sysadmin**固定サーバー ロールのメンバーだけです。  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> SQL Server Management Studio の使用  
  
#### <a name="to-create-a-wmi-event-alert"></a>WMI イベント警告を作成するには  
  
1.  **オブジェクト エクスプローラー** で、プラス記号をクリックして、WMI イベントの警告を作成するサーバーを展開します。  
  
2.  プラス記号をクリックして **[SQL Server エージェント]** を展開します。  
  
3.  **[警告]** を右クリックし、 **[新しい警告]** をクリックします。  
  
4.  **[新しい警告]** ダイアログ ボックスで、 **[名前]** ボックスに新しい警告の名前を入力します。  
  
5.  **[有効化]** チェック ボックスをオンにして、実行する警告を有効にします。 既定では、 **[有効化]** チェック ボックスはオンになっています。  
  
6.  **[種類]** ボックスの一覧の **[WMI イベント警告]** をクリックします。  
  
7.  **[WMI イベント警告定義]** の **[名前空間]** ボックスで、この警告を発生させる WMI イベントを識別する WQL (WMI Query Language) ステートメントの WMI 名前空間を指定します。  
  
8.  **[クエリ]** ボックスで、警告が応答するイベントを識別する WQL ステートメントを指定します。  
  
9. **[OK]** をクリックします。  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> Transact-SQL の使用  
  
#### <a name="to-create-a-wmi-event-alert"></a>WMI イベント警告を作成するには  
  
1.  **オブジェクト エクスプローラー**で、 [!INCLUDE[ssDE](../../includes/ssde-md.md)]のインスタンスに接続します。  
  
2.  [標準] ツール バーの **[新しいクエリ]** をクリックします。  
  
3.  次の例をコピーしてクエリ ウィンドウに貼り付け、 **[実行]** をクリックします。  
  
    ```  
    -- creates a WMI event alert that retrieves all event properties for any ALTER_TABLE event that occurs on table AdventureWorks2012.Sales.SalesOrderDetail  
    -- This example assumes that the message 54001 already exists.  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_add_alert  
        @name = N'Test Alert 2',  
        @message_id = 54001  
        @notification_message = N'Error 54001 has occurred on the Sales.SalesOrderDetail table on the AdventureWorks2012 database. Please see the following information...',  
        @wmi_namespace = '\\.\root\Microsoft\SqlServer\ServerEvents\,  
        @wmi_query = N'SELECT * FROM ALTER_TABLE   
    WHERE DatabaseName = 'AdventureWorks2012' AND SchemaName = 'Sales'   
        AND ObjectType='Table' AND ObjectName = 'SalesOrderDetail'';  
    GO  
    ```  
  
 詳細については、「 [sp_add_alert &#40;transact-sql&#41;](/sql/relational-databases/system-stored-procedures/sp-add-alert-transact-sql)」を参照してください。  
  
  
