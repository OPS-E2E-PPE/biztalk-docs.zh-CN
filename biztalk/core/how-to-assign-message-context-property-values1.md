---
title: 如何分配消息上下文属性 Values1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e76c62-3110-482c-8083-84d411e6f475
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39bb2a4c6520c1ff3a21889e7508bb2cf417b817
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247301"
---
# <a name="how-to-assign-message-context-property-values"></a>如何分配消息上下文属性值
若要从 BizTalk 业务流程管理 JD Edwards EnterpriseOne 适配器连接会话，必须在项目中添加对 Microsoft.BizTalk.Adapters.JDEProperties.dll 的引用。 此程序集都位于企业 Applications\bin %SystemDrive%\Program Files\Common Files\Microsoft BizTalk 适配器。  
  
 引用此属性架构后，则其他上下文属性都可以访问各种 BizTalk 开发工具，例如，消息赋值业务流程设计器中的形状。  
  
 若要访问上下文属性，你指定的博士 Edwards EnterpriseOne 命名空间中的可用的上下文属性之一。 若要读取从博士 Edwards EnterpriseOne 绑定到 Microsoft BizTalk 适配器的端口收到的消息的上下文属性，使用语法，消息 (JDE。属性），在表达式中。 属性的列表，请参阅博士 Edwards EnterpriseOne 适配器会话管理。  
  
 在 BizTalk 中，消息是不可改变的。  
  
### <a name="to-assign-context-property-value"></a>若要将分配上下文属性值  
  
1.  创建新的消息。  
  
2.  设置该消息内容，例如，通过分配现有的消息。  
  
3.  设置的属性。  
  
 若要将上下文属性分配给为博士 Edwards EnterpriseOne 绑定到 Microsoft BizTalk 适配器发送端口发往一条消息，请使用消息赋值运算符。 然后指定在博士 Edwards EnterpriseOne 命名空间中的可用的上下文属性之一。  
  
 语法是：`Message(JDE.Property) = value;`  
  
## <a name="see-also"></a>另请参阅  
 [使用消息上下文属性](../core/using-message-context-properties1.md)   
 [有关会话管理](../core/about-session-management2.md)   
 [教程： 使用适用于博士 Edwards EnterpriseOne BizTalk 适配器](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-enterpriseone.md)