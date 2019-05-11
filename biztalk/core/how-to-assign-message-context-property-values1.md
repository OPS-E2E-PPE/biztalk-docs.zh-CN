---
title: 如何分配消息上下文属性 Values1 |Microsoft Docs
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
ms.openlocfilehash: 8e66d88a2e12bb0e2672c04df06df711746c5efe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387194"
---
# <a name="how-to-assign-message-context-property-values"></a>如何分配消息上下文属性值
若要从 BizTalk 业务流程管理 JD Edwards EnterpriseOne 适配器连接会话，必须在项目中添加对 Microsoft.BizTalk.Adapters.JDEProperties.dll 的引用。 此程序集位于 %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin。  
  
 在引用此属性架构之后，其他上下文属性都可以访问各种 BizTalk 开发工具，例如，业务流程设计器中的消息赋值形状。  
  
 若要访问上下文属性，您指定的 JD Edwards EnterpriseOne 命名空间中可用的上下文属性之一。 若要读取从端口与用于 JD Edwards EnterpriseOne Microsoft BizTalk 适配器绑定接收的消息的上下文属性，使用的语法，消息 (JDE。属性），在表达式中。 有关属性的列表，请参阅 JD Edwards EnterpriseOne 适配器会话管理。  
  
 在 BizTalk 中，消息是不可变的。  
  
### <a name="to-assign-context-property-value"></a>若要将分配上下文属性值  
  
1. 创建新的消息。  
  
2. 设置消息内容，例如，通过分配现有的消息。  
  
3. 设置的属性。  
  
   若要将上下文属性分配到发往用于 JD Edwards EnterpriseOne 绑定到 Microsoft BizTalk 适配器的发送端口的消息，请使用消息赋值运算符。 然后指定 JD Edwards EnterpriseOne 命名空间中可用的上下文属性之一。  
  
   语法是： `Message(JDE.Property) = value;`  
  
## <a name="see-also"></a>请参阅  
 [使用消息上下文属性](../core/using-message-context-properties1.md)   
 [关于会话管理](../core/about-session-management2.md)   
 [教程：使用用于 JD Edwards EnterpriseOne 的 BizTalk 适配器](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-enterpriseone.md)