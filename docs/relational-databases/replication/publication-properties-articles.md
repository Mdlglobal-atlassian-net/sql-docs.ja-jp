---
title: '[パブリケーションのプロパティ]、[アーティクル] | Microsoft Docs'
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.newpubwizard.pubproperties.articles.f1
ms.assetid: bdeea318-a153-44b8-9e51-9155f3bad18b
author: MashaMSFT
ms.author: mathoma
monikerRange: =azuresqldb-mi-current||>=sql-server-2016||=sqlallproducts-allversions
ms.openlocfilehash: ee2f59fbb4634cc11bedfa881b1afef071d6dd69
ms.sourcegitcommit: 58158eda0aa0d7f87f9d958ae349a14c0ba8a209
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2020
ms.locfileid: "76286594"
---
# <a name="publication-properties-articles"></a>[パブリケーションのプロパティ]、[アーティクル]
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]
  **[パブリケーションのプロパティ]** ダイアログ ボックスの **[アーティクル]** ページには、パブリケーションに含まれるアーティクルの情報が表示されるため、これを使用すると、既存のパブリケーションに対してアーティクルを追加したり削除したりできます。また、アーティクルのプロパティや列のフィルターを変更することができます。  
  
> [!NOTE]  
>  パブリケーションの作成後、プロパティの変更によっては新しいスナップショットが必要となります。 パブリケーションにサブスクリプションが含まれている場合、変更によっては、すべてのサブスクリプションを再初期化する必要もあります。 詳細については、「[Change Publication and Article Properties](../../relational-databases/replication/publish/change-publication-and-article-properties.md)」 (パブリケーションおよびアーティクルのプロパティの変更) と「[既存のパブリケーションでのアーティクルの追加および削除](../../relational-databases/replication/publish/add-articles-to-and-drop-articles-from-existing-publications.md)」を参照してください。  
  
 1 つまたは複数の他のデータベース オブジェクトに依存するデータベース オブジェクトをパブリッシュする場合、参照されているオブジェクトをすべてパブリッシュする必要があります。 たとえば、テーブルに依存しているビューをパブリッシュする場合は、そのテーブルもパブリッシュする必要があります。  
  
 パブリッシュできないオブジェクトの横には赤いアイコンが表示され、ウィザード ページの一番下の情報パネルに説明が表示されます。 パブリッシュできないオブジェクトは次のとおりです。  
  
-   暗号化されたオブジェクト。  
  
-   NULL 値が許可されている列を含むインデックス付きビュー。  
  
-   主キーを持たないテーブル。これは、トランザクション パブリケーションにパブリッシュできません。  
  
-   テーブルは、キュー更新サブスクリプションが有効なマージ パブリケーションおよびトランザクション パブリケーションの両方でパブリッシュすることはできません。 複数のパブリケーションでのアーティクルのパブリッシュの詳細については、「[データとデータベース オブジェクトのパブリッシュ](../../relational-databases/replication/publish/publish-data-and-database-objects.md)」の「複数のパブリケーションでのテーブルのパブリッシュ」を参照してください。  
  
## <a name="oracle-publishers"></a>Oracle パブリッシャー  
 Oracle パブリッシャーについては、他にも次のような注意点があります。  
  
-   Oracle からパブリッシュできるオブジェクトの一覧については、「 [Design Considerations and Limitations for Oracle Publishers](../../relational-databases/replication/non-sql/design-considerations-and-limitations-for-oracle-publishers.md)」を参照してください。 パブリッシュできないオブジェクトは表示されません。  
  
-   パブリッシュできるデータ型の一覧については、「 [Data Type Mapping for Oracle Publishers](../../relational-databases/replication/non-sql/data-type-mapping-for-oracle-publishers.md)」を参照してください。 パブリッシュできないデータ型の列は表示されません。  
  
## <a name="column-filters"></a>列フィルター  
 このページで列をフィルターするには、 **[パブリッシュするオブジェクト]** ペインでテーブルを展開し、必要な列のみを選択します (このウィザードの **[テーブル行のフィルター選択]** ページで行をフィルターできます)。 列のフィルターが役に立つのには、セキュリティ (機密データのレプリケートの防止) やパフォーマンス (大規模な BLOB 列のレプリケーションの回避など) を含む複数の理由があります。 フィルター処理できない列の種類の一覧を含む、列のフィルターの詳細については、「[パブリッシュされたデータのフィルター選択](../../relational-databases/replication/publish/filter-published-data.md)」を参照してください。  
  
## <a name="options"></a>オプション  
 **[パブリッシュするオブジェクト]** ペインでは、次のことを行うことができます。  
  
-   レプリケーションが可能なすべてのオブジェクトを表示する。  
  
-   オブジェクトの横にあるチェック ボックスをオンにして、アーティクルをパブリケーションに追加する。  
  
-   オブジェクトの横にあるチェック ボックスをオフにして、パブリケーションからアーティクルを削除する。 アーティクルの削除の詳細については、「[既存のパブリケーションでのアーティクルの追加および削除](../../relational-databases/replication/publish/add-articles-to-and-drop-articles-from-existing-publications.md)」を参照してください。  
  
-   オブジェクトの種類 ( **[テーブル]** など) の横にあるチェック ボックスをオンにして、特定の型 (テーブルなど) のオブジェクトすべてをパブリケーションに含める。  
  
-   テーブル ノードを展開してテーブル内の列を表示する。  
  
-   列の横にあるチェック ボックスをオフにしてテーブル列をパブリケーションからフィルターする、またはチェック ボックスをオンにしてパブリッシュされていない列を含める。  
  
-   ペイン内でオブジェクトを右クリックし、そのオブジェクトに対するコマンドのメニューを表示する。  
  
 **[アーティクルのプロパティ]**  
 **[アーティクルのプロパティ]** をクリックし、次のいずれかの操作を行います。  
  
-   **[反転表示された \<ObjectType> アーティクルのプロパティを設定]** をクリックし、 **[アーティクルのプロパティ - \<ObjectName>]** ダイアログ ボックスを表示します。このダイアログ ボックスで行われたプロパティの変更は、 **[アーティクル]** ページのオブジェクト ペインで反転表示されたオブジェクトだけに適用されます。  
  
-   **[すべての\<ObjectType> アーティクルのプロパティを設定]** をクリックし、 **[すべての \<ObjectType> アーティクルのプロパティ]** ダイアログ ボックスを表示します。このダイアログ ボックスで行われたプロパティの変更は、パブリケーションが選択されていないオブジェクトも含めた、 **[アーティクル]** ページのオブジェクト ペインにあるこの種類のすべてのオブジェクトに適用されます。  
  
    > [!NOTE]  
    >  **[すべての \<ObjectType&gt; アーティクルのプロパティ]** ダイアログ ボックスで行われたプロパティの変更は、 **[アーティクルのプロパティ - \<ObjectName&gt;]** ダイアログ ボックスで以前行われたすべての変更をオーバーライドします。 たとえば、あるオブジェクトの種類のすべてのアーティクルに対して複数の既定を設定し、かつそれぞれのオブジェクトに対してプロパティを設定する場合には、最初にすべてのアーティクルに対する既定を設定します。 次に、それぞれのオブジェクトに対してプロパティを設定します。  
  
 **[反転表示されたテーブルはダウンロードのみである]**  
 マージ レプリケーションのみです。 [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] 以降のバージョンのみです。 クライアント サブスクリプションを使用している場合、サブスクライバーでの変更を許可しないように指定するときに選択します。 ダウンロード専用アーティクルはサブスクライバーで更新されないため、追跡メタデータがサブスクライバーに送信されることはありません。 これによってサブスクライバーの記憶域が節約されると共に、特に低速なネットワーク接続ではパフォーマンスの向上にもつながります。 このオプションは、 **[アーティクルのプロパティ]** ダイアログ ボックスの **[同期の方向]** オプションの **[サブスクライバーへのダウンロードのみを実行し、サブスクライバーの変更を禁止する]** の値に対応します。 詳細については、「[ダウンロード専用アーティクルを使用したマージ レプリケーションのパフォーマンス最適化](../../relational-databases/replication/merge/optimize-merge-replication-performance-with-download-only-articles.md)」を参照してください。  
  
 **[チェック ボックスがオンのオブジェクトのみ一覧に表示する]**  
 オブジェクト ペインで選択されたアーティクルのみを表示する場合に、このチェック ボックスをオンにします。  
  
## <a name="see-also"></a>参照  
 [Create a Publication](../../relational-databases/replication/publish/create-a-publication.md)   
 [パブリケーション プロパティの表示および変更](../../relational-databases/replication/publish/view-and-modify-publication-properties.md)   
 [初期スナップショットの作成および適用](../../relational-databases/replication/create-and-apply-the-initial-snapshot.md)   
 [サブスクリプションの再初期化](../../relational-databases/replication/reinitialize-a-subscription.md)   
 [データとデータベース オブジェクトのパブリッシュ](../../relational-databases/replication/publish/publish-data-and-database-objects.md)  
  
  
