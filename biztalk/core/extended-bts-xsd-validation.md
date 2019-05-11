---
title: 扩展 (BTS-XSD) 验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f225115d-8890-4149-8e46-d1bc8af17e62
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65f102e1d5a182b729af164a83efa8f20be49ba7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345923"
---
# <a name="extended-bts-xsd-validation"></a>扩展 (BTS-XSD) 验证
EDI 接收管道和 EDI 发送管道执行扩展的验证，仅当已使用其数据类型不是 EDI 数据类型的元素自定义架构。 不会通过 EDI 验证，以便将受扩展验证来验证这些添加的元素。 扩展验证使用`System.Xml.XmlValidatingReader`并且包括可以在标准 XSD 中定义的所有检查。  
  
 配置扩展的验证到或从参与方的所有消息。 为此，选择**扩展验证**中的复选框**验证**页 (在**事务集设置**对于 X12 或 EDIFACT 的部分)，请在在单向协议选项卡**协议属性**对话框。 您可以启用扩展验证而不启用 EDI 验证，反之亦然。  
  
 扩展的验证包括以下检查：  
  
-   数据元素要求和允许的重复  
  
-   枚举  
  
-   数据元素长度验证 （最小/最大）。  
  
> [!IMPORTANT]
>  不支持在 EDI 发送端的批处理消息的扩展的验证。  
  
## <a name="see-also"></a>请参阅  
 [EDI 消息验证](../core/edi-message-validation.md)