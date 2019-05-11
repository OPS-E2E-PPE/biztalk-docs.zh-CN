---
title: V2 中的 REF_I12。XML 2.3.1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF_I12 schema
ms.assetid: de30b128-3c70-41ea-849f-16f4c6d55430
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40a083c0c0e781379857dc639ccf917a214426ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291583"
---
# <a name="refi12-in-v2xml-231"></a><span data-ttu-id="14b25-102">V2 中的 REF_I12。XML 2.3.1</span><span class="sxs-lookup"><span data-stu-id="14b25-102">REF_I12 in V2.XML 2.3.1</span></span>
<span data-ttu-id="14b25-103">您必须手动更改 V2 中的 REF_I12 架构中的以下代码。XML 2.3.1 运行 Update2XMLSchema 工具后：</span><span class="sxs-lookup"><span data-stu-id="14b25-103">You must manually change the following code in the REF_I12 schema in V2.XML 2.3.1 after running the Update2XMLSchema tool:</span></span>  
  
```  
<xsd:element ref="REF_I12.PATIENT_VISIT" minOccurs="0" maxOccurs="1" />  
<xsd:element ref="REF_I12.PATIENT_VISIT" minOccurs="0" maxOccurs="1" />  
```  
  
 <span data-ttu-id="14b25-104">必须与以下内容，替换上面的代码中，若要解决多义性问题引起的多个实例**REF**元素定义：</span><span class="sxs-lookup"><span data-stu-id="14b25-104">You must replace the above code with the following, in order to fix the ambiguity caused by multiple occurrences of the **REF** element definition:</span></span>  
  
```  
<xsd:element minOccurs="0" maxOccurs="2" ref="REF_I12.PATIENT_VISIT" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="14b25-105">请参阅</span><span class="sxs-lookup"><span data-stu-id="14b25-105">See Also</span></span>  
 <span data-ttu-id="14b25-106">[所需的手动更新](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) </span><span class="sxs-lookup"><span data-stu-id="14b25-106">[Required Manual Updates](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md) </span></span>  
 [<span data-ttu-id="14b25-107">实用工具</span><span class="sxs-lookup"><span data-stu-id="14b25-107">Utilities</span></span>](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)