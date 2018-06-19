---
title: 创建并发布错误消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc7ba1d9-b647-4cba-a3dc-4400505ff51f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57833cefedcf53b7355c17cf97d429d2eb988819
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290677"
---
# <a name="creating-and-publishing-fault-messages"></a><span data-ttu-id="7e45e-102">创建并发布错误消息</span><span class="sxs-lookup"><span data-stu-id="7e45e-102">Creating and Publishing Fault Messages</span></span>
<span data-ttu-id="7e45e-103">为了帮助你了解如何使用异常管理框架的功能来管理例外，本部分提供了基于向 ESB 应用程序提交一条消息的一个常见方案。</span><span class="sxs-lookup"><span data-stu-id="7e45e-103">To help you understand how to use the features of the Exception Management Framework to manage exceptions, this section presents a common scenario based on the submission of a message to an ESB application.</span></span>  
  
 <span data-ttu-id="7e45e-104">方案由用户提交到系统发票。</span><span class="sxs-lookup"><span data-stu-id="7e45e-104">The scenario consists of a user submitting an invoice to the system.</span></span> <span data-ttu-id="7e45e-105">在处理发票业务流程中的过程中，BizTalk 业务规则引擎引发了应用程序异常，因为数据的某些部分不正确。</span><span class="sxs-lookup"><span data-stu-id="7e45e-105">During the course of processing the invoice in an orchestration, the BizTalk Business Rules Engine throws an application exception because some part of the data is incorrect.</span></span> <span data-ttu-id="7e45e-106">业务流程应捕获异常，将有问题的消息发送给其他人或可以更正该消息，然后重新提交处理的消息的系统。</span><span class="sxs-lookup"><span data-stu-id="7e45e-106">The business process should catch the exception, send the offending message to another person or system that can correct the message, and then resubmit the message for processing.</span></span>  
  
 <span data-ttu-id="7e45e-107">使用 ESB 失败业务流程异常路由功能时，过程步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e45e-107">When using the ESB Failed Orchestration Exception Routing feature, the process steps are the following:</span></span>  
  
1.  <span data-ttu-id="7e45e-108">异常处理程序中的代码检测到错误，然后通过调用创建的错误消息**CreateFaultMessage**方法，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="7e45e-108">Code in the exception handler detects the error and creates a fault message by calling the **CreateFaultMessage** method, as shown in the following code example.</span></span>  
  
    ```csharp  
    // Create fault exception message.  
    faultMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.CreateFaultMessage();  
    ```  
  
2.  <span data-ttu-id="7e45e-109">ESB 异常机制将错误说明自动插入错误消息上下文 （例如，"业务规则引擎除数为零的错误时引发处理 LoanProcessing 策略。"）。</span><span class="sxs-lookup"><span data-stu-id="7e45e-109">The ESB Exception mechanism automatically inserts the error description into the fault message context (for example, "The Business Rules Engine threw a divide by zero error while processing the LoanProcessing policy.").</span></span>  
  
3.  <span data-ttu-id="7e45e-110">ESB 异常机制自动提升到错误消息上下文的失败相关的属性和应用程序特定属性，并从当前环境中设置的值。</span><span class="sxs-lookup"><span data-stu-id="7e45e-110">The ESB Exception mechanism automatically promotes failure-specific properties and application-specific properties into the fault message context and sets the values from the current environment.</span></span> <span data-ttu-id="7e45e-111">这些属性如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e45e-111">These properties are the following:</span></span>  
  
    -   <span data-ttu-id="7e45e-112">**应用程序**（自动填充）</span><span class="sxs-lookup"><span data-stu-id="7e45e-112">**Application** (auto-populated)</span></span>  
  
    -   <span data-ttu-id="7e45e-113">**DateTime** （自动填充为 UTC 值）</span><span class="sxs-lookup"><span data-stu-id="7e45e-113">**DateTime** (auto-populated as a UTC value)</span></span>  
  
    -   <span data-ttu-id="7e45e-114">**说明**(自动填充-异常消息)</span><span class="sxs-lookup"><span data-stu-id="7e45e-114">**Description** (auto-populated—the exception message)</span></span>  
  
    -   <span data-ttu-id="7e45e-115">**ErrorType** (自动填充-异常类型)</span><span class="sxs-lookup"><span data-stu-id="7e45e-115">**ErrorType** (auto-populated—the exception type)</span></span>  
  
    -   <span data-ttu-id="7e45e-116">**MachineName** (自动填充-当前的服务器名称)</span><span class="sxs-lookup"><span data-stu-id="7e45e-116">**MachineName** (auto-populated—the current server name)</span></span>  
  
    -   <span data-ttu-id="7e45e-117">**作用域**(自动填充-作用域形状包含当前异常处理程序)</span><span class="sxs-lookup"><span data-stu-id="7e45e-117">**Scope** (auto-populated—the Scope shape that contains the current exception handler)</span></span>  
  
    -   <span data-ttu-id="7e45e-118">**ServiceName** (自动填充-业务流程名称)</span><span class="sxs-lookup"><span data-stu-id="7e45e-118">**ServiceName** (auto-populated—the orchestration name)</span></span>  
  
    -   <span data-ttu-id="7e45e-119">**ServiceInstanceID**(自动填充-业务流程实例 ID 作为 GUID)</span><span class="sxs-lookup"><span data-stu-id="7e45e-119">**ServiceInstanceID**(auto-populated—the orchestration instance ID as a GUID)</span></span>  
  
4.  <span data-ttu-id="7e45e-120">异常处理程序中的代码将错误消息的其他属性设置为必需的，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="7e45e-120">Code in the exception handler sets other properties of the fault message as required, as shown in the following code example.</span></span>  
  
    ```csharp  
    // Set fault message properties.  
    faultMsg.Body.FailureCategory = "MessageBuild";  
    faultMsg.Body.FaultCode = 1000;  
    faultMsg.Body.FaultDescription = "Some error occurred";  
    faultMsg.Body.FaultSeverity =  
       Microsoft.Practices.ESB.ExceptionHandling.FaultSeverity.Severe;  
    ```  
  
5.  <span data-ttu-id="7e45e-121">ESB 异常机制自动序列化当前**异常**对象写入错误消息。</span><span class="sxs-lookup"><span data-stu-id="7e45e-121">The ESB Exception mechanism automatically serializes the current **Exception** object into the fault message.</span></span>  
  
6.  <span data-ttu-id="7e45e-122">（可选） 中的异常处理代码可以将当前的业务流程消息添加到 ESB 错误消息使用**AddMessage （faultMsg，messageToAdd）** 方法。</span><span class="sxs-lookup"><span data-stu-id="7e45e-122">Optionally, code in the exception handler can add current orchestration messages to the ESB fault message using the **AddMessage(faultMsg, messageToAdd)** method.</span></span> <span data-ttu-id="7e45e-123">此方法序列化和仍然存在消息，包括所有的上下文属性，如下面的代码示例中所示。</span><span class="sxs-lookup"><span data-stu-id="7e45e-123">This method serializes and persists the message, including all the context properties, as shown in the following code example.</span></span>  
  
    ```csharp  
    // Add other current orchestration messages to the fault message.  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, approvedRequestMsg);  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, DeniedRequestMsg, @"c:\temp");  
    ```  
  
7.  <span data-ttu-id="7e45e-124">异常处理程序中的代码将 ESB 错误消息发布到消息框数据库使用的直接绑定的端口。</span><span class="sxs-lookup"><span data-stu-id="7e45e-124">Code in the exception handler publishes the ESB fault message to the Message Box database using a direct bound port.</span></span>  
  
8.  <span data-ttu-id="7e45e-125">如果成功发布，会发生以下事件：</span><span class="sxs-lookup"><span data-stu-id="7e45e-125">If publishing succeeds, the following events occur:</span></span>  
  
    -   <span data-ttu-id="7e45e-126">业务流程或发送端口订阅可以处理 ESB 错误消息，并提取任何添加的消息，完成，但其上下文属性值。</span><span class="sxs-lookup"><span data-stu-id="7e45e-126">Orchestration or send port subscriptions can process the ESB fault message and extract any added messages, complete with their context property values.</span></span>  
  
    -   <span data-ttu-id="7e45e-127">全局异常处理程序 （发送端口） 自动将 ESB 错误消息发布到 ESB 管理门户。</span><span class="sxs-lookup"><span data-stu-id="7e45e-127">A global exception handler (a send port) automatically publishes the ESB fault message to the ESB Management Portal.</span></span>