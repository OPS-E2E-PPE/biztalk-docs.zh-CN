---
title: 创建并发布错误消息 |Microsoft Docs
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
ms.openlocfilehash: c6d57b5f6ed8a5df00e5c1447b54167b3cfa688b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394697"
---
# <a name="creating-and-publishing-fault-messages"></a>创建并发布故障消息
为了帮助你了解如何使用异常管理框架的功能来管理异常，本部分提供了基于邮件提交到 ESB 应用程序的常见方案。  
  
 方案包括用户提交到系统的发票。 在处理业务流程中的发票的课程中，BizTalk 业务规则引擎引发应用程序异常，因为数据的某些部分不正确。 业务流程应捕获异常，将有问题的消息发送到另一个人或系统，可以更正该消息，然后重新提交邮件以进行处理。  
  
 使用 ESB 失败，业务流程异常路由功能时，过程步骤如下所示：  
  
1.  异常处理程序中的代码检测到错误时，并通过调用创建的错误消息**CreateFaultMessage**方法，如下面的代码示例中所示。  
  
    ```csharp  
    // Create fault exception message.  
    faultMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.CreateFaultMessage();  
    ```  
  
2.  ESB 异常机制自动将错误说明插入到错误消息上下文 （例如，"业务规则引擎引发除数为零的错误处理 LoanProcessing 策略时。"）。  
  
3.  ESB 异常机制自动将特定于失败的属性和特定于应用程序的属性升级到错误消息上下文，并从当前环境设置的值。 这些属性如下所示：  
  
    -   **应用程序**（自动填充）  
  
    -   **DateTime** （自动填充为 UTC 值）  
  
    -   **说明**(自动填充-异常消息)  
  
    -   **错误类型**(自动填充，异常类型)  
  
    -   **MachineName** (自动填充，当前的服务器名称)  
  
    -   **作用域**(自动填充，包含当前异常处理程序的作用域形状)  
  
    -   **ServiceName** (自动填充，业务流程名称)  
  
    -   **ServiceInstanceID**(自动填充，以 GUID 形式表示的业务流程实例 ID)  
  
4.  异常处理程序中的代码根据需要，设置错误消息的其他属性，如下面的代码示例中所示。  
  
    ```csharp  
    // Set fault message properties.  
    faultMsg.Body.FailureCategory = "MessageBuild";  
    faultMsg.Body.FaultCode = 1000;  
    faultMsg.Body.FaultDescription = "Some error occurred";  
    faultMsg.Body.FaultSeverity =  
       Microsoft.Practices.ESB.ExceptionHandling.FaultSeverity.Severe;  
    ```  
  
5.  ESB 异常机制自动序列化当前**异常**对象写入错误消息。  
  
6.  （可选） 在异常处理程序中的代码可以将当前业务流程消息添加到 ESB 错误消息使用**AddMessage （faultMsg，messageToAdd）** 方法。 此方法序列化，并包括所有的上下文属性，如下面的代码示例中所示的消息。  
  
    ```csharp  
    // Add other current orchestration messages to the fault message.  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, approvedRequestMsg);  
    Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.AddMessage(  
                                faultMsg, DeniedRequestMsg, @"c:\temp");  
    ```  
  
7.  异常处理程序中的代码将 ESB 错误消息发布到 Messagebox 数据库使用直接绑定的端口。  
  
8.  如果发布成功，将发生以下事件：  
  
    -   业务流程或发送端口订阅可以处理 ESB 错误消息和提取任何添加的消息，完成，但其上下文属性值。  
  
    -   全局异常处理程序 （发送端口） 会自动将 ESB 错误消息发布到 ESB 管理门户。