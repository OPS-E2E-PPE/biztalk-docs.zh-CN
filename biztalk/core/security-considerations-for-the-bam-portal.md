---
title: BAM 门户的安全注意事项 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal, security
- BAM portal, administrator accounts
- user accounts, BAM
- administrator accounts, BAM portal
- BAM portal, user accounts
- security, BAM portal
ms.assetid: 5c8e6034-dfb8-4dba-b040-0c19504abdb2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b0f5220eba5b66daf41dffc7ab74f93df8bb509
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269381"
---
# <a name="security-considerations-for-the-bam-portal"></a><span data-ttu-id="3bb2e-102">BAM 门户的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="3bb2e-102">Security Considerations for the BAM Portal</span></span>
<span data-ttu-id="3bb2e-103">遵循最小权限原则，用户帐户在 BAM 门户中应使用受限制的权限来执行日常的任务。</span><span class="sxs-lookup"><span data-stu-id="3bb2e-103">Using the principle of least privilege, user accounts should have restrictive permissions to perform routine tasks in the BAM portal.</span></span> <span data-ttu-id="3bb2e-104">在设置 BAM 的用户帐户时请记住以下几点，通过适当的用户访问权限来平衡安全性。</span><span class="sxs-lookup"><span data-stu-id="3bb2e-104">Keep the following points in mind as you set up your user accounts for BAM to balance security with appropriate access for users.</span></span>  
  
## <a name="user-accounts"></a><span data-ttu-id="3bb2e-105">用户帐户</span><span class="sxs-lookup"><span data-stu-id="3bb2e-105">User accounts</span></span>  
 <span data-ttu-id="3bb2e-106">使用最小权限的用户帐户不能使用 BAM 门户分布式的 navigationfeature。</span><span class="sxs-lookup"><span data-stu-id="3bb2e-106">User accounts with minimum permissions are not able to use the BAM portal distributed navigationfeature.</span></span> <span data-ttu-id="3bb2e-107">要使用此功能，必须授予这些帐户足够的权限，使其不仅可以访问本地计算机上的 Web Services，也能够访问远程计算机上的 Web Services。</span><span class="sxs-lookup"><span data-stu-id="3bb2e-107">To be able to use this feature, these accounts must have sufficient permissions to allow access to the Web services on the remote computer as well as on the local computer.</span></span>  
  
 <span data-ttu-id="3bb2e-108">BAM Web Services 的用户帐户必须具有访问所有引用的数据库的权限，并且在引用的数据库中必须是 BAM_ManagementWS 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="3bb2e-108">User accounts for the BAM Web services must have permissions to access all referenced databases and must be a member of the BAM_ManagementWS role in the referenced databases.</span></span>  
  
 <span data-ttu-id="3bb2e-109">对于下面的用户类型，应注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="3bb2e-109">For the following user types, you should be aware of these considerations:</span></span>  
  
-   <span data-ttu-id="3bb2e-110">域用户必须具有对要访问的主导入数据库的宿主远程计算机的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3bb2e-110">Domain Users, must have access permissions on remote computers that host Primary Import databases that are being accessed.</span></span>  
  
-   <span data-ttu-id="3bb2e-111">指定为“本地用户”角色的用户无法使用分布式导航。</span><span class="sxs-lookup"><span data-stu-id="3bb2e-111">Users who are assigned Local User role, cannot use distributed navigation.</span></span>  
  
## <a name="administrator-accounts"></a><span data-ttu-id="3bb2e-112">管理员帐户</span><span class="sxs-lookup"><span data-stu-id="3bb2e-112">Administrator accounts</span></span>  
 <span data-ttu-id="3bb2e-113">管理员必须是 securityadmin 或 sysadmin 组的成员，才能授予域用户权限。</span><span class="sxs-lookup"><span data-stu-id="3bb2e-113">Administrators must be members of the securityadmin or sysadmin groups to grant permissions to domain users.</span></span>  
  
 <span data-ttu-id="3bb2e-114">要运行 BAM 管理实用程序，您必须至少是 BAM 数据库的数据库操作员。</span><span class="sxs-lookup"><span data-stu-id="3bb2e-114">To run the BAM Management utility, you must be at least a database operator for the BAM databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb2e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bb2e-115">See Also</span></span>  
 [<span data-ttu-id="3bb2e-116">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="3bb2e-116">BAM Portal</span></span>](../core/bam-portal.md)