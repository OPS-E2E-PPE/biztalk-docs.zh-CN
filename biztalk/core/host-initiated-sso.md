---
title: "主机启动的 SSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host initiated SSO
- SSO, SSO database
- SSO, host initiated
- managing [SSO], host intitiated
ms.assetid: 492f730d-08ec-47d6-a88b-0d373bd8912b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 136ed2555410187a98960d6671c0c960aeebdd04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="host-initiated-sso"></a><span data-ttu-id="ec147-102">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="ec147-102">Host Initiated SSO</span></span>
<span data-ttu-id="ec147-103">使用主机启动的单一登录，来自主机系统的请求可以访问 Windows 系统中的资源。</span><span class="sxs-lookup"><span data-stu-id="ec147-103">Host initiated Single Sign-On enables a request from the host system to access a resource on a Windows system.</span></span> <span data-ttu-id="ec147-104">主机系统（例如 RACF 帐户）存在于非 Windows 环境和非 Windows 用户的上下文中。</span><span class="sxs-lookup"><span data-stu-id="ec147-104">The host system (for example, a RACF account) exists in a non-Windows environment and under the context of a non-Windows user.</span></span> <span data-ttu-id="ec147-105">单一登录凭据存储可将主机帐户映射到 Windows 帐户，以便允许此访问。</span><span class="sxs-lookup"><span data-stu-id="ec147-105">The Single Sign-On Credential Store maps host accounts to Windows accounts, enabling this access.</span></span>  
  
 <span data-ttu-id="ec147-106">以下主题对特定于主机启动的 SSO 的配置进行了说明：</span><span class="sxs-lookup"><span data-stu-id="ec147-106">The following topics describe configuration specific to Host initiated SSO.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec147-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="ec147-107">In This Section</span></span>  
  
-   [<span data-ttu-id="ec147-108">如何配置主机的要求启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="ec147-108">How to Configure Requirements for Host Initiated SSO</span></span>](../core/how-to-configure-requirements-for-host-initiated-sso.md)  
  
-   [<span data-ttu-id="ec147-109">如何启用和禁用主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="ec147-109">How to Enable and Disable Host Initiated SSO</span></span>](../core/how-to-enable-and-disable-host-initiated-sso.md)  
  
-   [<span data-ttu-id="ec147-110">如何创建关联应用程序为主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="ec147-110">How to Create Affiliate Applications for Host Initiated SSO</span></span>](../core/how-to-create-affiliate-applications-for-host-initiated-sso.md)  
  
-   [<span data-ttu-id="ec147-111">验证密码为主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="ec147-111">Validating Passwords for Host Initiated SSO</span></span>](../core/validating-passwords-for-host-initiated-sso.md)  
  
-   [<span data-ttu-id="ec147-112">如何管理用户映射为主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="ec147-112">How to Manage User Mappings for Host Initiated SSO</span></span>](../core/how-to-manage-user-mappings-for-host-initiated-sso.md)  
  
-   [<span data-ttu-id="ec147-113">如何在主机上使用跟踪实用程序启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="ec147-113">How to Use the Trace Utility in Host Initiated SSO</span></span>](../core/how-to-use-the-trace-utility-in-host-initiated-sso.md)