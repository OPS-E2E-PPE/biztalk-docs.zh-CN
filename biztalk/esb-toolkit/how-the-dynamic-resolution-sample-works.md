---
title: "动态解析示例的工作原理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7789316d-f2c4-4018-a8e8-dd9359f1664f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe7d7b473482c432c8e3ae9ca48cab414a9e9573
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-dynamic-resolution-sample-works"></a>动态解析示例的工作原理
动态解析示例使用上一节中所述的所有消息传送示例 ESB 调度程序反汇编程序管道组件。  
  
 为单向消息传递方案，该示例解析终结点使用静态、 BRE 或 XPATH 冲突解决程序，代理到文件、 FTP 或 MQSeries 来自文件的协议。  
  
 为双向消息传递方案，该示例解析终结点使用静态、 BRE、 UDDI 或 XPATH 冲突解决程序，代理为 SOAP 或 WCF BasicHttp 来自 SOAP 的协议。 此外，示例解析和执行使用 BRE 冲突解决程序，它使用消息上下文属性和消息正文中包含的事实数据以确定解析结果的 Microsoft BizTalk 映射。  
  
 解析过程的结果是双向的所有示例都提交到 ESB 其消息。位于 http://localhost/ESB.CanadianServices/SubmitPOService.asmx CanadianServices Web 服务。 此外，具体取决于解析结果中，该示例执行**将订单**或**submitPurchase**操作。 此外，ESB 调度程序反汇编程序管道组件动态执行 BizTalk 映射，具体取决于指定或解析的操作。  
  
 图 1 显示 DynamicResolutionReqResp_SOAP 的配置的管道接收位置。  
  
 ![动态解析管道](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6 DynamicResolutionPipelines")  
  
 **图 1**  
  
 **配置的管道的 DynamicResolutionReqResp_SOAP 接收动态解析示例应用程序的位置**  
  
 图 2 显示了使用 ESB 调度程序反汇编程序 ESBReceiveXML 组件的每个实例属性。  
  
 ![动态解析接收 XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6 DynamicResolutionReceiveXML")  
  
 **图 2**  
  
 **中的动态解析 ESBReceiveXML 管道的组件的每个实例属性示例应用程序**  
  
 以下属性图 2 所示：  
  
-   **启用**。 此属性确定管道是否处于活动状态。 如果此值设置为**False**，而不处理传递的消息。  
  
-   **终结点**。 此属性是用来确定要加载，请的冲突解决程序的连接字符串，并指定终结点配置。  
  
-   **映射名称**。 此属性是用来确定哪些冲突解决程序，以加载和执行哪些 BizTalk 映射的连接字符串。 它可以是映射的而不是映射的解析程序连接字符串的完全限定的名称。  
  
-   **验证**。 当设置为**True** （默认设置），ESB 调度程序拆装器组件指示 ESB 转换服务以验证对源架构中的映射定义源消息将解析和执行。  
  
 图 3 显示了使用 ESB 调度程序 ESBSendPassthrough 组件的每个实例属性。  
  
 ![动态解析发送传递](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6 DynamicResolutionSendPassthrough")  
  
 **图 3**  
  
 **中的动态解析 ESBSendPassthrough 管道的组件的每个实例属性示例应用程序**  
  
 以下属性图 3 所示：  
  
-   **启用**。 此属性确定管道是否处于活动状态。 如果此值设置为**False**，而不处理传递的消息。  
  
-   **终结点**。 此属性是用来确定负载和终结点配置的解析程序的连接字符串。  
  
-   **映射名称**。 此属性是用来确定哪些冲突解决程序，以加载和执行哪些 BizTalk 映射的连接字符串。 映射的完全限定的名称可以代替冲突解决程序的连接字符串。  
  
-   **验证**。 当设置为**True** （默认设置），ESB 调度程序拆装器组件指示 ESB 转换服务以验证对源架构中的映射定义源消息将解析和执行。