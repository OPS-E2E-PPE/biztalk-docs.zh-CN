---
title: BizTalk Server 消息上下文属性 （发送处理程序） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a065ba89-9fdb-47dc-9021-fb95cf347cdc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4396f3404b885d4b2069eae2b6e9be882401e664
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358149"
---
# <a name="biztalk-server-message-context-properties-send-handlers"></a>BizTalk Server 消息上下文属性 （发送处理程序）
除了消息负载中，一条消息包含的补充信息必须可从 BizTalk Server 业务流程在运行时访问。  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a>TIBCO RV 消息信息升级为消息上下文属性  
  
|数据标识|类型|路由|发送位置|  
|-------------------------|----------|--------------|-------------------|  
|发送主题|string|是|业务流程指定 TIBCO Rendezvous 发送主题。 默认值为 Null。 必需，除非在端口配置中指定了默认主题。|  
|答复主题|string|是|业务流程提供使用者的答复消息，相关时。 默认值为 Null。|  
  
## <a name="getting-a-tibco-reply"></a>获取 TIBCO 答复  
 **问：** 如何用于 TIBCO Rendezvous 的 BizTalk 适配器读取和处理业务流程中的答复主题，您可以将其用作发送主题响应？ 适配器如何作用到传入消息的消息上下文来自 Rendezvous？  
  
 **答案：** 答复主题在传入消息的上下文中填充和业务流程可以读取它。 如果业务流程最终可以生成答复，它可以使用该值来设置答复消息的发送主题。  
  
1. 在 BizTalk Server 项目中，将添加到 < 请 > \TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll 的引用。  
  
2. 在业务流程 （某处之间分发传入 Rendezvous 消息的接收形状和发送答复的发送形状），添加消息构造/赋值形状 （或表达式形状） 来执行一些操作如下例所示为您构造的答复：  
  
   ```  
   OutgoingMsg(Rendezvous.SendSubject) = IncomingMsg  
   (Rendezvous.ReplySubject);  
   ```  
   ## <a name="management-assembly"></a>管理程序集
   TIBCO Rendezvous 未提供元数据存储库，用于 TIBCO Rendezvous 管理程序集的 Microsoft BizTalk 适配器不提供浏览功能或架构生成。 因此，必须向 BizTalk Server 提供架构。 有关详细信息，请参阅[安装、 架构和限制](../core/installing-biztalk-adapter-for-tibco-rendezvous.md)。
  
   用于 TIBCO Rendezvous 的 BizTalk 适配器包括具有预定义的类型的架构。 生成一些特定的数据类型 （数组） 的消息时，适配器将使用这些类型。

  
## <a name="see-also"></a>请参阅  
 [用于 TIBCO Rendezvous 中的发送处理程序的数据类型映射](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md)   
 [创建 TIBCO Rendezvous 发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)