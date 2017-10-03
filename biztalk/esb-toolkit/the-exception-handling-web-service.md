---
title: "异常处理 Web 服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe6ebdf-9b92-40c7-93fb-afd6c5f68aaa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8d8f3439e3b99d118e2932d0a158113ec51be2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-exception-handling-web-service"></a>异常处理 Web 服务
异常处理 Web 服务接受的错误消息，并将其发布到 ESB 异常门户。 客户端应用程序可以创建异常消息，并将其提交至 ESB，其中该异常类型或一般的处理程序，而配置的任何处理程序可以处理的异常。 此服务的主要好处是能让 ESB 应用程序，以参与 ESB 异常处理机制外部实体。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含此服务的两个版本： ASP.NET (ASMX) 版本和 Windows Communication Foundation (WCF) 版本。 服务名称**ESB。ExceptionHandlingServices**和**ESB。ExceptionHandlingServices.WCF**分别和服务公开一种方法：  
  
-   **SubmitFault**。 此方法采用实例**FaultMessage**类并没有返回值。  
  
 异常处理机制的工作方式的信息，请参阅[使用 ESB 异常管理](../esb-toolkit/using-esb-exception-management.md)。  
  
> [!NOTE]
>  默认情况下，异常处理 Web 服务未配置为要求安全套接字层 (SSL) 时的客户端访问。 你应配置服务，因此需要 SSL 的客户端访问和保护 Internet Information Services (IIS) Web 服务主机计算机和承载的服务器之间的连接**ESBExceptions**数据库使用网络级别 IPSec 和相应的文件级访问控制列表 (ACL) 权限。