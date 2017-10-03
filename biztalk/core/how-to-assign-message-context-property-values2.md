---
title: "如何分配消息上下文属性 Values2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 137f82ab-f301-465d-be78-a6e67971dd3b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f0e19a425a4842e3bfac150d1cac851e4686f17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-assign-message-context-property-values"></a>如何分配消息上下文属性值
若要从 BizTalk 业务流程管理 JD Edwards OneWorld 连接会话，必须在项目中添加对 Microsoft.BizTalk.Adapters.JDEProperties.dll 的引用。 此程序集都位于企业 Applications\bin %SystemDrive%\Program Files\Common Files\Microsoft BizTalk 适配器。  
  
 引用此属性架构后，则其他上下文属性都可以访问各种 BizTalk 开发工具，例如，消息赋值业务流程设计器中的形状。  
  
 若要访问上下文属性，需要在 JD Edwards OneWorld 命名空间中指定一个可用上下文属性。 若要读取从端口（该端口与用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器绑定）接收到的上下文属性，请在表达式中使用语法 Message(JDE.Property)。 有关属性列表，请参阅 JD Edwards OneWorld 会话管理。  
  
 在 BizTalk 中，消息是不可改变的。  
  
### <a name="to-assign-a-message-context-property-value"></a>若要将分配一个消息上下文属性值  
  
1.  创建新的消息。  
  
2.  设置该消息内容，例如，通过分配现有的消息。  
  
3.  设置的属性。  
  
 若要将上下文属性分配到将发送端口（该端口与用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器绑定）作为目标的消息，请使用消息赋值运算符。 然后指定 JD Edwards OneWorld 命名空间中的一个可用上下文属性。  
  
 语法是：`Message(JDE.Property) = value;`  
  
## <a name="see-also"></a>另请参阅  
 [使用消息上下文属性](../core/using-message-context-properties2.md)   
 [有关会话管理](../core/about-session-management1.md)   
 [教程： 使用适用于博士 Edwards OneWorld BizTalk 适配器](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)