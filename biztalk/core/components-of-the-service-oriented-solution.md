---
title: "服务组件面向解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service solution tutorial, pipelines
- pipelines, service solutions
- service solution tutorial, assemblies
- service solution tutorial, components [BizTalk Server]
- service solution tutorial, client applications
- assemblies, service solutions
- orchestrations, service solutions
- client applications, service solutions
- back-end systems
- service solution tutorial, orchestrations
- service solution tutorial, back-end applications
ms.assetid: 97b7b754-abfb-48f9-87bf-7fe171121166
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a50743b178f9394c74b137e265532542af2b579c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="components-of-the-service-oriented-solution"></a>服务组件面向解决方案
本部分对面向服务的解决方案的主要 BizTalk Server 组件进行了说明。 下图显示了该解决方案的主要组件：  
  
 ![面向服务的解决方案流关系图](../core/media/service-oriented-flow-diagram.gif "Service_Oriented_Flow_Diagram")  
  
 面向服务的解决方案具有以下三个业务流程版本：  
  
-   一个版本中对所有三个后端应用程序进行了存根  
  
-   一个版本中将内联调用所有三个后端应用程序  
  
-   一个版本使用适配器连接到应用程序。  
  
 在 SDK\Senarios\SO\BTSSoln\Orchestrations 目录中将显示所有这些业务流程版本。  
  
 业务流程的内联版本提供了业务流程内请求与响应之间最低的延迟时间。  
  
 有关源文件的信息，请参阅[服务面向解决方案的文件清单](../core/file-inventory-for-the-service-oriented-solution.md)。  
  
## <a name="orchestrations-in-the-service-oriented-solution"></a>面向服务的解决方案中的业务流程  
 三个业务流程， **CustomerServiceReceiveSend**， **CustomerServiceNativeRequestResponse**，和**CustomerService**编写解决方案的大容量。 **CustomerServiceReceiveSend**和**CustomerServiceNativeRequestResponse**业务流程充当前端调用**CustomerService**业务流程。 **CustomerService**业务流程完成大部分工作-将请求发送到后端应用程序、 收集答复、 将答复合并为单个消息，并将其发送到相应前端业务流程。 因为前端业务流程调用**CustomerService**业务流程，将一直等到前端业务流程**CustomerService**业务流程完成。  
  
 解决方案公开**CustomerServiceNativeRequestResponse**作为 Web 服务的业务流程。 **CustomerServiceReceiveSend** orchestration 采用 MQSeries 队列中的消息。  
  
## <a name="back-end-applications"></a>后端应用程序  
 面向服务的解决方案与三个后端应用程序进行通信：  
  
-   **PaymentTracker**应用程序返回的最近的付款模拟的列表。 **PaymentTracker**从 MQSeries 队列读取请求并发送到另一个 MQSeries 队列响应。  
  
-   **PendingTransaction**应用程序报告挂起针对的是客户帐户的事务的总数。 而该应用程序是使用 Microsoft Host Integration Server (HIS) 与大型机上的 CICS/COBOL 程序进行通信的 Web Services。  
  
-   SAP 应用程序提供有关客户的信用总限额的信息。 该解决方案将连接到作为 Web Services 的 SAP 应用程序。 应用程序使用 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 中的 SAP 适配器与 SAP 系统进行通信。  
  
## <a name="pipelines"></a>管道  
 面向服务的解决方案在两个位置使用除默认管道： 用于接收管道**CustomerServiceReceiveSend**业务流程，和**CustomerService**业务流程的发送到管道**PaymentTracker**。 这两个管道都使用自定义组件。  
  
 接收管道**CustomerServiceReceiveSend**包括自定义方解析组件， **SSO 票证颁发者管道组件**。 消息的**CustomerServiceReceiveSend** orchestration 接收没有凭据。 这样可以模拟在消息来自交互式语音应答系统的情况下所发生的情况。 自定义管道组件将使用 BizTalk 接收主机的服务帐户来添加凭据。  
  
 相反，消息**CustomerSericeNativeRequestResponse**业务流程已接收具有凭据。 由于为集成安全性配置了 Web Services 的虚拟文件夹，并且配置了 SOAP 接收位置以集成企业单一登录 (SSO)，因此 SOAP 适配器将为该消息生成票证。  
  
 其他自定义管道将出现在**CustomerService**到发送管道**PaymentTracker**应用程序。 MQSeries 标头 Setter 管道组件将设置两个 MQSeries 消息头属性的值。 该组件设置的第一个，消息数据格式 (**MQMD_Format**)，以指示消息位于形式**MQCIH**结构时，通常使用与 CICS 程序进行通信的结构。 第二个、 数据本身的格式中**MQCIH**结构 (**MQCIH_Format**)，设置为显示该消息是一个字符串。  
  
 使用**MQCIH**格式可用于传递用户 ID 和密码在**MQCIH**结构。 SSO 关联应用程序将 BizTalk 应用程序的 Windows 用户 ID 映射到支付跟踪系统的用户 Id 传入**MQCIH**结构。  
  
> [!NOTE]
>  该解决方案的内联版本使用相同管道，方法是从业务流程中调用这些管道。 这样允许重用管道代码。  
  
## <a name="client-application"></a>客户端应用程序  
 该解决方案包括使用 C# 编写的客户端应用程序。 可以使用该应用程序将请求作为 SOAP 或 MQSeries 消息进行发送并检查结果。  
  
## <a name="other-assemblies"></a>其他程序集  
 应用程序包括几个未显示在以上摘要图中的辅助程序集。 **实用工具**解决方案的程序集实用工具函数。  
  
 **ErrorHelper**程序集包含将错误代码转换消息，并将错误消息转换为错误代码的类。  
  
 **ServiceLevelTracking**程序集包括使用业务活动监视 (BAM) API 跟踪服务级别协议的数据的帮助器方法。  
  
 **ConfigHelper**程序集包含帮助器方法来检索从解决方案的配置值**SSOConfigStore**应用程序。  
  
## <a name="see-also"></a>另请参阅  
 [面向开发的服务解决方案](../core/developing-a-service-oriented-solution.md)   
 [服务文件清单面向解决方案](../core/file-inventory-for-the-service-oriented-solution.md)