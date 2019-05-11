---
title: 使用 SSO 来保护 JD Edwards OneWorld |Microsoft Docs
description: 在 BizTalk Server 中使用 Microsoft BizTalk 适配器 JD Edwards OneWorld 时的安全性概述
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: beb736a8-d95f-4d44-a882-2d437c4892f4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b44e203a614edf4fdf6fe1decd5862c5c33d3430
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279962"
---
# <a name="security-in-jd-edwards-oneworld"></a><span data-ttu-id="4a2f7-103">JD Edwards OneWorld 中的安全性</span><span class="sxs-lookup"><span data-stu-id="4a2f7-103">Security in JD Edwards OneWorld</span></span>

## <a name="overview"></a><span data-ttu-id="4a2f7-104">概述</span><span class="sxs-lookup"><span data-stu-id="4a2f7-104">Overview</span></span>
<span data-ttu-id="4a2f7-105">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供单一登录 (SSO) 支持。</span><span class="sxs-lookup"><span data-stu-id="4a2f7-105">Microsoft BizTalk Adapter for JD Edwards OneWorld provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="4a2f7-106">由企业单一登录工具创建的关联应用程序代表诸如 JD Edwards OneWorld 之类的服务器系统。</span><span class="sxs-lookup"><span data-stu-id="4a2f7-106">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as JD Edwards OneWorld.</span></span>  

<span data-ttu-id="4a2f7-107">本部分提供有关如何在安全环境中部署用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器的指南。</span><span class="sxs-lookup"><span data-stu-id="4a2f7-107">This section provides guidelines about how to deploy Microsoft BizTalk Adapter for JD Edwards OneWorld in a secure environment.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4a2f7-108">我们建议将用于 JD Edwards OneWorld 的 BizTalk 适配器使用限制给已授权用户，如客户端文件直接连接到业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="4a2f7-108">We recommended that you restrict the use of BizTalk Adapter for JD Edwards OneWorld to authorized users only, as the client files directly connect to the line-of-business applications.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="4a2f7-109">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4a2f7-109">Next steps</span></span>
  
-   [<span data-ttu-id="4a2f7-110">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="4a2f7-110">Requirements for Single Sign-On</span></span>](../core/requirements-for-single-sign-on5.md)  
  
-   [<span data-ttu-id="4a2f7-111">用于 JD Enterprise OneWorld 的单一登录和 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="4a2f7-111">Single Sign-On and BizTalk Adapter for JD Enterprise OneWorld</span></span>](../core/single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld.md)  
  
-   [<span data-ttu-id="4a2f7-112">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="4a2f7-112">Creating Affiliate Applications</span></span>](../core/creating-affiliate-applications3.md)  
  
-   [<span data-ttu-id="4a2f7-113">配置虚拟目录</span><span class="sxs-lookup"><span data-stu-id="4a2f7-113">Configuring the Virtual Directory</span></span>](../core/configuring-the-virtual-directory.md)  
  
-   [<span data-ttu-id="4a2f7-114">如何配置 HTTP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="4a2f7-114">How to Configure the HTTP Receive Adapter</span></span>](../core/how-to-configure-the-http-receive-adapter2.md)  
  
-   [<span data-ttu-id="4a2f7-115">创建发送和接收端口</span><span class="sxs-lookup"><span data-stu-id="4a2f7-115">Creating Send and Receive Ports</span></span>](../core/creating-send-and-receive-ports.md)  
  
-   [<span data-ttu-id="4a2f7-116">将架构导入 BizTalk Server 项目中</span><span class="sxs-lookup"><span data-stu-id="4a2f7-116">Importing Schemas into BizTalk Server Projects</span></span>](../core/importing-schemas-into-biztalk-server-projects1.md)  
  
-   [<span data-ttu-id="4a2f7-117">运行业务流程</span><span class="sxs-lookup"><span data-stu-id="4a2f7-117">Running Orchestrations</span></span>](../core/running-orchestrations1.md)  
  
-   [<span data-ttu-id="4a2f7-118">运行 SSO 项目</span><span class="sxs-lookup"><span data-stu-id="4a2f7-118">Running SSO Projects</span></span>](../core/running-sso-projects3.md)