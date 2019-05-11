---
title: 使用 TIBCO EMS 消息上下文属性 |Microsoft Docs
description: 使用 BizTalk Server 业务流程中的 TIBCO Enterprise Message System 消息描述符字段
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 163ac2cf-0e2d-4780-b398-baa825f92b00
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c4c095969483905cf30403e4831e4f2df8296b7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394575"
---
# <a name="message-context-properties-in-tibco-ems"></a><span data-ttu-id="878bd-103">在 TIBCO EMS 的消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="878bd-103">Message Context Properties in TIBCO EMS</span></span>

## <a name="tibcoemspropertiesdll"></a><span data-ttu-id="878bd-104">TibcoEMSProperties.dll</span><span class="sxs-lookup"><span data-stu-id="878bd-104">TibcoEMSProperties.dll</span></span>
<span data-ttu-id="878bd-105">若要从 BizTalk Server 业务流程访问 TIBCO 企业消息系统消息描述符字段，必须添加对的引用**Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll**到你的项目。</span><span class="sxs-lookup"><span data-stu-id="878bd-105">To access TIBCO Enterprise Message System message descriptor fields from a BizTalk Server orchestration, you must add a reference to **Microsoft.BizTalk.Adapters.TibcoEMSProperties.dll** to your project.</span></span> <span data-ttu-id="878bd-106">此程序集位于 **\<TIBCO EMS_Adapter_installation_directory\>\bin**。</span><span class="sxs-lookup"><span data-stu-id="878bd-106">This assembly is located in **\<TIBCO EMS_Adapter_installation_directory\>\bin**.</span></span> <span data-ttu-id="878bd-107">在引用此 TIBCO EMS 属性架构之后，可以通过各种 BizTalk Server 开发工具 （例如，业务流程设计器中的消息赋值形状） 访问其他上下文属性。</span><span class="sxs-lookup"><span data-stu-id="878bd-107">After you reference this TIBCO EMS property schema, additional context properties can be accessed by various BizTalk Server development tools (for example, the message assignment shape in the orchestration designer).</span></span>  
  
## <a name="access-context-properties"></a><span data-ttu-id="878bd-108">访问上下文属性</span><span class="sxs-lookup"><span data-stu-id="878bd-108">Access context Properties</span></span>  
 <span data-ttu-id="878bd-109">若要访问上下文属性，指定一个可用上下文属性在 TIBCO EMS 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="878bd-109">To access a context property, you specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="878bd-110">若要读取从端口绑定到的 BizTalk 适配器 TIBCO EMS 接收的消息的上下文属性，请在表达式中使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="878bd-110">To read the context property of a message received from a port bound to BizTalk Adapter for TIBCO EMS, use the following syntax in an expression:</span></span>  
  
```  
Message(TibcoEMS.Property)  
```  
  
 <span data-ttu-id="878bd-111">有关详细信息，请参阅[TIBCO Enterprise Message Service 消息描述符属性](../core/tibco-enterprise-message-service-message-descriptor-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="878bd-111">For more information, see [TIBCO Enterprise Message Service Message Descriptor Properties](../core/tibco-enterprise-message-service-message-descriptor-properties.md).</span></span>  
  
 <span data-ttu-id="878bd-112">在 BizTalk Server 中，消息是不可变的。</span><span class="sxs-lookup"><span data-stu-id="878bd-112">In BizTalk Server, messages are immutable.</span></span> <span data-ttu-id="878bd-113">因此，若要将分配消息上下文属性值，请创建新的消息、 设置消息内容 （可通过分配现有的消息），然后设置所需的属性。</span><span class="sxs-lookup"><span data-stu-id="878bd-113">Therefore, to assign a message context property value, you create a new message, set the message content (possibly by assigning an existing message), and then set the properties that you need.</span></span>  
  
 <span data-ttu-id="878bd-114">若要将 TIBCO EMS 上下文属性分配到发往 TIBCO ems 绑定到的 BizTalk 适配器的发送端口的消息，请使用消息赋值运算符，并在 TIBCO EMS 命名空间中指定一个可用上下文属性。</span><span class="sxs-lookup"><span data-stu-id="878bd-114">To assign TIBCO EMS context properties to a message destined to a send port that is bound to BizTalk Adapter for TIBCO EMS, use the message assignment operator and specify one of the available context properties in the TIBCO EMS namespace.</span></span> <span data-ttu-id="878bd-115">语法如下：</span><span class="sxs-lookup"><span data-stu-id="878bd-115">The syntax is as follows:</span></span>  
  
```  
Message(TibcoEMS.Property) = value;  
```  
  
## <a name="next-steps"></a><span data-ttu-id="878bd-116">后续步骤</span><span class="sxs-lookup"><span data-stu-id="878bd-116">Next steps</span></span>
-   [<span data-ttu-id="878bd-117">TIBCO EMS 消息描述符属性和值</span><span class="sxs-lookup"><span data-stu-id="878bd-117">TIBCO EMS Message Descriptor properties & values</span></span>](../core/tibco-enterprise-message-service-message-descriptor-properties.md)  
  
-   [<span data-ttu-id="878bd-118">教程：使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="878bd-118">Tutorial: Use Message Context Properties</span></span>](../core/tutorial-using-message-context-properties.md)