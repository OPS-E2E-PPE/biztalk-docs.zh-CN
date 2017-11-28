---
title: "管理 Windows 组和用户帐户的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, Windows groups
- authenticating, best practices
- Windows groups, security
- best practices, user accounts
- best practices, security
- security, best practices
- user accounts, security
- authenticating, security
- Windows groups, best practices
- best practices, authenticating
- user accounts, best practices
- hosts, security
- hosts, best practices
- best practices, hosts
ms.assetid: 0c4a141e-97ce-434a-8e45-a56c634bbd6c
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71f7560e3867bf290f20e0f2f49a740d7298131b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-managing-windows-groups-and-user-accounts"></a><span data-ttu-id="d0a4f-102">管理 Windows 组和用户帐户的最佳实践</span><span class="sxs-lookup"><span data-stu-id="d0a4f-102">Best Practices for Managing Windows Groups and User Accounts</span></span>
<span data-ttu-id="d0a4f-103">本部分包含了管理 Windows 组和用户帐户的安全性时的最佳实践和提示。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-103">This section contains best practices and tips for managing security for Windows groups and user accounts.</span></span>  
  
-   <span data-ttu-id="d0a4f-104">**使用服务帐户与主机实例所需的最小权限**</span><span class="sxs-lookup"><span data-stu-id="d0a4f-104">**Use service accounts with minimum privileges necessary for host instances**</span></span>  
  
     <span data-ttu-id="d0a4f-105">为了确保 BizTalk Server 环境的安全性，建议您使用具有运行主机实例时所需的最低权限的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-105">To help ensure the security of your BizTalk Server environment, we recommend that you use service accounts with the minimum privileges necessary to run host instances.</span></span> <span data-ttu-id="d0a4f-106">有关服务帐户要求的最小特权的详细信息，请参阅[访问控制和数据安全](../core/access-control-and-data-security.md)。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-106">For more information about the minimum privileges that service accounts require, see [Access Control and Data Security](../core/access-control-and-data-security.md).</span></span>  
  
-   <span data-ttu-id="d0a4f-107">**使用不同的用户组来指定受信任的身份验证和非受信任的主机**</span><span class="sxs-lookup"><span data-stu-id="d0a4f-107">**Use different user groups for authentication trusted and non-trusted hosts**</span></span>  
  
     <span data-ttu-id="d0a4f-108">为了确保不受信任验证主机比受信任验证主机拥有更少的权限，每个主机必须使用不同的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-108">To ensure that non-authentication trusted hosts have fewer privileges than authentication trusted hosts, you must use different service accounts for each host.</span></span>  
  
-   <span data-ttu-id="d0a4f-109">**为每个 BizTalk 主机使用不同的用户组**</span><span class="sxs-lookup"><span data-stu-id="d0a4f-109">**Use a different user group for each BizTalk Host**</span></span>  
  
     <span data-ttu-id="d0a4f-110">为了使各主机间的安全边界最大，建议对 BizTalk 组中每个 BizTalk 主机使用不同的 Windows 用户组。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-110">To maximize the security boundary between hosts, we recommend that you use a different Windows user group for each BizTalk Host in your BizTalk group.</span></span>  
  
-   <span data-ttu-id="d0a4f-111">**从 BizTalk Server Administrators 组中删除安装用户**</span><span class="sxs-lookup"><span data-stu-id="d0a4f-111">**Remove the installation user from the BizTalk Server Administrators group**</span></span>  
  
     <span data-ttu-id="d0a4f-112">在具有本地组的单台计算机上安装 BizTalk Server 时，系统会自动将执行 BizTalk Server 交互式安装的用户添加到 BizTalk Server Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-112">When you install BizTalk Server on a single computer with local groups, the user performing an interactive installation of BizTalk Server is automatically added to the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d0a4f-113">这使该用户可以使用配置管理器来配置 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-113">This allows that user to configure BizTalk Server with the Configuration Manager.</span></span>  
  
     <span data-ttu-id="d0a4f-114">如果安装 BizTalk Server 的用户将来不需要对 BizTalk Server 进行管理，则建议在配置完 BizTalk Server 之后将该用户从 BizTalk Server Administrators 组中删除。</span><span class="sxs-lookup"><span data-stu-id="d0a4f-114">If the user who installs BizTalk Server will not be administering BizTalk Server, we recommend that you remove this user from the BizTalk Server Administrators group after BizTalk Server is configured.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0a4f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0a4f-115">See Also</span></span>  
 [<span data-ttu-id="d0a4f-116">管理 BizTalk Server 安全性</span><span class="sxs-lookup"><span data-stu-id="d0a4f-116">Managing BizTalk Server Security</span></span>](../core/managing-biztalk-server-security.md)