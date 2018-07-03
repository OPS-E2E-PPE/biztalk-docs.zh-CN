---
title: 如何分配消息上下文属性 Values2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137f82ab-f301-465d-be78-a6e67971dd3b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afb08895ba841ce2e99399ea9590b05394102472
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006382"
---
# <a name="how-to-assign-message-context-property-values"></a>如何分配消息上下文属性值
若要从 BizTalk 业务流程管理 JD Edwards OneWorld 连接会话，必须在项目中添加对 Microsoft.BizTalk.Adapters.JDEProperties.dll 的引用。 此程序集位于 %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin。  
  
 在引用此属性架构之后，其他上下文属性都可以访问各种 BizTalk 开发工具，例如，业务流程设计器中的消息赋值形状。  
  
 若要访问上下文属性，需要在 JD Edwards OneWorld 命名空间中指定一个可用上下文属性。 若要读取从端口（该端口与用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器绑定）接收到的上下文属性，请在表达式中使用语法 Message(JDE.Property)。 有关属性列表，请参阅 JD Edwards OneWorld 会话管理。  
  
 在 BizTalk 中，消息是不可改变的。  
  
### <a name="to-assign-a-message-context-property-value"></a>若要将分配消息上下文属性值  
  
1. 创建新的消息。  
  
2. 设置消息内容，例如，通过分配现有的消息。  
  
3. 设置的属性。  
  
   若要将上下文属性分配到将发送端口（该端口与用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器绑定）作为目标的消息，请使用消息赋值运算符。 然后指定 JD Edwards OneWorld 命名空间中的一个可用上下文属性。  
  
   语法是： `Message(JDE.Property) = value;`  
  
## <a name="see-also"></a>请参阅  
 [使用消息上下文属性](../core/using-message-context-properties2.md)   
 [关于会话管理](../core/about-session-management1.md)   
 [教程：使用适用于 JD Edwards OneWorld 的 BizTalk 适配器](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)