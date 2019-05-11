---
title: 在发送端口上设置筛选器表达式 |Microsoft Docs
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
ms.openlocfilehash: ab5fcc0e4245599dfffb29f6f5690707df325c04
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291566"
---
# <a name="setting-filter-expressions-on-send-ports"></a>发送端口设置筛选器表达式
若要控制端口发送的内容在发送端口上筛选器表达式中设置上下文属性。 可以使用大量运算符，使你能够灵活中如何筛选该属性设置筛选器表达式 (等式或不等式，存在，大于、 大于或等于、 小于且小于或等于)。  
  
### <a name="to-set-the-filter-expression-on-a-send-port"></a>若要在发送端口上设置筛选器表达式  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk 应用程序1** （或另一个应用程序）。 单击**发送端口**。  
  
2.  右键单击你想要设置的筛选器表达式，，然后单击发送端口**属性**。  
  
3.  在控制台树中的发送端口属性对话框中，单击**筛选器**。  
  
4.  单击中的文本框**属性**列中，然后选择上下文属性从**属性**下拉列表。  
  
5.  单击**运算符**框中的行的属性，并从下拉列表中选择该属性的运算符。  
  
6.  单击**值**框的属性，行中，键入值表达式。  
  
7.  如果需要添加另一个子句的筛选器表达式，请单击**Group By**框中的属性行，然后选择**并**或**或**来确定之间的关系子句。  
  
8.  重复步骤 4 至 6 可添加另一个筛选器子句。  
  
9. 验证筛选器表达式是在底部窗格中正确**筛选器**窗格。  
  
10. 已添加所有筛选器子句，单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用上下文属性](../../adapters-and-accelerators/accelerator-hl7/using-context-properties.md)