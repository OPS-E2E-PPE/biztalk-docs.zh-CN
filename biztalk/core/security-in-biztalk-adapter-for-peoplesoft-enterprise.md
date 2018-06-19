---
title: BizTalk 适配器 PeopleSoft 企业中的安全 |Microsoft 文档
description: 使用 enterprise 上单一登录 (SSO) 来保护在 BizTalk 使用 PeopleSoft Enterprise 适配器的应用程序
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cfdf0db-6f83-4322-a57a-e373c7245700
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfbfea25bfad3a745f7f09c41302a556f4846b52
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013052"
---
# <a name="security-in-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="cee32-103">PeopleSoft Enterprise 的 BizTalk 适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="cee32-103">Security in BizTalk Adapter for PeopleSoft Enterprise</span></span>

## <a name="overview"></a><span data-ttu-id="cee32-104">概述</span><span class="sxs-lookup"><span data-stu-id="cee32-104">Overview</span></span>
<span data-ttu-id="cee32-105">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器提供了单一登录 (SSO) 支持。</span><span class="sxs-lookup"><span data-stu-id="cee32-105">Microsoft BizTalk Adapter for PeopleSoft Enterprise provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="cee32-106">企业单一登录工具创建的关联应用程序代表诸如 PeopleSoft 之类的服务器系统。</span><span class="sxs-lookup"><span data-stu-id="cee32-106">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as PeopleSoft.</span></span> 

<span data-ttu-id="cee32-107">本部分提供用于在安全的环境 PeopleSoft 企业中部署 Microsoft BizTalk Server 适配器的准则。</span><span class="sxs-lookup"><span data-stu-id="cee32-107">This section provides guidelines for deploying Microsoft BizTalk Server Adapter for PeopleSoft Enterprise in a secure environment.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="cee32-108">我们建议您限制对 PeopleSoft 企业使用 BizTalk 适配器授权用户仅，如客户端文件直接连接到业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="cee32-108">We recommended that you restrict the use of BizTalk Adapter for PeopleSoft Enterprise to authorized users only, as the client files directly connect to the line-of-business applications.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="cee32-109">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cee32-109">Next steps</span></span> 
  
-   [<span data-ttu-id="cee32-110">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="cee32-110">Requirements for Single Sign-On</span></span>](../core/requirements-for-single-sign-on2.md)  
  
-   [<span data-ttu-id="cee32-111">用于 PeopleSoft Enterprise 的单一登录和 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="cee32-111">Single Sign-On and BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/single-sign-on-and-biztalk-adapter-for-peoplesoft-enterprise.md)  
  
-   [<span data-ttu-id="cee32-112">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="cee32-112">Creating Affiliate Applications</span></span>](../core/creating-affiliate-applications2.md)  
  
-   [<span data-ttu-id="cee32-113">创建端口</span><span class="sxs-lookup"><span data-stu-id="cee32-113">Creating Ports</span></span>](../core/creating-ports.md)  
  
-   [<span data-ttu-id="cee32-114">如何配置虚拟目录</span><span class="sxs-lookup"><span data-stu-id="cee32-114">How to Configure the Virtual Directory</span></span>](../core/how-to-configure-the-virtual-directory.md)  
  
-   [<span data-ttu-id="cee32-115">如何配置 HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="cee32-115">How to Configure the HTTP Receive Adapter</span></span>](../core/how-to-configure-the-http-receive-adapter1.md)  
  
-   [<span data-ttu-id="cee32-116">运行业务流程</span><span class="sxs-lookup"><span data-stu-id="cee32-116">Running Orchestrations</span></span>](../core/running-orchestrations2.md)  
  
-   [<span data-ttu-id="cee32-117">运行 SSO 项目</span><span class="sxs-lookup"><span data-stu-id="cee32-117">Running SSO Projects</span></span>](../core/running-sso-projects1.md)