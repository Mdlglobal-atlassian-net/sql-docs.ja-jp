---
title: xml_schema_types (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.xml_schema_types_TSQL
- xml_schema_types_TSQL
- sys.xml_schema_types
- xml_schema_types
dev_langs:
- TSQL
helpviewer_keywords:
- sys.xml_schema_types catalog view
ms.assetid: 441ba49d-f778-4fa1-98c4-ced375a01a34
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 356e73e2b90d059117cadef436bcea27498c9871
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82824967"
---
# <a name="sysxml_schema_types-transact-sql"></a>xml_schema_types (Transact-sql)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  **T**の**symbol_space**型である XML スキーマコンポーネントごとに1行の値を返します。  
  
|列名|データ型|説明|  
|-----------------|---------------|-----------------|  
|**\<継承された列>**||[Xml_schema_components](../../relational-databases/system-catalog-views/sys-xml-schema-components-transact-sql.md)から列を継承します。|  
|**is_abstract**|**bit**|1 = 型は抽象型です。 この型の要素のすべてのインスタンスは、抽象型ではない派生型を示すために、 **xsi: type**を使用する必要があります。<br /><br /> 0 = 型は abstract ではありません  (既定値)。|  
|**allows_mixed_content**|**bit**|1 = 混合コンテンツは許可されます。<br /><br /> 0 = 混合コンテンツは許可されていません。 (既定値)。|  
|**is_extension_blocked**|**bit**|1 = **complexType**定義の block 属性または先祖> スキーマの**blockdefault**属性 \< が "extension" または "#all" に設定されている場合、型の拡張による置換はインスタンスでブロックされます。<br /><br /> 0 = 拡張による置き換えはブロックされません。|  
|**is_restriction_blocked**|**bit**|1 = **complexType**定義の block 属性、または先祖スキーマ> 要素情報項目の**blockdefault**属性 \< が "restriction" または "#all" に設定されている場合、型の制限付きの置換はインスタンスでブロックされます。<br /><br /> 0 = 制約による置き換えはブロックされません  (既定値)。|  
|**is_final_extension**|**bit**|1 = **complexType**定義の final 属性、または先祖スキーマ> 要素情報項目の**finaldefault**属性 \< が "extension" または "#all" に設定されている場合、型の拡張による派生はブロックされます。<br /><br /> 0 = 拡張は許可されます  (既定値)。|  
|**is_final_restriction**|**bit**|1 = simple または**complexType**定義の final 属性、または先祖スキーマ> 要素情報項目の**finaldefault**属性 \< が "restriction" または "#all" に設定されている場合、型の制約による派生はブロックされます。<br /><br /> 0 = 制約は許可されます  (既定値)。|  
|**is_final_list_member**|**bit**|1 = この単純型は、リスト項目の型として使用できません。<br /><br /> 0 = この型は複合型、またはリスト項目の型として使用できます  (既定値)。|  
|**is_final_union_member**|**bit**|1 = この単純型は、共用体型のメンバー型として使用することはできません。<br /><br /> 0 = この型は複合型です。 または、共用体メンバー型として使用することもできます。 (既定値)。|  
  
## <a name="permissions"></a>アクセス許可  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 詳細については、「 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [Transact-sql&#41;&#40;カタログビュー](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Xml スキーマ &#40;XML 型システム&#41; カタログビュー &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/xml-schemas-xml-type-system-catalog-views-transact-sql.md)  
  
  
