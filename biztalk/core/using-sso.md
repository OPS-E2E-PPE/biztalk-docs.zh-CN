---
title: 使用 SSO |Microsoft Docs
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
ms.openlocfilehash: 4b4ad2e75e8d66f0563e9bda2996383ab294970d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321382"
---
# <a name="using-sso"></a><span data-ttu-id="5ae00-102">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="5ae00-102">Using SSO</span></span>
<span data-ttu-id="5ae00-103">可以使用 MMC 管理单元或命令行管理实用工具 (ssomanage) 来管理 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="5ae00-103">You can use either the MMC Snap-in or the command line management utility (ssomanage) to manage the SSO system.</span></span> <span data-ttu-id="5ae00-104">这包括活动，例如更新 SSO 数据库，添加、 删除和管理应用程序，以及管理用户映射。</span><span class="sxs-lookup"><span data-stu-id="5ae00-104">This includes activities such as updating the SSO database, adding, deleting, and managing applications, and administering user mappings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ae00-105">在系统上支持用户帐户控制 (UAC)，可能需要使用管理权限运行 SSO 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="5ae00-105">On a system that supports User Account Control (UAC), you may need to run the SSO command line tools with Administrative privileges.</span></span>  
  
 <span data-ttu-id="5ae00-106">只有单一登录管理员才可以执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="5ae00-106">Only Single Sign-On Administrators can perform these tasks.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ae00-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="5ae00-107">In This Section</span></span>  
  
-   [<span data-ttu-id="5ae00-108">如何设置 SSO 服务器</span><span class="sxs-lookup"><span data-stu-id="5ae00-108">How to Set the SSO Server</span></span>](../core/how-to-set-the-sso-server.md)  
  
-   [<span data-ttu-id="5ae00-109">如何启用 SSO</span><span class="sxs-lookup"><span data-stu-id="5ae00-109">How to Enable SSO</span></span>](../core/how-to-enable-sso.md)  
  
-   [<span data-ttu-id="5ae00-110">如何更改主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="5ae00-110">How to Change the Master Secret Server</span></span>](../core/how-to-change-the-master-secret-server.md)  
  
-   [<span data-ttu-id="5ae00-111">如何禁用 SSO</span><span class="sxs-lookup"><span data-stu-id="5ae00-111">How to Disable SSO</span></span>](../core/how-to-disable-sso.md)  
  
-   [<span data-ttu-id="5ae00-112">如何更新 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="5ae00-112">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)  
  
-   [<span data-ttu-id="5ae00-113">如何显示 SSO 数据库信息</span><span class="sxs-lookup"><span data-stu-id="5ae00-113">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
-   [<span data-ttu-id="5ae00-114">如何配置 SSO 票证</span><span class="sxs-lookup"><span data-stu-id="5ae00-114">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)  
  
-   [<span data-ttu-id="5ae00-115">如何审核 SSO</span><span class="sxs-lookup"><span data-stu-id="5ae00-115">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  
  
-   [<span data-ttu-id="5ae00-116">如何为 SSO 启用 SSL</span><span class="sxs-lookup"><span data-stu-id="5ae00-116">How to Enable SSL for SSO</span></span>](../core/how-to-enable-ssl-for-sso.md)  
  
-   [<span data-ttu-id="5ae00-117">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="5ae00-117">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  
  
-   [<span data-ttu-id="5ae00-118">如何指定 SSO 管理员和关联管理员帐户</span><span class="sxs-lookup"><span data-stu-id="5ae00-118">How to Specify SSO Administrators and Affiliate Administrators Accounts</span></span>](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md)  
  
-   [<span data-ttu-id="5ae00-119">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="5ae00-119">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)  
  
-   [<span data-ttu-id="5ae00-120">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="5ae00-120">Managing User Mappings</span></span>](../core/managing-user-mappings.md)  
  
-   [<span data-ttu-id="5ae00-121">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="5ae00-121">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)