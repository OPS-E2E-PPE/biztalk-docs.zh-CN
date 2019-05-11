---
title: 实现企业单一登录 |Microsoft Docs
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
ms.openlocfilehash: e7dfd1c2a21bcbb5bfe1e7befe299540e59e7526
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382596"
---
# <a name="implementing-enterprise-single-sign-on"></a><span data-ttu-id="4f491-102">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="4f491-102">Implementing Enterprise Single Sign-On</span></span>
<span data-ttu-id="4f491-103">企业单一登录 (SSO) 提供服务，以启用单一登录到企业应用程序集成 (EAI) 解决方案的最终用户。</span><span class="sxs-lookup"><span data-stu-id="4f491-103">Enterprise Single Sign-On (SSO) provides services to enable single sign-on to end users for enterprise application integration (EAI) solutions.</span></span> <span data-ttu-id="4f491-104">SSO 系统将 Microsoft Windows 帐户映射到后端凭据。</span><span class="sxs-lookup"><span data-stu-id="4f491-104">The SSO system maps Microsoft Windows accounts to back-end credentials.</span></span> <span data-ttu-id="4f491-105">SSO 简化了管理用户 Id 和密码，同时为用户和管理员。</span><span class="sxs-lookup"><span data-stu-id="4f491-105">SSO simplifies the management of user IDs and passwords, both for users and administrators.</span></span> <span data-ttu-id="4f491-106">它使用户能够登录到 Windows 网络仅一次访问后端系统和应用程序。</span><span class="sxs-lookup"><span data-stu-id="4f491-106">It enables users to access back-end systems and applications by logging on only once to the Windows network.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4f491-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="4f491-107">In This Section</span></span>  
  
-   [<span data-ttu-id="4f491-108">了解 SSO</span><span class="sxs-lookup"><span data-stu-id="4f491-108">Understanding SSO</span></span>](../core/understanding-sso.md)  
  
-   [<span data-ttu-id="4f491-109">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="4f491-109">Installing SSO</span></span>](../core/installing-sso.md)  
  
-   [<span data-ttu-id="4f491-110">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="4f491-110">Using SSO</span></span>](../core/using-sso.md)  
  
-   [<span data-ttu-id="4f491-111">确保 SSO 部署的安全</span><span class="sxs-lookup"><span data-stu-id="4f491-111">Securing Your Deployment of SSO</span></span>](../core/securing-your-deployment-of-sso.md)  
  
-   [<span data-ttu-id="4f491-112">密码同步</span><span class="sxs-lookup"><span data-stu-id="4f491-112">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   [<span data-ttu-id="4f491-113">SSO 安全建议</span><span class="sxs-lookup"><span data-stu-id="4f491-113">SSO Security Recommendations</span></span>](../core/sso-security-recommendations.md)