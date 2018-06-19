---
title: 在发送端口上设置筛选器表达式 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, context properties
- filtering, send ports
- send ports, filtering
- context properties, send ports
- context properties, filtering
- filtering, context properties
ms.assetid: 48c7c83b-9464-4ed9-bd8d-cf5b75e16702
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b94497f4e1412f81c36df3195994aafa32ecc451
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206077"
---
# <a name="setting-filter-expressions-on-send-ports"></a>发送端口上设置筛选器表达式
您设置上下文属性筛选器表达式中发送端口来控制端口所发送的内容。 提供了灵活地如何筛选属性的运算符的数量，可以设置筛选器表达式 (存在的相等运算符或不等、，大于、 大于或等于、 小于且小于或等于)。  
  
### <a name="to-set-the-filter-expression-on-a-send-port"></a>若要在发送端口上设置筛选器表达式  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1** （或另一个应用程序）。 单击**发送端口**。  
  
2.  右键单击你想要设置的筛选器表达式，，然后单击发送端口**属性**。  
  
3.  在控制台树中的发送端口属性对话框中，单击**筛选器**。  
  
4.  单击中的文本框**属性**列，然后选择上下文属性**属性**下拉列表。  
  
5.  单击**运算符**框中的行的属性，并从下拉列表中选择该属性的运算符。  
  
6.  单击**值**框中，将该属性的行，然后键入值表达式。  
  
7.  如果你需要添加筛选器表达式的另一个子句，请单击**Group By**框中，将该属性的行，然后选择**和**或**或**以确定之间的关系子句。  
  
8.  重复步骤 4 到 6 以添加另一个筛选器子句。  
  
9. 验证是否正确在底部窗格中的筛选器表达式**筛选器**窗格。  
  
10. 在添加所有筛选子句后，单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用上下文属性](../../adapters-and-accelerators/accelerator-hl7/using-context-properties.md)