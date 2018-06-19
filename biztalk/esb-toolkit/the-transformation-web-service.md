---
title: 转换 Web 服务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 788bf4a9-a63b-4fd3-93a2-6e34a1464049
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5abad7a5a7bae3c76fba58ecd92fc3384df5ca25
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294869"
---
# <a name="the-transformation-web-service"></a><span data-ttu-id="b4d1f-102">转换 Web 服务</span><span class="sxs-lookup"><span data-stu-id="b4d1f-102">The Transformation Web Service</span></span>
<span data-ttu-id="b4d1f-103">转换 Web 服务使外部应用程序提交到 ESB 应用程序的文档，并让它使用已部署的 Microsoft BizTalk 映射转换。</span><span class="sxs-lookup"><span data-stu-id="b4d1f-103">The Transformation Web service enables external applications to submit a document to an ESB application and have it transformed using a deployed Microsoft BizTalk map.</span></span> <span data-ttu-id="b4d1f-104">与不同的是转换代理，此服务不路由通过 BizTalk 消息框数据库的消息。</span><span class="sxs-lookup"><span data-stu-id="b4d1f-104">Unlike the transformation agent, this service does not route messages through the BizTalk Message Box database.</span></span>  
  
 <span data-ttu-id="b4d1f-105">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含此服务的两个版本： ASP.NET (ASMX) 版本和 Windows Communication Foundation (WCF) 版本。</span><span class="sxs-lookup"><span data-stu-id="b4d1f-105">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains two versions of this service: an ASP.NET (ASMX) version and a Windows Communication Foundation (WCF) version.</span></span> <span data-ttu-id="b4d1f-106">服务名称**ESB。TransformServices**和**ESB。TransformServices.WCF**分别和服务公开一种方法：</span><span class="sxs-lookup"><span data-stu-id="b4d1f-106">The service names are **ESB.TransformServices** and **ESB.TransformServices.WCF**, respectively, and the services expose a single method:</span></span>  
  
-   <span data-ttu-id="b4d1f-107">**转换。**</span><span class="sxs-lookup"><span data-stu-id="b4d1f-107">**Transform.**</span></span> <span data-ttu-id="b4d1f-108">此方法使用作为参数**字符串**，包含要转换的消息和**字符串**，其中包含部署在 BizTalk 映射的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="b4d1f-108">This method takes as parameters a **String** that contains the message to transform and a **String** that contains the fully qualified name of a map deployed in BizTalk.</span></span> <span data-ttu-id="b4d1f-109">该方法返回**字符串**包含转换后的文档。</span><span class="sxs-lookup"><span data-stu-id="b4d1f-109">The method returns a **String** that contains the transformed document.</span></span> <span data-ttu-id="b4d1f-110">使用字符串参数降低了异类环境; 中的互操作性问题的风险但是，请记住，这是 Web 服务，因此应避免使用它来转换大型文档 （BizTalk 中的转换服务更适合大型文档）。</span><span class="sxs-lookup"><span data-stu-id="b4d1f-110">The use of string parameters reduces the risk of interoperability issues in a heterogeneous environment; however, keep in mind that this is a Web service, so you should avoid using it to transform large documents (the Transformation Service in BizTalk is better suited for large documents).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4d1f-111">默认情况下，转换 Web 服务未配置为要求安全套接字层 (SSL) 时的客户端访问。</span><span class="sxs-lookup"><span data-stu-id="b4d1f-111">By default, the Transformation Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="b4d1f-112">你应配置服务，因此需要 SSL 的客户端访问和保护 Internet Information Services (IIS) Web 服务主机计算机和使用网络级别 IPSec 和相应的文件级访问你 BizTalk Server 之间的连接控制列表 (ACL) 权限。</span><span class="sxs-lookup"><span data-stu-id="b4d1f-112">You should configure the service so that it requires SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and your BizTalk Server using network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span>