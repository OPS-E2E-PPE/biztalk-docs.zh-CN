---
title: 有效的 BizTalk 映射器 XSLT 编码类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- grid properties
- Code Page property
- XSLT Encoding property [grid pages]
- Schema node
- XSLT, encoding types [BizTalk Mapper]
- BizTalk Mapper, XSLT encoding
ms.assetid: 922b46cb-7bc8-4267-bf52-e5f0262b8da1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 874e30f6d1cb56880dc9b15cce9c815305430871
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012334"
---
# <a name="valid-biztalk-mapper-xslt-encoding-types"></a>有效的 BizTalk 映射器 XSLT 编码类型
BizTalk 映射器支持不同类型的可扩展样式表语言转换 (XSLT) 编码。 您使用**XSLT 编码**网格属性设置的 XSLT 编码您喜欢的类型。 以下列表显示了与关联的下拉列表中可用的编码格式**XSLT 编码**网格属性：  
  
- InclusionThresholdSetting  
  
- 阿拉伯语 (windows-1256)  
  
- 波罗的语 (windows-1257)  
  
- 中欧语 (windows-1250)  
  
- 简体中文 (GB18030)  
  
- 西里尔语 (windows-1251)  
  
- 希腊语 (windows-1253)  
  
- 希伯来语 (windows-1255)  
  
- 日语 (Shift_JIS)  
  
- 韩语 (ks_c_5601 1987)  
  
- Little Endian Unicode (UTF-16)  
  
- 简体中文 (GBK)  
  
- 泰语 (windows-874)  
  
- 繁体中文 (Big5)  
  
- 土耳其语 (windows-1254)  
  
- UTF-8  
  
- 越南语 (windows-1258)  
  
- 西欧语 (windows-1252)  
  
  如果在此列表中找不到要使用的编码，则可以输入其他编码值。 确保所提供的值是有效的，因为 BizTalk 映射器将不测试该值。  
  
> [!NOTE]
>  **代码页**的属性**架构**节点映射中定义的架构的使用的编码格式。 若要配置**代码页**属性，BizTalk 编辑器中打开该架构，并指定的值**代码页**属性。  
  
## <a name="see-also"></a>请参阅  
 [映射](../core/maps.md)   
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)