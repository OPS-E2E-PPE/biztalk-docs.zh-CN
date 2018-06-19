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
# <a name="creating-and-publishing-fault-messages"></a>创建并发布错误消息
为了帮助你了解如何使用异常管理框架的功能来管理例外，本部分提供了基于向 ESB 应用程序提交一条消息的一个常见方案。  
  
 方案由用户提交到系统发票。 在处理发票业务流程中的过程中，BizTalk 业务规则引擎引发了应用程序异常，因为数据的某些部分不正确。 业务流程应捕获异常，将有问题的消息发送给其他人或可以更正该消息，然后重新提交处理的消息的系统。  
  
 使用 ESB 失败业务流程异常路由功能时，过程步骤如下所示：  
  
1.  异常处理程序中的代码检测到错误，然后通过调用创建的错误消息**CreateFaultMessage**方法，如下面的代码示例中所示。  
  
    ```csharp  
    // Create fault exception message.  
    faultMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.CreateFaultMessage();  
    ```  
  
2.  ESB 异常机制将错误说明自动插入错误消息上下文 （例如，"业务规则引擎除数为零的错误时引发处理 LoanProcessing 策略。"）。  
  
3.  ESB 异常机制自动提升到错误消息上下文的失败相关的属性和应用程序特定属性，并从当前环境中设置的值。 这些属性如下所示：  
  
    -   **应用程序**（自动填充）  
  
    -   **DateTime** （自动填充为 UTC 值）  
  
    -   **说明**(自动填充-异常消息)  
  
    -   **ErrorType** (自动填充-异常类型)  
  
    -   **MachineName** (自动填充-当前的服务器名称)  
  
    -   **作用域**(自动填充-作用域形状包含当前异常处理程序)  
  
    -   **ServiceName** (自动填充-业务流程名称)  
  
    -   **ServiceInstanceID**(自动填充-业务流程实例 ID 作为 GUID)  
  
4.  异常处理程序中的代码将错误消息的其他属性设置为必需的，如下面的代码示例中所示。  
  
    ```csharp  
    // Set fault message properties.  
    faultMsg.Body.FailureCategory = "MessageBuild";  
    faultMsg.Body.FaultCode = 1000;  
    faultMsg.Body.FaultDescription = "Some error occurred";  
    faultMsg.Body.FaultSeverity =  
       Microsoft.Practices.ESB.ExceptionHandling.FaultSeverity.Severe;  
    ```  
  
5.  ESB 异常机制自动序列化当前**异常**对象写入错误消息。  
  
6.  （可选） 中的异常处理代码可以将当前的业务流程消息添加到 ESB 错误消息使用**AddMessage （faultMsg，messageToAdd）** 方法。 此方法序列化和仍然存在消息，包括所有的上下文属性，如下面的代码示例中所示。  
  
    ```csharp  
    // Add other current orchestration messages to the fault message.  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, approvedRequestMsg);  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, DeniedRequestMsg, @"c:\temp");  
    ```  
  
7.  异常处理程序中的代码将 ESB 错误消息发布到消息框数据库使用的直接绑定的端口。  
  
8.  如果成功发布，会发生以下事件：  
  
    -   业务流程或发送端口订阅可以处理 ESB 错误消息，并提取任何添加的消息，完成，但其上下文属性值。  
  
    -   全局异常处理程序 （发送端口） 自动将 ESB 错误消息发布到 ESB 管理门户。