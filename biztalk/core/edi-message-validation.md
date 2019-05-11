---
title: EDI 消息验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71f34561-d280-48bb-b1dd-ce37b87c5023
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09ee189ccd827c72fd177d65eaa49461e2287538
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350351"
---
# <a name="edi-message-validation"></a>EDI 消息验证
EDI 数据作为带分隔符的文件传输 （不带自描述标签） 并因此编码规则强制执行严格的格式设置规则，以确保目标应用程序应能够成功地分析和使用进行下游处理的信息。  
  
 EDI 接收管道和 EDI 发送管道中 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 执行一系列验证。 始终执行一些;如果协议中启用属性，或者在架构中执行其他人。 有关如何配置验证的详细信息，请参阅[如何验证 EDI 交换是配置的](../core/how-validation-of-an-edi-interchange-is-configured.md)。  
  
 对 EDI 交换的验证涉及几种不同的验证，如以下主题中所述。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何配置对 EDI 交换的验证](../core/how-validation-of-an-edi-interchange-is-configured.md)  
  
-   [EDI 结构验证](../core/edi-structural-validation.md)  
  
-   [协议属性验证](../core/agreement-properties-validation.md)  
  
-   [EDI 类型（数据元素）验证](../core/edi-type-data-element-validation.md)  
  
-   [扩展 (BTS-XSD) 验证](../core/extended-bts-xsd-validation.md)  
  
-   [架构验证](../core/schema-validation2.md)  
  
-   [跨字段-段验证](../core/cross-field-segment-validation.md)