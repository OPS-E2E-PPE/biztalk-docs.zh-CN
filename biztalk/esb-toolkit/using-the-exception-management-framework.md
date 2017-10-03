---
title: "使用异常管理框架 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b69c9c01-e7e4-4788-8fe2-43d32075155d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47442604831a3a11bb9d00b65f9dc34961de2367
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-exception-management-framework"></a>使用异常管理框架
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用异常的动态转换和路由进行通信失败 （例如，非部署映射或未返回映射名称的规则）。 当转换或路由过程失败时，ESB 创建一条异常消息，并将其提交通过直接绑定到消息框数据库端口。 ESB 还实现名为所有发送端口。订阅和检索异常消息，并将其发布到 ESB 管理门户的异常。  
  
 此外，所有的业务流程示例使用 ESB 失败业务流程异常路由 API 来处理异常。 在部署任何业务流程项目中，可以使用此 API。 ESB 失败业务流程异常路由功能可提供一种标准的方式，以捕获并报告在 BizTalk Server 环境中的所有异常。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含演示如何使用 ESB 异常管理框架的几个示例项目。 以下两个项目封装 ESB 失败业务流程异常路由 API:  
  
-   **ESB。ExceptionHandling**。 此项目包含用于处理在业务流程中的错误消息处理的所有公共方法。 你必须在本地服务器上的全局程序集缓存中的此项目中注册程序集。  
  
-   **ESB。ExceptionHandling.Schemas.Faults**。 此项目包含命名空间定义的错误消息架构**http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**和系统属性架构。 必须将此项目部署到 Microsoft.Practices.ESB 应用程序容器。  
  
 使用 ESB 失败业务流程异常路由 API 的所有项目必须都引用核心程序集：  
  
-   **Microsoft.Practices.ESB.ExceptionHandling.dll**  
  
-   **Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**  
  
 下列各节提供有关使用 ESB 异常管理框架的详细信息：  
  
-   [ESB 异常 API 成员](../esb-toolkit/the-esb-exception-api-members.md)  
  
-   [创建并发布错误消息](../esb-toolkit/creating-and-publishing-fault-messages.md)  
  
-   [订阅以及提取消息](../esb-toolkit/subscribing-to-and-extracting-messages.md)  
  
-   [方案解决方案步骤](../esb-toolkit/scenario-solution-steps.md)