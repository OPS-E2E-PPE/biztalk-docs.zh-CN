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
ms.openlocfilehash: cfd3dca7c807ef48c82d46743e749e19a40001bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016296"
---
# <a name="biztalk-server-message-context-properties-send-handlers"></a>BizTalk Server 消息上下文属性 （发送处理程序）
除了消息负载之外，消息包含的补充信息必须在运行时从 BizTalk Server 业务流程访问。  
  
## <a name="tibco-rv-message-information-promoted-as-message-context-properties"></a>TIBCO RV 消息信息升级为消息上下文属性  
  
|数据标识|类型|可路由|发送位置|  
|-------------------------|----------|--------------|-------------------|  
|发送主题|string|是|指定 TIBCO Rendezvous 发送主题的业务流程。 默认值为 Null。 必填字段，除非在端口配置中指定了默认主题。|  
|答复主题|string|是|提供答复消息的主题的业务流程（相关时）。 默认值为 Null。|  
  
## <a name="getting-a-tibco-reply"></a>获取 TIBCO 答复  
 **问：** 原理的 BizTalk 适配器的 TIBCO Rendezvous 读取和处理业务流程中的答复主题，您可以将其用作发送主题响应？ 适配器如何获得来自 Rendezvous 的传入消息的消息上下文？  
  
 **答案是：** 答复主题在传入消息的上下文中填充和业务流程可以读取它。 如果业务流程最终可以生成答复，则可以使用该值来设置答复消息的发送主题。  
  
1. 在 BizTalk Server 项目中，请向 <install_directory>\TibcoRV\bin\Microsoft.BizTalk.Adapters.TibRV.Properties.dll 中添加引用。  
  
2. 在业务流程中（传输传入 Rendezvous 消息的“接收”形状和发送答复的“发送”形状之间的某个位置），添加消息构造/赋值形状（或表达式形状）以进行某些类似于下面您构造答复示例的操作。  
  
   ```  
   OutgoingMsg(Rendezvous.SendSubject) = IncomingMsg  
   (Rendezvous.ReplySubject);  
   ```  
   ## <a name="management-assembly"></a>管理程序集
   TIBCO Rendezvous 未提供元数据储存库，并且用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器管理程序集未提供浏览功能或架构生成。 因此，您必须向 BizTalk Server 提供架构。 有关详细信息，请参阅[安装、 架构和限制](../core/installing-biztalk-adapter-for-tibco-rendezvous.md)。
  
   用于 TIBCO Rendezvous 的 BizTalk 适配器包括具有预定义类型的架构。 为某些特定数据类型（数组）生成消息时，该适配器将使用这些类型。

  
## <a name="see-also"></a>请参阅  
 [用于 TIBCO Rendezvous 中的发送处理程序的数据类型映射](../core/data-type-mapping-for-send-handlers-in-tibco-rendezvous.md)   
 [创建 TIBCO Rendezvous 发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)