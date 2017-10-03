---
title: "EDI 消息验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71f34561-d280-48bb-b1dd-ce37b87c5023
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21439969bc8e23b5b9901077c14a98128aa64c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-message-validation"></a>EDI 消息验证
EDI 数据是作为带分隔符的文件（没有自描述标签）进行传输的，因此编码规则会施加严格的格式规则以确保目标应用程序可以成功地分析和使用信息以进行下游处理。  
  
 EDI 接收管道和 EDI 发送管道中 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 执行一系列的验证。 一些始终执行;如果启用协议中的属性或架构中执行其他人。 有关如何配置验证的详细信息，请参阅[如何验证 EDI 交换是配置的](../core/how-validation-of-an-edi-interchange-is-configured.md)。  
  
 如以下主题中所述，EDI 交换的验证工作涉及几种不同类型的验证。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何配置 EDI 交换的验证](../core/how-validation-of-an-edi-interchange-is-configured.md)  
  
-   [EDI 结构验证](../core/edi-structural-validation.md)  
  
-   [协议属性验证](../core/agreement-properties-validation.md)  
  
-   [EDI 类型 （数据元素） 验证](../core/edi-type-data-element-validation.md)  
  
-   [扩展 (BTS-XSD) 验证](../core/extended-bts-xsd-validation.md)  
  
-   [架构验证](../core/schema-validation2.md)  
  
-   [交叉字段段验证](../core/cross-field-segment-validation.md)