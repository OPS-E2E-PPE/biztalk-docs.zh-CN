---
title: 面向服务的组件的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77d8560a9dd9862ec2a265de729afd1879fb206f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356728"
---
# <a name="components-of-the-service-oriented-solution"></a>面向服务的组件的解决方案
本部分介绍面向服务的解决方案的主要 BizTalk Server 组件。 下图显示了解决方案的主要组件：  
  
 ![面向服务的解决方案流关系图](../core/media/service-oriented-flow-diagram.gif "Service_Oriented_Flow_Diagram")  
  
 面向服务的解决方案具有三个版本的业务流程：  
  
- 其中所有三个后端应用程序进行了存根版本  
  
- 以内联方式调用一个在所有三个后端应用程序  
  
- 使用适配器连接到应用程序的版本。  
  
  在 SDK\Senarios\SO\BTSSoln\Orchestrations 目录中显示的业务流程的所有版本。  
  
  业务流程的内联版本提供了最低的延迟时间之间的请求和响应解决方案中。  
  
  有关源文件的信息，请参阅[面向服务的解决方案的文件清单](../core/file-inventory-for-the-service-oriented-solution.md)。  
  
## <a name="orchestrations-in-the-service-oriented-solution"></a>面向服务中的业务流程的解决方案  
 三个业务流程**CustomerServiceReceiveSend**， **CustomerServiceNativeRequestResponse**，并**CustomerService**的解决方案。 **CustomerServiceReceiveSend**并**CustomerServiceNativeRequestResponse**业务流程充当前端调用**CustomerService**业务流程。 **CustomerService**业务流程执行大部分工作，将请求发送到后端应用程序、 收集答复、 将答复合并到单个消息，并将其发送到相应前端业务流程。 由于前端业务流程调用**CustomerService**业务流程，因此前端业务流程等待，直到**CustomerService**业务流程完成。  
  
 该解决方案公开**CustomerServiceNativeRequestResponse**业务流程作为 Web 服务。 **CustomerServiceReceiveSend**业务流程获取来自 MQSeries 队列的消息。  
  
## <a name="back-end-applications"></a>后端应用程序  
 面向服务的解决方案与三个后端应用程序进行通信：  
  
- **付款跟踪模拟**应用程序返回模拟的最近付款列表。 **付款跟踪模拟**从 MQSeries 队列读取请求并向另一个 MQSeries 队列发送响应。  
  
- **PendingTransaction**应用程序报告的客户帐户挂起事务总数之和。 应用程序是使用 Microsoft Host Integration Server (HIS) 进行通信与大型机上的 CICS/COBOL 程序的 Web 服务。  
  
- SAP 应用程序提供了有关客户的信用总限额的信息。 该解决方案将连接到 SAP 应用程序作为 Web 服务。 应用程序使用中的 SAP 适配器[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]与 SAP 系统进行通信。  
  
## <a name="pipelines"></a>管道  
 面向服务的解决方案的两个位置使用除默认管道： 的接收管道**CustomerServiceReceiveSend**业务流程，并**CustomerService**业务流程的发送为管道**付款跟踪模拟**。 这两个管道使用自定义组件。  
  
 接收管道**CustomerServiceReceiveSend**包括一个自定义参与方解析组件， **SSO 票证颁发者管道组件**。 消息的**CustomerServiceReceiveSend**业务流程收到没有凭据。 这模拟的是如果在消息来自交互式语音应答系统，会发生什么情况。 自定义管道组件将添加接收主机使用的 BizTalk 服务帐户的凭据。  
  
 与之相反，消息**CustomerSericeNativeRequestResponse**业务流程已收到具有凭据。 由于 Web 服务的虚拟文件夹配置为使用集成安全性和 SOAP 接收位置配置为将企业单一登录 (SSO) 集成，SOAP 适配器生成的消息的票证。  
  
 其他自定义管道中将出现**CustomerService**到发送管道**付款跟踪模拟**应用程序。 该组件，MQSeries 标头 Setter 管道组件设置的两个 MQSeries 消息标头属性的值。 该组件设置第一个消息数据格式 (**MQMD_Format**)，以指示消息的形式**MQCIH**结构，该结构常用于与 CICS 程序进行通信。 第二个、 数据本身的格式内**MQCIH**结构 (**MQCIH_Format**)，设置为显示该消息是一个字符串。  
  
 使用**MQCIH**格式，可将用户 ID 和密码传递**MQCIH**结构。 SSO 关联应用程序将 BizTalk 应用程序的 Windows 用户 ID 映射到付款跟踪系统的用户 Id 中传递**MQCIH**结构。  
  
> [!NOTE]
>  该解决方案的内联版本使用相同管道，通过从业务流程中调用它们。 这样允许重用管道代码。  
  
## <a name="client-application"></a>客户端应用程序  
 该解决方案包含在 C# 中编写的客户端应用程序。 可以使用该应用程序发送请求作为 SOAP 或 MQSeries 消息，并检查结果。  
  
## <a name="other-assemblies"></a>其他程序集  
 该应用程序包括多个辅助程序集不在以上摘要图中所示。 **实用程序**解决方案的程序集实用工具函数。  
  
 **ErrorHelper**程序集包含错误代码转换成消息，并将错误消息转换为错误代码的类。  
  
 **ServiceLevelTracking**程序集包括帮助器方法使用业务活动监视 (BAM) API 来跟踪服务级别协议的数据。  
  
 **ConfigHelper**程序集包含帮助器方法来检索配置值从解决方案**SSOConfigStore**应用程序。  
  
## <a name="see-also"></a>请参阅  
 [开发面向服务的解决方案](../core/developing-a-service-oriented-solution.md)   
 [面向服务的解决方案的文件清单](../core/file-inventory-for-the-service-oriented-solution.md)