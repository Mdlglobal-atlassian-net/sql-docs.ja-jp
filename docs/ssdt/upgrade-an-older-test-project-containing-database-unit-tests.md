---
title: データベース単体テストを含む以前のテスト プロジェクトをアップグレードする
ms.prod: sql
ms.technology: ssdt
ms.topic: conceptual
ms.assetid: 42782ff3-e8cf-4c9d-8dac-a95b236edfc4
author: markingmyname
ms.author: maghan
manager: jroth
ms.reviewer: “”
ms.custom: seo-lt-2019
ms.date: 02/09/2017
ms.openlocfilehash: 146d52de5abbd868d80e848636213cf273c468ef
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2020
ms.locfileid: "75256302"
---
# <a name="upgrade-an-older-test-project-containing-database-unit-tests"></a>データベース単体テストを含む以前のテスト プロジェクトをアップグレードする

Visual Studio 2010 で作成され、データベース単体テストを含んでいる以前のテスト プロジェクトをアップグレードすると、新しい SQL Server Data Tools データベース単体テストのランタイムとツールを使用できます。 以前のプロジェクトをアップグレードしたら、SQL Server 単体テストをプロジェクトに追加できます (詳細については、「[SQL Server の単体テストの作成と定義](../ssdt/creating-and-defining-sql-server-unit-tests.md)」を参照してください)。  
  
> [!TIP]  
> Visual Studio 2010 を使用している場合は、SQL Server 単体テストをテスト プロジェクトに追加した後、以前のデータベース単体テスト テンプレートを使用して単体テストを追加しないでください。 追加した場合は、再度プロジェクトを変換しないと、テストが正常に実行されなくなります。  
  
Visual Studio 2010 より前のリリースで作成されたテスト データベース プロジェクトがある場合は、「[方法: 以前のリリースの Visual Studio からデータベース単体テストをアップグレードする](https://msdn.microsoft.com/library/dd193412(VS.100).aspx)」の情報を利用して、データベース プロジェクトを Visual Studio 2010 にアップグレードしてから SQL Server Data Tools にアップグレードできます。  
  
### <a name="initiating-an-upgrade"></a>アップグレードの開始  
  
-   テスト プロジェクトのコンテキスト メニューからプロジェクトのアップグレードを開始できます。  
  
    SQL Server Data Tools では、テスト プロジェクトのアップグレードを開始できるダイアログ ボックスが表示される場合があります。  
  
-   プロジェクトをアップグレードすると、以前のデータベース テスト フレームワークへのアセンブリ参照が削除され、新しいフレームワークへの参照と、アダプター アセンブリが追加されます。 また、app.config ファイルも更新されます。  
  
    > [!NOTE]  
    > テスト プロジェクトに DatabaseSetup コード ファイルと SQLDatabaseSetup コード ファイルの両方がある場合は、プロジェクトを SQL Server Data Tools にアップグレードすると、ビルドから DatabaseSetup ファイルが除外されます。 DatabaseSetup ファイルは、ビルドから除外された場合に削除できます。  
  
-   変換後、以前のテンプレートで作成された既存のデータベース単体テストは、アダプター アセンブリの新しい型を使用して新しいフレームワークにアクセスします。 アダプター アセンブリを使用するということは、アップグレード プロシージャではテスト スクリプトとコードが変更されていないことを意味します。 プロジェクトに SQL Server 単体テストを追加すると、新しいテストは、アダプターを介さず、直接新しいフレームワークを参照します。 新しいテストとの一貫性を保持するために、新しいフレームワークを使用するよう既存のコードを手動で更新することもできますが、これは必須ではありません。  
  
## <a name="see-also"></a>参照  
[SQL Server の単体テストを使用したデータベース コードの検証](../ssdt/verifying-database-code-by-using-sql-server-unit-tests.md)  
  
