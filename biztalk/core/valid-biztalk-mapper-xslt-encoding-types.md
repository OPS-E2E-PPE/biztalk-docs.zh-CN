---
title: "编码类型的有效 BizTalk 映射程序 XSLT |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grid properties
- Code Page property
- XSLT Encoding property [grid pages]
- Schema node
- XSLT, encoding types [BizTalk Mapper]
- BizTalk Mapper, XSLT encoding
ms.assetid: 922b46cb-7bc8-4267-bf52-e5f0262b8da1
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83e8b69de5c60a1701f0989f725d9225633d38ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="valid-biztalk-mapper-xslt-encoding-types"></a>编码类型的有效 BizTalk 映射程序 XSLT
BizTalk 映射器支持不同类型的可扩展样式表语言转换 (XSLT) 编码。 你使用**XSLT 编码**网格属性来设置 XSLT 编码您喜欢的类型。 以下列表显示与关联的下拉列表中可用的编码格式**XSLT 编码**网格属性：  
  
-   无  
  
-   阿拉伯语 (windows-1256)  
  
-   波罗的语 (windows-1257)  
  
-   中欧语 (windows-1250)  
  
-   简体中文 (GB18030)  
  
-   西里尔语 (windows-1251)  
  
-   希腊语 (windows-1253)  
  
-   希伯来语 (windows-1255)  
  
-   日语 (Shift_JIS)  
  
-   韩语 (ks_c_5601 1987)  
  
-   Little Endian Unicode (UTF-16)  
  
-   简体中文 (GBK)  
  
-   泰语 (windows-874)  
  
-   繁体中文 (Big5)  
  
-   土耳其语 (windows-1254)  
  
-   UTF-8  
  
-   越南语 (windows-1258)  
  
-   西欧语 (windows-1252)  
  
 如果在此列表中找不到要使用的编码，则可以输入其他编码值。 确保所提供的值是有效的，因为 BizTalk 映射器将不测试该值。  
  
> [!NOTE]
>  **代码页**属性**架构**节点在映射中定义的架构，你使用的编码格式。 若要配置**代码页**属性，打开 BizTalk 编辑器中的架构，然后指定的值**代码页**属性。  
  
## <a name="see-also"></a>另请参阅  
 [地图](../core/maps.md)   
 [创建使用 BizTalk 映射程序图](../core/creating-maps-using-biztalk-mapper.md)