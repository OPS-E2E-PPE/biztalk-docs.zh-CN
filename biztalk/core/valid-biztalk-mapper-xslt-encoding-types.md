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
ms.openlocfilehash: d611c6ace56d4d61c891c9c156bd7263edf4622b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243157"
---
# <a name="valid-biztalk-mapper-xslt-encoding-types"></a>有效的 BizTalk 映射器 XSLT 编码类型
BizTalk 映射器支持不同类型的可扩展样式表语言转换 (XSLT) 编码。 您使用**XSLT 编码**网格属性设置的 XSLT 编码您喜欢的类型。 以下列表显示了与关联的下拉列表中可用的编码格式**XSLT 编码**网格属性：  
  
- None  
  
- 阿拉伯语 (windows-1256)  
  
- 波罗的语 (windows-1257)  
  
- 中欧语 (windows-1250)  
  
- 简体中文 (GB18030)  
  
- 西里尔语 (windows-1251)  
  
- 希腊语 (windows-1253)  
  
- 希伯来语 (windows-1255)  
  
- 日语 (Shift_JIS)  
  
- 朝鲜语 (ks_c_5601-1987)）  
  
- Little Endian Unicode (utf-16)  
  
- 简体中文 (GBK)  
  
- 泰语 (windows-874)  
  
- 繁体中文 (Big5)  
  
- 土耳其语 (windows-1254)  
  
- UTF-8  
  
- 越南语 (windows-1258)  
  
- 西欧语言 (windows-1252)  
  
  如果未找到你想要使用此列表中的编码，则可以输入不同的编码值。 请确保提供因为 BizTalk 映射器不会测试该值无效的值。  
  
> [!NOTE]
>  **代码页**的属性**架构**节点映射中定义的架构的使用的编码格式。 若要配置**代码页**属性，BizTalk 编辑器中打开该架构，并指定的值**代码页**属性。  
  
## <a name="see-also"></a>请参阅  
 [映射](../core/maps.md)   
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)