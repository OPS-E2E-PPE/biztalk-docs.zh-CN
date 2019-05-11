---
title: 动态解析示例工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7789316d-f2c4-4018-a8e8-dd9359f1664f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 207299cefb5632072fdced38f3c25ad495a6d775
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400802"
---
# <a name="how-the-dynamic-resolution-sample-works"></a>动态解析示例工作原理
动态解析示例使用上一节中所述的所有消息传送示例 ESB 调度程序反汇编程序管道组件。  

 单向消息传送方案，该示例解析终结点使用静态、 BRE 或 XPATH 冲突解决程序并中转站到文件、 FTP 或 MQSeries 的文件中的协议。  

 双向消息传送方案，该示例解析使用静态、 BRE、 UDDI 或 XPATH 冲突解决程序的终结点并中转站为 SOAP 或 WCF BasicHttp 的 SOAP 的协议。 此外，示例解析和执行使用 BRE 冲突解决程序，它使用消息上下文属性和消息正文中包含的事实数据确定解析结果的 Microsoft BizTalk 映射。  

 解析过程的结果是双向的所有示例都提交到 ESB 其消息。CanadianServices Web 服务位于 http://localhost/ESB.CanadianServices/SubmitPOService.asmx 。 此外，具体取决于解析结果，该示例执行任一**submitOrder**或**submitPurchase**操作。 此外，ESB 调度程序反汇编程序管道组件可以动态执行 BizTalk 映射时，具体取决于指定或解析的操作。  

 图 1 显示了 DynamicResolutionReqResp_SOAP 配置的管道接收位置。  

 ![动态解析管道](../esb-toolkit/media/ch6-dynamicresolutionpipelines.gif "Ch6-DynamicResolutionPipelines")  

 **图 1**  

 **DynamicResolutionReqResp_SOAP 配置的管道接收的动态解析示例应用程序的位置**  

 图 2 显示了使用 ESB 调度程序拆装器的 ESBReceiveXML 组件的每个实例的属性。  

 ![动态解析接收 XML](../esb-toolkit/media/ch6-dynamicresolutionreceivexml.gif "Ch6-DynamicResolutionReceiveXML")  

 **图 2**  

 **动态解析示例应用程序在 ESBReceiveXML 管道中的组件基于实例的属性**  

 图 2 显示以下属性：  

- **启用**。 此属性确定管道是否处于活动状态。 如果此值设置为**False**，而无需处理传递的消息。  

- **终结点**。 此属性是用来确定要加载，冲突解决程序的连接字符串，并指定终结点配置。  

- **MapName**。 此属性是用来确定要加载的冲突解决程序和执行的 BizTalk 映射的连接字符串。 它可以是映射而不是冲突解决程序连接字符串的完全限定的名称。  

- **验证**。 如果设置为 **，则返回 True** （默认设置），ESB 调度程序拆装器组件指示 ESB 转换服务来验证根据源架构是在映射中定义的源消息将解析和执行。  

  图 3 显示了使用 ESB 调度程序的 ESBSendPassthrough 组件的每个实例的属性。  

  ![动态解析发送直通](../esb-toolkit/media/ch6-dynamicresolutionsendpassthrough.gif "Ch6-DynamicResolutionSendPassthrough")  

  **图 3**  

  **动态解析示例应用程序在 ESBSendPassthrough 管道中的组件基于实例的属性**  

  图 3 显示以下属性：  

- **启用**。 此属性确定管道是否处于活动状态。 如果此值设置为**False**，而无需处理传递的消息。  

- **终结点**。 此属性是用来确定负载和终结点配置的冲突解决程序的连接字符串。  

- **MapName**。 此属性是用来确定要加载的冲突解决程序和执行的 BizTalk 映射的连接字符串。 映射的完全限定的名称可以代替冲突解决程序的连接字符串。  

- **验证**。 如果设置为 **，则返回 True** （默认设置），ESB 调度程序拆装器组件指示 ESB 转换服务来验证根据源架构是在映射中定义的源消息将解析和执行。
