---
title: "扩展 (BTS XSD) 验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f225115d-8890-4149-8e46-d1bc8af17e62
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed147515b48a23c55e552710d6a76d6df981edd7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="extended-bts-xsd-validation"></a>扩展 (BTS-XSD) 验证
仅当在使用其数据类型不为 EDI 数据类型的元素对架构进行了自定义的情况下，EDI 接收管道和 EDI 发送管道才会执行扩展验证。 EDI 验证，以便将受扩展验证将不验证这些添加的元素。 扩展验证使用 `System.Xml.XmlValidatingReader` 并且包括可以在标准 XSD 中定义的所有检查。  
  
 可以为发送到参与方或从参与方接收的所有消息配置扩展验证。 这样做通过选择**扩展验证**中的复选框**验证**页 (下**事务设置设置**X12 或 EDIFACT 部分)，请在中的单向协议选项卡**协议属性**对话框。 可以在不启用 EDI 验证的情况下启用扩展验证，反之亦然。  
  
 扩展验证包括以下检查：  
  
-   数据元素要求和允许的重复  
  
-   枚举  
  
-   数据元素长度验证（最小/最大）。  
  
> [!IMPORTANT]
>  不支持对 EDI 发送端的批处理消息进行扩展式验证。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 消息验证](../core/edi-message-validation.md)