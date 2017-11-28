---
title: "消息在 BizTalk Server 中的上下文属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message context properties, accessing
- message context properties, BizTalk Server
ms.assetid: 163ac2cf-0e2d-4780-b398-baa825f92b00
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75e92e458ec6927ab8e1bc6082cd9a71ee3e4387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-context-properties-in-biztalk-server"></a><span data-ttu-id="a64f5-102">BizTalk Server 中的消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="a64f5-102">Message Context Properties in BizTalk Server</span></span>
<span data-ttu-id="a64f5-103">若要从 BizTalk Server 业务流程访问 TIBCO 企业消息系统消息描述符字段，必须添加对引用**Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll**到你的项目。</span><span class="sxs-lookup"><span data-stu-id="a64f5-103">To access TIBCO Enterprise Message System message descriptor fields from a BizTalk Server orchestration, you must add a reference to **Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll** to your project.</span></span> <span data-ttu-id="a64f5-104">此程序集位于 **\<TIBCO EMS_Adapter_installation_directory > \bin**。</span><span class="sxs-lookup"><span data-stu-id="a64f5-104">This assembly is located in **\<TIBCO EMS_Adapter_installation_directory>\bin**.</span></span> <span data-ttu-id="a64f5-105">在引用此 TIBCO EMS 属性架构之后，将可以使用各种 BizTalk Server 开发工具访问其他上下文属性（例如，业务流程设计器中的消息赋值形状）。</span><span class="sxs-lookup"><span data-stu-id="a64f5-105">After you reference this TIBCO EMS property schema, additional context properties can be accessed by various BizTalk Server development tools (for example, the message assignment shape in the orchestration designer).</span></span>  
  
## <a name="accessing-context-properties"></a><span data-ttu-id="a64f5-106">访问上下文属性</span><span class="sxs-lookup"><span data-stu-id="a64f5-106">Accessing Context Properties</span></span>  
 <span data-ttu-id="a64f5-107">若要访问上下文属性，需要在 TIBCO EMS 命名空间中指定一个可用上下文属性。</span><span class="sxs-lookup"><span data-stu-id="a64f5-107">To access a context property, you specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="a64f5-108">若要读取从绑定到 TIBCO EMS 的 BizTalk 适配器的端口接收的消息的上下文属性，可在表达式中使用下列语法：</span><span class="sxs-lookup"><span data-stu-id="a64f5-108">To read the context property of a message received from a port bound to BizTalk Adapter for TIBCO EMS, use the following syntax in an expression:</span></span>  
  
```  
Message(TibcoEMS.Property)  
```  
  
 <span data-ttu-id="a64f5-109">有关详细信息，请参阅[TIBCO 企业消息服务消息描述符属性](../core/tibco-enterprise-message-service-message-descriptor-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="a64f5-109">For more information, see [TIBCO Enterprise Message Service Message Descriptor Properties](../core/tibco-enterprise-message-service-message-descriptor-properties.md).</span></span>  
  
 <span data-ttu-id="a64f5-110">在 BizTalk Server 中，消息是不可改变的。</span><span class="sxs-lookup"><span data-stu-id="a64f5-110">In BizTalk Server, messages are immutable.</span></span> <span data-ttu-id="a64f5-111">因此，若要分配消息上下文属性值，可创建一个新消息、设置消息内容（可通过分配现有消息来实现）然后设置您需要的属性。</span><span class="sxs-lookup"><span data-stu-id="a64f5-111">Therefore, to assign a message context property value, you create a new message, set the message content (possibly by assigning an existing message), and then set the properties that you need.</span></span>  
  
 <span data-ttu-id="a64f5-112">对于以绑定到 TIBCO EMS 的 BizTalk 适配器的发送端口为目标的消息，若要将 TIBCO EMS 上下文属性分配给此类消息，请使用消息赋值运算符，并在 TIBCO EMS 命名空间中指定可用的上下文属性之一。</span><span class="sxs-lookup"><span data-stu-id="a64f5-112">To assign TIBCO EMS context properties to a message destined to a send port that is bound to BizTalk Adapter for TIBCO EMS, use the message assignment operator and specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="a64f5-113">语法如下：</span><span class="sxs-lookup"><span data-stu-id="a64f5-113">The syntax is as follows:</span></span>  
  
```  
Message(TibcoEMS.Property) = value;  
```  
  
## <a name="see-also"></a><span data-ttu-id="a64f5-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a64f5-114">See Also</span></span>  
 [<span data-ttu-id="a64f5-115">消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="a64f5-115">Message Context Properties</span></span>](../core/message-context-properties2.md)