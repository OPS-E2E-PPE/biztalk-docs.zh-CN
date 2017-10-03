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
# <a name="the-exception-handling-web-service"></a><span data-ttu-id="8bf16-102">异常处理 Web 服务</span><span class="sxs-lookup"><span data-stu-id="8bf16-102">The Exception Handling Web Service</span></span>
<span data-ttu-id="8bf16-103">异常处理 Web 服务接受的错误消息，并将其发布到 ESB 异常门户。</span><span class="sxs-lookup"><span data-stu-id="8bf16-103">The Exception Handling Web service accepts a fault message and publishes it to the ESB Exception Portal.</span></span> <span data-ttu-id="8bf16-104">客户端应用程序可以创建异常消息，并将其提交至 ESB，其中该异常类型或一般的处理程序，而配置的任何处理程序可以处理的异常。</span><span class="sxs-lookup"><span data-stu-id="8bf16-104">A client application can create exception messages and submit them to the ESB, where any handler configured for that exception type, or a generic handler, can process the exception.</span></span> <span data-ttu-id="8bf16-105">此服务的主要好处是能让 ESB 应用程序，以参与 ESB 异常处理机制外部实体。</span><span class="sxs-lookup"><span data-stu-id="8bf16-105">The major benefit of this service is that it allows entities outside an ESB application to participate in the ESB exception handling mechanism.</span></span>  
  
 <span data-ttu-id="8bf16-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含此服务的两个版本： ASP.NET (ASMX) 版本和 Windows Communication Foundation (WCF) 版本。</span><span class="sxs-lookup"><span data-stu-id="8bf16-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains two versions of this service: an ASP.NET (ASMX) version and a Windows Communication Foundation (WCF) version.</span></span> <span data-ttu-id="8bf16-107">服务名称**ESB。ExceptionHandlingServices**和**ESB。ExceptionHandlingServices.WCF**分别和服务公开一种方法：</span><span class="sxs-lookup"><span data-stu-id="8bf16-107">The service names are **ESB.ExceptionHandlingServices** and **ESB.ExceptionHandlingServices.WCF**, respectively, and the services expose a single method:</span></span>  
  
-   <span data-ttu-id="8bf16-108">**SubmitFault**。</span><span class="sxs-lookup"><span data-stu-id="8bf16-108">**SubmitFault**.</span></span> <span data-ttu-id="8bf16-109">此方法采用实例**FaultMessage**类并没有返回值。</span><span class="sxs-lookup"><span data-stu-id="8bf16-109">This method takes an instance of the **FaultMessage** class and has no return value.</span></span>  
  
 <span data-ttu-id="8bf16-110">异常处理机制的工作方式的信息，请参阅[使用 ESB 异常管理](../esb-toolkit/using-esb-exception-management.md)。</span><span class="sxs-lookup"><span data-stu-id="8bf16-110">For information about the way the exception handling mechanism works, see [Using ESB Exception Management](../esb-toolkit/using-esb-exception-management.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bf16-111">默认情况下，异常处理 Web 服务未配置为要求安全套接字层 (SSL) 时的客户端访问。</span><span class="sxs-lookup"><span data-stu-id="8bf16-111">By default, the Exception Handling Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="8bf16-112">你应配置服务，因此需要 SSL 的客户端访问和保护 Internet Information Services (IIS) Web 服务主机计算机和承载的服务器之间的连接**ESBExceptions**数据库使用网络级别 IPSec 和相应的文件级访问控制列表 (ACL) 权限。</span><span class="sxs-lookup"><span data-stu-id="8bf16-112">You should configure the service so that it requires SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and the server that hosts the **ESBExceptions** database using network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span>