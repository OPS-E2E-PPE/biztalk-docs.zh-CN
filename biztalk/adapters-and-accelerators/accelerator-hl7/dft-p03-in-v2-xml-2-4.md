---
title: V2 中的 DFT_P03。XML 2.4 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DFT_P03 schema
ms.assetid: 6735685a-2aac-4481-87d1-202b2178aeb5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff7e35c52c38d5e9738b557118a3caf1d03344ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="dftp03-in-v2xml-24"></a><span data-ttu-id="31341-102">V2 中的 DFT_P03。XML 2.4</span><span class="sxs-lookup"><span data-stu-id="31341-102">DFT_P03 in V2.XML 2.4</span></span>
<span data-ttu-id="31341-103">你必须手动更改 V2 中的 DFT_P03 架构中的以下代码。XML 2.4 后运行 Update2XMLSchema 工具：</span><span class="sxs-lookup"><span data-stu-id="31341-103">You must manually change the following code in the DFT_P03 schema in V2.XML 2.4 after running the Update2XMLSchema tool:</span></span>  
  
```  
<xsd:element ref="ROL" minOccurs="0" maxOccurs="unbounded" />  
<xsd:element ref="PV1" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="PV2" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="ROL" minOccurs="0" maxOccurs="unbounded" />  
```  
  
 <span data-ttu-id="31341-104">你必须将上面的代码替换为以下，以便修复导致多个匹配项的多义性**角色**元素定义：</span><span class="sxs-lookup"><span data-stu-id="31341-104">You must replace the above code with the following, in order to fix the ambiguity caused by multiple occurrences of the **ROL** element definition:</span></span>  
  
```  
<xsd:element minOccurs="0" maxOccurs="unbounded" ref="ROL" />  
  <xsd:choice minOccurs="0" maxOccurs="1">  
    <xsd:sequence>  
      <xsd:element minOccurs="1" maxOccurs="1" ref="PV1" />  
      <xsd:element minOccurs="0" maxOccurs="1" ref="PV2" />  
      <xsd:element minOccurs="0" maxOccurs="unbounded" ref="ROL" />  
    </xsd:sequence>  
    <xsd:sequence>  
      <xsd:element minOccurs="1" maxOccurs="1" ref="PV2" />  
      <xsd:element minOccurs="0" maxOccurs="unbounded" ref="ROL" />  
    </xsd:sequence>  
  </xsd:choice>  
```  
  
## <a name="see-also"></a><span data-ttu-id="31341-105">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31341-105">See Also</span></span>  
 <span data-ttu-id="31341-106">[所需的手动更新](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) </span><span class="sxs-lookup"><span data-stu-id="31341-106">[Required Manual Updates](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) </span></span>  
 [<span data-ttu-id="31341-107">实用程序</span><span class="sxs-lookup"><span data-stu-id="31341-107">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)