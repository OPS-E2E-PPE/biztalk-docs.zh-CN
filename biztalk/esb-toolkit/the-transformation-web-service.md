---
title: 转换 Web 服务 |Microsoft Docs
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
ms.openlocfilehash: 5812cd340d2f7e7a47f54e6e77ff39c144542615
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399658"
---
# <a name="the-transformation-web-service"></a><span data-ttu-id="c3020-102">转换 Web 服务</span><span class="sxs-lookup"><span data-stu-id="c3020-102">The Transformation Web Service</span></span>
<span data-ttu-id="c3020-103">转换 Web 服务允许外部应用程序提交到 ESB 应用程序文档，并让它使用已部署的 Microsoft BizTalk 映射转换。</span><span class="sxs-lookup"><span data-stu-id="c3020-103">The Transformation Web service enables external applications to submit a document to an ESB application and have it transformed using a deployed Microsoft BizTalk map.</span></span> <span data-ttu-id="c3020-104">转换代理与此服务不路由消息通过 BizTalk Messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="c3020-104">Unlike the transformation agent, this service does not route messages through the BizTalk Message Box database.</span></span>  
  
 <span data-ttu-id="c3020-105">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含此服务的两个版本： ASP.NET (ASMX) 版本和 Windows Communication Foundation (WCF) 版本。</span><span class="sxs-lookup"><span data-stu-id="c3020-105">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains two versions of this service: an ASP.NET (ASMX) version and a Windows Communication Foundation (WCF) version.</span></span> <span data-ttu-id="c3020-106">服务名称是**ESB。TransformServices**和**ESB。TransformServices.WCF**分别和服务公开一个方法：</span><span class="sxs-lookup"><span data-stu-id="c3020-106">The service names are **ESB.TransformServices** and **ESB.TransformServices.WCF**, respectively, and the services expose a single method:</span></span>  
  
-   <span data-ttu-id="c3020-107">**转换。**</span><span class="sxs-lookup"><span data-stu-id="c3020-107">**Transform.**</span></span> <span data-ttu-id="c3020-108">此方法将作为参数**字符串**，其中包含要转换的消息和一个**字符串**，其中包含部署在 BizTalk 映射的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="c3020-108">This method takes as parameters a **String** that contains the message to transform and a **String** that contains the fully qualified name of a map deployed in BizTalk.</span></span> <span data-ttu-id="c3020-109">该方法返回**字符串**，其中包含转换后的文档。</span><span class="sxs-lookup"><span data-stu-id="c3020-109">The method returns a **String** that contains the transformed document.</span></span> <span data-ttu-id="c3020-110">使用字符串参数，可降低风险异类环境; 中的互操作性问题但是，请记住，这是 Web 服务，因此，应避免使用它来转换 （在 BizTalk 转换服务更好地适合大型文档） 的大型文档。</span><span class="sxs-lookup"><span data-stu-id="c3020-110">The use of string parameters reduces the risk of interoperability issues in a heterogeneous environment; however, keep in mind that this is a Web service, so you should avoid using it to transform large documents (the Transformation Service in BizTalk is better suited for large documents).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3020-111">默认情况下，转换 Web 服务未配置为需要安全套接字层 (SSL) 客户端进行访问时。</span><span class="sxs-lookup"><span data-stu-id="c3020-111">By default, the Transformation Web services are not configured to require Secure Sockets Layer (SSL) when accessed by clients.</span></span> <span data-ttu-id="c3020-112">应配置服务，因此它需要 SSL 客户端访问和保护 Internet 信息服务 (IIS) Web 服务主机计算机和使用网络级别 IPSec 和相应的文件级访问 BizTalk Server 之间的连接控制列表 (ACL) 权限。</span><span class="sxs-lookup"><span data-stu-id="c3020-112">You should configure the service so that it requires SSL for client access and protect the connection between the Internet Information Services (IIS) Web service host computer and your BizTalk Server using network-level IPSec and appropriate file-level access control list (ACL) permissions.</span></span>