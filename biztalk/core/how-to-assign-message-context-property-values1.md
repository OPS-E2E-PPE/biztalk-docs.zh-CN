---
title: "如何分配消息上下文属性 Values1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7e76c62-3110-482c-8083-84d411e6f475
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39bb2a4c6520c1ff3a21889e7508bb2cf417b817
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-assign-message-context-property-values"></a><span data-ttu-id="c1473-102">如何分配消息上下文属性值</span><span class="sxs-lookup"><span data-stu-id="c1473-102">How to Assign Message Context Property Values</span></span>
<span data-ttu-id="c1473-103">若要从 BizTalk 业务流程管理 JD Edwards EnterpriseOne 适配器连接会话，必须在项目中添加对 Microsoft.BizTalk.Adapters.JDEProperties.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="c1473-103">To manage the JD Edwards EnterpriseOne Adapter connection session from a BizTalk orchestration, you must add the reference to Microsoft.BizTalk.Adapters.JDEProperties.dll in your project.</span></span> <span data-ttu-id="c1473-104">此程序集都位于企业 Applications\bin %SystemDrive%\Program Files\Common Files\Microsoft BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="c1473-104">This assembly is located in %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
 <span data-ttu-id="c1473-105">引用此属性架构后，则其他上下文属性都可以访问各种 BizTalk 开发工具，例如，消息赋值业务流程设计器中的形状。</span><span class="sxs-lookup"><span data-stu-id="c1473-105">After you reference this property schema, additional context properties are accessible to various BizTalk development tools, for example, the Message Assignment shape within the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="c1473-106">若要访问上下文属性，你指定的博士 Edwards EnterpriseOne 命名空间中的可用的上下文属性之一。</span><span class="sxs-lookup"><span data-stu-id="c1473-106">To access a context property, you specify one of the available context properties within the JD Edwards EnterpriseOne namespace.</span></span> <span data-ttu-id="c1473-107">若要读取从博士 Edwards EnterpriseOne 绑定到 Microsoft BizTalk 适配器的端口收到的消息的上下文属性，使用语法，消息 (JDE。属性），在表达式中。</span><span class="sxs-lookup"><span data-stu-id="c1473-107">To read a context property of a message received from a port bound to the Microsoft BizTalk Adapter for JD Edwards EnterpriseOne, use the syntax, Message(JDE.Property), in an expression.</span></span> <span data-ttu-id="c1473-108">属性的列表，请参阅博士 Edwards EnterpriseOne 适配器会话管理。</span><span class="sxs-lookup"><span data-stu-id="c1473-108">Refer to JD Edwards EnterpriseOne Adapter Session Management for a list of properties.</span></span>  
  
 <span data-ttu-id="c1473-109">在 BizTalk 中，消息是不可改变的。</span><span class="sxs-lookup"><span data-stu-id="c1473-109">In BizTalk, messages are immutable.</span></span>  
  
### <a name="to-assign-context-property-value"></a><span data-ttu-id="c1473-110">若要将分配上下文属性值</span><span class="sxs-lookup"><span data-stu-id="c1473-110">To assign context property value</span></span>  
  
1.  <span data-ttu-id="c1473-111">创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="c1473-111">Create a new message.</span></span>  
  
2.  <span data-ttu-id="c1473-112">设置该消息内容，例如，通过分配现有的消息。</span><span class="sxs-lookup"><span data-stu-id="c1473-112">Set the message content, for example, by assigning an existing message.</span></span>  
  
3.  <span data-ttu-id="c1473-113">设置的属性。</span><span class="sxs-lookup"><span data-stu-id="c1473-113">Set the properties.</span></span>  
  
 <span data-ttu-id="c1473-114">若要将上下文属性分配给为博士 Edwards EnterpriseOne 绑定到 Microsoft BizTalk 适配器发送端口发往一条消息，请使用消息赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="c1473-114">To assign context properties to a message destined to a send port that is bound to the Microsoft BizTalk Adapter for JD Edwards EnterpriseOne, use the message assignment operator.</span></span> <span data-ttu-id="c1473-115">然后指定在博士 Edwards EnterpriseOne 命名空间中的可用的上下文属性之一。</span><span class="sxs-lookup"><span data-stu-id="c1473-115">Then specify one of the available context properties within the JD Edwards EnterpriseOne namespace.</span></span>  
  
 <span data-ttu-id="c1473-116">语法是：`Message(JDE.Property) = value;`</span><span class="sxs-lookup"><span data-stu-id="c1473-116">The syntax is: `Message(JDE.Property) = value;`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1473-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1473-117">See Also</span></span>  
 <span data-ttu-id="c1473-118">[使用消息上下文属性](../core/using-message-context-properties1.md) </span><span class="sxs-lookup"><span data-stu-id="c1473-118">[Using Message Context Properties](../core/using-message-context-properties1.md) </span></span>  
 <span data-ttu-id="c1473-119">[有关会话管理](../core/about-session-management2.md) </span><span class="sxs-lookup"><span data-stu-id="c1473-119">[About Session Management](../core/about-session-management2.md) </span></span>  
 [<span data-ttu-id="c1473-120">教程： 使用适用于博士 Edwards EnterpriseOne BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="c1473-120">Tutorial: Using the BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-enterpriseone.md)