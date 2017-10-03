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
# <a name="how-to-assign-message-context-property-values"></a><span data-ttu-id="200c5-102">如何分配消息上下文属性值</span><span class="sxs-lookup"><span data-stu-id="200c5-102">How to Assign Message Context Property Values</span></span>
<span data-ttu-id="200c5-103">若要从 BizTalk 业务流程管理 JD Edwards OneWorld 连接会话，必须在项目中添加对 Microsoft.BizTalk.Adapters.JDEProperties.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="200c5-103">To manage the JD Edwards OneWorld connection session from a BizTalk orchestration, you must add the reference to Microsoft.BizTalk.Adapters.JDEProperties.dll in your project.</span></span> <span data-ttu-id="200c5-104">此程序集都位于企业 Applications\bin %SystemDrive%\Program Files\Common Files\Microsoft BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="200c5-104">This assembly is located in %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
 <span data-ttu-id="200c5-105">引用此属性架构后，则其他上下文属性都可以访问各种 BizTalk 开发工具，例如，消息赋值业务流程设计器中的形状。</span><span class="sxs-lookup"><span data-stu-id="200c5-105">After you reference this property schema, additional context properties are accessible to various BizTalk development tools, for example, the Message Assignment shape within the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="200c5-106">若要访问上下文属性，需要在 JD Edwards OneWorld 命名空间中指定一个可用上下文属性。</span><span class="sxs-lookup"><span data-stu-id="200c5-106">To access a context property, you specify one of the available context properties within the JD Edwards OneWorld namespace.</span></span> <span data-ttu-id="200c5-107">若要读取从端口（该端口与用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器绑定）接收到的上下文属性，请在表达式中使用语法 Message(JDE.Property)。</span><span class="sxs-lookup"><span data-stu-id="200c5-107">To read a context property of a message received from a port bound to the Microsoft BizTalk Adapter for JD Edwards OneWorld, use the syntax, Message(JDE.Property), in an expression.</span></span> <span data-ttu-id="200c5-108">有关属性列表，请参阅 JD Edwards OneWorld 会话管理。</span><span class="sxs-lookup"><span data-stu-id="200c5-108">Refer to JD Edwards OneWorld Session Management for a list of properties.</span></span>  
  
 <span data-ttu-id="200c5-109">在 BizTalk 中，消息是不可改变的。</span><span class="sxs-lookup"><span data-stu-id="200c5-109">In BizTalk, messages are immutable.</span></span>  
  
### <a name="to-assign-a-message-context-property-value"></a><span data-ttu-id="200c5-110">若要将分配一个消息上下文属性值</span><span class="sxs-lookup"><span data-stu-id="200c5-110">To assign a message context property value</span></span>  
  
1.  <span data-ttu-id="200c5-111">创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="200c5-111">Create a new message.</span></span>  
  
2.  <span data-ttu-id="200c5-112">设置该消息内容，例如，通过分配现有的消息。</span><span class="sxs-lookup"><span data-stu-id="200c5-112">Set the message content, for example, by assigning an existing message.</span></span>  
  
3.  <span data-ttu-id="200c5-113">设置的属性。</span><span class="sxs-lookup"><span data-stu-id="200c5-113">Set the properties.</span></span>  
  
 <span data-ttu-id="200c5-114">若要将上下文属性分配到将发送端口（该端口与用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器绑定）作为目标的消息，请使用消息赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="200c5-114">To assign context properties to a message destined to a send port that is bound to the Microsoft BizTalk Adapter for JD Edwards OneWorld, use the message assignment operator.</span></span> <span data-ttu-id="200c5-115">然后指定 JD Edwards OneWorld 命名空间中的一个可用上下文属性。</span><span class="sxs-lookup"><span data-stu-id="200c5-115">Then, specify one of the available context properties within the JD Edwards OneWorld namespace.</span></span>  
  
 <span data-ttu-id="200c5-116">语法是：`Message(JDE.Property) = value;`</span><span class="sxs-lookup"><span data-stu-id="200c5-116">The syntax is: `Message(JDE.Property) = value;`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="200c5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="200c5-117">See Also</span></span>  
 <span data-ttu-id="200c5-118">[使用消息上下文属性](../core/using-message-context-properties2.md) </span><span class="sxs-lookup"><span data-stu-id="200c5-118">[Using Message Context Properties](../core/using-message-context-properties2.md) </span></span>  
 <span data-ttu-id="200c5-119">[有关会话管理](../core/about-session-management1.md) </span><span class="sxs-lookup"><span data-stu-id="200c5-119">[About Session Management](../core/about-session-management1.md) </span></span>  
 [<span data-ttu-id="200c5-120">教程： 使用适用于博士 Edwards OneWorld BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="200c5-120">Tutorial: Using the BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-oneworld.md)