---
title: 使用 SSO 来保护 TIBCO EMS |Microsoft Docs
description: 使用 BizTalk Server 中的 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器时的安全性概述
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eccb44b-e9d8-42c2-a575-47f1d1cfe93c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ec373526a8e436b21614acab22cb9d2120936f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280287"
---
# <a name="security-in-biztalk-adapter-for-tibco-ems"></a><span data-ttu-id="e733b-103">用于 TIBCO EMS 的 BizTalk 适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="e733b-103">Security in BizTalk Adapter for TIBCO EMS</span></span>

## <a name="overview"></a><span data-ttu-id="e733b-104">概述</span><span class="sxs-lookup"><span data-stu-id="e733b-104">Overview</span></span>
<span data-ttu-id="e733b-105">用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器提供单一登录 (SSO) 支持。</span><span class="sxs-lookup"><span data-stu-id="e733b-105">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="e733b-106">由企业单一登录工具创建的关联应用程序代表诸如 TIBCO Enterprise Message Service 之类的服务器系统。</span><span class="sxs-lookup"><span data-stu-id="e733b-106">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as TIBCO Enterprise Message Service.</span></span>  

<span data-ttu-id="e733b-107">此部分指导如何在安全环境中部署用于 TIBCO Enterprise Message Service 的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="e733b-107">This section provides guidelines on how to deploy BizTalk Adapter for TIBCO Enterprise Message Service in a secure environment.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e733b-108">强烈建议将用于 Enterprise Message Service 的 BizTalk 适配器使用限制给已授权用户，如客户端文件直接连接到业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="e733b-108">It is highly recommended that you restrict the use of BizTalk Adapter for Enterprise Message Service to authorized users only, as the client files directly connect to the line-of-business applications.</span></span>    

  
## <a name="next-steps"></a><span data-ttu-id="e733b-109">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e733b-109">Next steps</span></span>
  
-   [<span data-ttu-id="e733b-110">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="e733b-110">Requirements for Single Sign-On</span></span>](../core/requirements-for-single-sign-on4.md)  
  
-   [<span data-ttu-id="e733b-111">用于 TIBCO Enterprise Message Service 的单一登录和 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="e733b-111">Single Sign-On and BizTalk Adapter for TIBCO Enterprise Message Service</span></span>](../core/single-sign-on-and-biztalk-adapter-for-tibco-enterprise-message-service.md)  
  
-   [<span data-ttu-id="e733b-112">创建关联应用程序</span><span class="sxs-lookup"><span data-stu-id="e733b-112">Creating Affiliate Applications</span></span>](../core/creating-affiliate-applications5.md)  
  
-   [<span data-ttu-id="e733b-113">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="e733b-113">Creating Send Ports</span></span>](../core/creating-send-ports1.md)  
  
-   [<span data-ttu-id="e733b-114">运行 SSO 项目</span><span class="sxs-lookup"><span data-stu-id="e733b-114">Running SSO Projects</span></span>](../core/running-sso-projects2.md)