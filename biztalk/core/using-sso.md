---
title: 使用 SSO |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO]
- SSO, managing
ms.assetid: e7245632-9c71-4b1f-836d-a4ea1dd6e5ee
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 850425f140b526baf251568f09ab47db9115e8ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287813"
---
# <a name="using-sso"></a><span data-ttu-id="14092-102">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="14092-102">Using SSO</span></span>
<span data-ttu-id="14092-103">您可以使用 MMC 管理单元或命令行管理实用工具 (ssomanage) 来管理 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="14092-103">You can use either the MMC Snap-in or the command line management utility (ssomanage) to manage the SSO system.</span></span> <span data-ttu-id="14092-104">其中的活动包括：更新 SSO 数据库，添加、删除和管理应用程序，以及管理用户映射。</span><span class="sxs-lookup"><span data-stu-id="14092-104">This includes activities such as updating the SSO database, adding, deleting, and managing applications, and administering user mappings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14092-105">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行 SSO 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="14092-105">On a system that supports User Account Control (UAC), you may need to run the SSO command line tools with Administrative privileges.</span></span>  
  
 <span data-ttu-id="14092-106">只有单一登录管理员才可以执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="14092-106">Only Single Sign-On Administrators can perform these tasks.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14092-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="14092-107">In This Section</span></span>  
  
-   [<span data-ttu-id="14092-108">如何设置 SSO 服务器</span><span class="sxs-lookup"><span data-stu-id="14092-108">How to Set the SSO Server</span></span>](../core/how-to-set-the-sso-server.md)  
  
-   [<span data-ttu-id="14092-109">如何启用 SSO</span><span class="sxs-lookup"><span data-stu-id="14092-109">How to Enable SSO</span></span>](../core/how-to-enable-sso.md)  
  
-   [<span data-ttu-id="14092-110">如何更改主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="14092-110">How to Change the Master Secret Server</span></span>](../core/how-to-change-the-master-secret-server.md)  
  
-   [<span data-ttu-id="14092-111">如何禁用 SSO</span><span class="sxs-lookup"><span data-stu-id="14092-111">How to Disable SSO</span></span>](../core/how-to-disable-sso.md)  
  
-   [<span data-ttu-id="14092-112">如何更新 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="14092-112">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)  
  
-   [<span data-ttu-id="14092-113">如何显示的 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="14092-113">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
-   [<span data-ttu-id="14092-114">如何配置 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="14092-114">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)  
  
-   [<span data-ttu-id="14092-115">如何审核 SSO</span><span class="sxs-lookup"><span data-stu-id="14092-115">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  
  
-   [<span data-ttu-id="14092-116">如何启用 SSO 的 SSL</span><span class="sxs-lookup"><span data-stu-id="14092-116">How to Enable SSL for SSO</span></span>](../core/how-to-enable-ssl-for-sso.md)  
  
-   [<span data-ttu-id="14092-117">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="14092-117">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  
  
-   [<span data-ttu-id="14092-118">如何指定 SSO Administrators 和 Affiliate Administrators 帐户</span><span class="sxs-lookup"><span data-stu-id="14092-118">How to Specify SSO Administrators and Affiliate Administrators Accounts</span></span>](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md)  
  
-   [<span data-ttu-id="14092-119">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="14092-119">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)  
  
-   [<span data-ttu-id="14092-120">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="14092-120">Managing User Mappings</span></span>](../core/managing-user-mappings.md)  
  
-   [<span data-ttu-id="14092-121">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="14092-121">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)