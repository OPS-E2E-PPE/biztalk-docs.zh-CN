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
ms.openlocfilehash: 4f9f5a42e208d81f8898ce85592402f675d1b361
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979738"
---
# <a name="how-to-assign-message-context-property-values"></a><span data-ttu-id="1680e-102">如何分配消息上下文属性值</span><span class="sxs-lookup"><span data-stu-id="1680e-102">How to Assign Message Context Property Values</span></span>
<span data-ttu-id="1680e-103">若要从 BizTalk 业务流程管理 JD Edwards EnterpriseOne 适配器连接会话，必须在项目中添加对 Microsoft.BizTalk.Adapters.JDEProperties.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="1680e-103">To manage the JD Edwards EnterpriseOne Adapter connection session from a BizTalk orchestration, you must add the reference to Microsoft.BizTalk.Adapters.JDEProperties.dll in your project.</span></span> <span data-ttu-id="1680e-104">此程序集位于 %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin。</span><span class="sxs-lookup"><span data-stu-id="1680e-104">This assembly is located in %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin.</span></span>  
  
 <span data-ttu-id="1680e-105">在引用此属性架构之后，其他上下文属性都可以访问各种 BizTalk 开发工具，例如，业务流程设计器中的消息赋值形状。</span><span class="sxs-lookup"><span data-stu-id="1680e-105">After you reference this property schema, additional context properties are accessible to various BizTalk development tools, for example, the Message Assignment shape within the Orchestration Designer.</span></span>  
  
 <span data-ttu-id="1680e-106">若要访问上下文属性，您指定的 JD Edwards EnterpriseOne 命名空间中可用的上下文属性之一。</span><span class="sxs-lookup"><span data-stu-id="1680e-106">To access a context property, you specify one of the available context properties within the JD Edwards EnterpriseOne namespace.</span></span> <span data-ttu-id="1680e-107">若要读取从端口与用于 JD Edwards EnterpriseOne Microsoft BizTalk 适配器绑定接收的消息的上下文属性，使用的语法，消息 (JDE。属性），在表达式中。</span><span class="sxs-lookup"><span data-stu-id="1680e-107">To read a context property of a message received from a port bound to the Microsoft BizTalk Adapter for JD Edwards EnterpriseOne, use the syntax, Message(JDE.Property), in an expression.</span></span> <span data-ttu-id="1680e-108">有关属性的列表，请参阅 JD Edwards EnterpriseOne 适配器会话管理。</span><span class="sxs-lookup"><span data-stu-id="1680e-108">Refer to JD Edwards EnterpriseOne Adapter Session Management for a list of properties.</span></span>  
  
 <span data-ttu-id="1680e-109">在 BizTalk 中，消息是不可改变的。</span><span class="sxs-lookup"><span data-stu-id="1680e-109">In BizTalk, messages are immutable.</span></span>  
  
### <a name="to-assign-context-property-value"></a><span data-ttu-id="1680e-110">若要将分配上下文属性值</span><span class="sxs-lookup"><span data-stu-id="1680e-110">To assign context property value</span></span>  
  
1. <span data-ttu-id="1680e-111">创建新的消息。</span><span class="sxs-lookup"><span data-stu-id="1680e-111">Create a new message.</span></span>  
  
2. <span data-ttu-id="1680e-112">设置消息内容，例如，通过分配现有的消息。</span><span class="sxs-lookup"><span data-stu-id="1680e-112">Set the message content, for example, by assigning an existing message.</span></span>  
  
3. <span data-ttu-id="1680e-113">设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1680e-113">Set the properties.</span></span>  
  
   <span data-ttu-id="1680e-114">若要将上下文属性分配到发往用于 JD Edwards EnterpriseOne 绑定到 Microsoft BizTalk 适配器的发送端口的消息，请使用消息赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="1680e-114">To assign context properties to a message destined to a send port that is bound to the Microsoft BizTalk Adapter for JD Edwards EnterpriseOne, use the message assignment operator.</span></span> <span data-ttu-id="1680e-115">然后指定 JD Edwards EnterpriseOne 命名空间中可用的上下文属性之一。</span><span class="sxs-lookup"><span data-stu-id="1680e-115">Then specify one of the available context properties within the JD Edwards EnterpriseOne namespace.</span></span>  
  
   <span data-ttu-id="1680e-116">语法是： `Message(JDE.Property) = value;`</span><span class="sxs-lookup"><span data-stu-id="1680e-116">The syntax is: `Message(JDE.Property) = value;`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1680e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1680e-117">See Also</span></span>  
 <span data-ttu-id="1680e-118">[使用消息上下文属性](../core/using-message-context-properties1.md) </span><span class="sxs-lookup"><span data-stu-id="1680e-118">[Using Message Context Properties](../core/using-message-context-properties1.md) </span></span>  
 <span data-ttu-id="1680e-119">[关于会话管理](../core/about-session-management2.md) </span><span class="sxs-lookup"><span data-stu-id="1680e-119">[About Session Management](../core/about-session-management2.md) </span></span>  
 [<span data-ttu-id="1680e-120">教程：使用用于 JD Edwards EnterpriseOne 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="1680e-120">Tutorial: Using the BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/tutorial-using-the-biztalk-adapter-for-jd-edwards-enterpriseone.md)