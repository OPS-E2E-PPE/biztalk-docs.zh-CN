---
title: 实现企业单一登录 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- EAI
- 64-bit environments, SSO support
- SSO, 64-bit support
- SSO
- SSO, service accounts
ms.assetid: 155a62fc-5dc5-4aee-9602-b970067c1bf2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfd4aaf39456c68c744384aa05ff5664e781aa3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256461"
---
# <a name="implementing-enterprise-single-sign-on"></a><span data-ttu-id="61df8-102">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="61df8-102">Implementing Enterprise Single Sign-On</span></span>
<span data-ttu-id="61df8-103">企业单一登录 (SSO) 提供的相关服务可使企业应用程序集成 (EAI) 解决方案的最终用户能够使用单一登录。</span><span class="sxs-lookup"><span data-stu-id="61df8-103">Enterprise Single Sign-On (SSO) provides services to enable single sign-on to end users for enterprise application integration (EAI) solutions.</span></span> <span data-ttu-id="61df8-104">SSO 系统将 Microsoft Windows 帐户映射到后端凭据。</span><span class="sxs-lookup"><span data-stu-id="61df8-104">The SSO system maps Microsoft Windows accounts to back-end credentials.</span></span> <span data-ttu-id="61df8-105">对于用户和管理员来说，SSO 简化了对用户 ID 和密码的管理。</span><span class="sxs-lookup"><span data-stu-id="61df8-105">SSO simplifies the management of user IDs and passwords, both for users and administrators.</span></span> <span data-ttu-id="61df8-106">使用 SSO，用户只需登录 Windows 网络一次，即可访问后端系统和应用程序。</span><span class="sxs-lookup"><span data-stu-id="61df8-106">It enables users to access back-end systems and applications by logging on only once to the Windows network.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61df8-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="61df8-107">In This Section</span></span>  
  
-   [<span data-ttu-id="61df8-108">了解 SSO</span><span class="sxs-lookup"><span data-stu-id="61df8-108">Understanding SSO</span></span>](../core/understanding-sso.md)  
  
-   [<span data-ttu-id="61df8-109">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="61df8-109">Installing SSO</span></span>](../core/installing-sso.md)  
  
-   [<span data-ttu-id="61df8-110">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="61df8-110">Using SSO</span></span>](../core/using-sso.md)  
  
-   [<span data-ttu-id="61df8-111">保护你的部署的 SSO</span><span class="sxs-lookup"><span data-stu-id="61df8-111">Securing Your Deployment of SSO</span></span>](../core/securing-your-deployment-of-sso.md)  
  
-   [<span data-ttu-id="61df8-112">密码同步</span><span class="sxs-lookup"><span data-stu-id="61df8-112">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   [<span data-ttu-id="61df8-113">SSO 安全建议</span><span class="sxs-lookup"><span data-stu-id="61df8-113">SSO Security Recommendations</span></span>](../core/sso-security-recommendations.md)