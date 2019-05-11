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
ms.openlocfilehash: 083fa3e8d6474e0f369cc1c66210ac39f4e1d56e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342687"
---
# <a name="how-to-assign-message-context-property-values"></a><span data-ttu-id="ae1fb-102">如何分配消息上下文属性值</span><span class="sxs-lookup"><span data-stu-id="ae1fb-102">How to Assign Message Context Property Values</span></span>
<span data-ttu-id="ae1fb-103">若要从 BizTalk 业务流程管理 JD Edwards OneWorld 连接会话，必须在项目中添加对 Microsoft.BizTalk.Adapters.JDEProperties.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="ae1fb-103">To manage the JD Edwards OneWorld connection session from a BizTalk orchestration, you must add the reference to Microsoft.BizTalk.Adapters.JDEProperties.dll in your project.</span></span> <span data-ttu-id="ae1fb-104">此程序集位于 %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin。</span><span class="sxs-lookup"><span data-stu-id="ae1fb-104">This assembly is located in %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
 <span data-ttu-id="ae1fb-105">在引用此属性架构之后，其他上下文属性都可以访问各种 BizTalk 开发工具，例如，业务流程设计器中的消息赋值形状。</span><span class="sxs-lookup"><span data-stu-id="ae1fb-105">After you reference this property schema, additional context properties are accessible to various BizTalk development tools, for example, the Message Assignment shape within the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="ae1fb-106">若要访问上下文属性，您指定的 JD Edwards OneWorld 命名空间中可用的上下文属性之一。</span><span class="sxs-lookup"><span data-stu-id="ae1fb-106">To access a context property, you specify one of the available context properties within the JD Edwards OneWorld namespace.</span></span> <span data-ttu-id="ae1fb-107">若要读取从端口与用于 JD Edwards OneWorld Microsoft BizTalk 适配器绑定接收的消息的上下文属性，使用的语法，消息 (JDE。属性），在表达式中。</span><span class="sxs-lookup"><span data-stu-id="ae1fb-107">To read a context property of a message received from a port bound to the Microsoft BizTalk Adapter for JD Edwards OneWorld, use the syntax, Message(JDE.Property), in an expression.</span></span> <span data-ttu-id="ae1fb-108">有关属性的列表，请参阅 JD Edwards OneWorld 会话管理。</span><span class="sxs-lookup"><span data-stu-id="ae1fb-108">Refer to JD Edwards OneWorld Session Management for a list of properties.</span></span>  
  
 <span data-ttu-id="ae1fb-109">在 BizTalk 中，消息是不可变的。</span><span class="sxs-lookup"><span data-stu-id="ae1fb-109">In BizTalk, messages are immutable.</span></span>  
  
### <a name="to-assign-a-message-context-property-value"></a><span data-ttu-id="ae1fb-110">若要将分配消息上下文属性值</span><span class="sxs-lookup"><span data-stu-id="ae1fb-110">To assign a message context property value</span></span>  
  
1. <span data-ttu-id="ae1fb-111">创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="ae1fb-111">Create a new message.</span></span>  
  
2. <span data-ttu-id="ae1fb-112">设置消息内容，例如，通过分配现有的消息。</span><span class="sxs-lookup"><span data-stu-id="ae1fb-112">Set the message content, for example, by assigning an existing message.</span></span>  
  
3. <span data-ttu-id="ae1fb-113">设置的属性。</span><span class="sxs-lookup"><span data-stu-id="ae1fb-113">Set the properties.</span></span>  
  
   <span data-ttu-id="ae1fb-114">若要将上下文属性分配到发往用于 JD Edwards OneWorld 绑定到 Microsoft BizTalk 适配器的发送端口的消息，请使用消息赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="ae1fb-114">To assign context properties to a message destined to a send port that is bound to the Microsoft BizTalk Adapter for JD Edwards OneWorld, use the message assignment operator.</span></span> <span data-ttu-id="ae1fb-115">然后，指定在 JD Edwards OneWorld 命名空间中可用的上下文属性之一。</span><span class="sxs-lookup"><span data-stu-id="ae1fb-115">Then, specify one of the available context properties within the JD Edwards OneWorld namespace.</span></span>  
  
   <span data-ttu-id="ae1fb-116">语法是： `Message(JDE.Property) = value;`</span><span class="sxs-lookup"><span data-stu-id="ae1fb-116">The syntax is: `Message(JDE.Property) = value;`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae1fb-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae1fb-117">See Also</span></span>  
 <span data-ttu-id="ae1fb-118">[使用消息上下文属性](../core/using-message-context-properties2.md) </span><span class="sxs-lookup"><span data-stu-id="ae1fb-118">[Using Message Context Properties](../core/using-message-context-properties2.md) </span></span>  
 <span data-ttu-id="ae1fb-119">[关于会话管理](../core/about-session-management1.md) </span><span class="sxs-lookup"><span data-stu-id="ae1fb-119">[About Session Management](../core/about-session-management1.md) </span></span>  
 [<span data-ttu-id="ae1fb-120">教程：使用用于 JD Edwards OneWorld 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="ae1fb-120">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)