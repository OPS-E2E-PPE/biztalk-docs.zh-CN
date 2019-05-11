---
title: 有关 BAM 门户的安全注意事项 |Microsoft Docs
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
ms.openlocfilehash: 22aa95167640482ccd2e00dfbfd98b0a323da1a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280312"
---
# <a name="security-considerations-for-the-bam-portal"></a><span data-ttu-id="18dc8-102">有关 BAM 门户的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="18dc8-102">Security Considerations for the BAM Portal</span></span>
<span data-ttu-id="18dc8-103">使用最小特权原则，用户帐户应具有限制性的权限在 BAM 门户中执行日常任务。</span><span class="sxs-lookup"><span data-stu-id="18dc8-103">Using the principle of least privilege, user accounts should have restrictive permissions to perform routine tasks in the BAM portal.</span></span> <span data-ttu-id="18dc8-104">请设置 BAM 来平衡安全性具有适当访问权限的用户的用户帐户时注意以下几点。</span><span class="sxs-lookup"><span data-stu-id="18dc8-104">Keep the following points in mind as you set up your user accounts for BAM to balance security with appropriate access for users.</span></span>  
  
## <a name="user-accounts"></a><span data-ttu-id="18dc8-105">用户帐户</span><span class="sxs-lookup"><span data-stu-id="18dc8-105">User accounts</span></span>  
 <span data-ttu-id="18dc8-106">不能使用 BAM 门户分布式的 navigationfeature 具有最低权限的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="18dc8-106">User accounts with minimum permissions are not able to use the BAM portal distributed navigationfeature.</span></span> <span data-ttu-id="18dc8-107">若要能够使用此功能，这些帐户必须具有足够权限以允许对 Web 服务的访问，远程计算机上以及在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="18dc8-107">To be able to use this feature, these accounts must have sufficient permissions to allow access to the Web services on the remote computer as well as on the local computer.</span></span>  
  
 <span data-ttu-id="18dc8-108">BAM Web services 的用户帐户必须有权访问所有引用的数据库，并且必须被引用数据库中的 BAM_ManagementWS 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="18dc8-108">User accounts for the BAM Web services must have permissions to access all referenced databases and must be a member of the BAM_ManagementWS role in the referenced databases.</span></span>  
  
 <span data-ttu-id="18dc8-109">对于以下用户类型，您应注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="18dc8-109">For the following user types, you should be aware of these considerations:</span></span>  
  
-   <span data-ttu-id="18dc8-110">域用户，必须在远程计算机上正在访问该主机主导入数据库具有访问权限。</span><span class="sxs-lookup"><span data-stu-id="18dc8-110">Domain Users, must have access permissions on remote computers that host Primary Import databases that are being accessed.</span></span>  
  
-   <span data-ttu-id="18dc8-111">分配本地用户角色的用户不能使用分布式的导航。</span><span class="sxs-lookup"><span data-stu-id="18dc8-111">Users who are assigned Local User role, cannot use distributed navigation.</span></span>  
  
## <a name="administrator-accounts"></a><span data-ttu-id="18dc8-112">管理员帐户</span><span class="sxs-lookup"><span data-stu-id="18dc8-112">Administrator accounts</span></span>  
 <span data-ttu-id="18dc8-113">管理员必须是 securityadmin 或 sysadmin 组的成员的域用户授予权限。</span><span class="sxs-lookup"><span data-stu-id="18dc8-113">Administrators must be members of the securityadmin or sysadmin groups to grant permissions to domain users.</span></span>  
  
 <span data-ttu-id="18dc8-114">若要运行 BAM 管理实用程序，您必须是 BAM 数据库的至少一个数据库运算符。</span><span class="sxs-lookup"><span data-stu-id="18dc8-114">To run the BAM Management utility, you must be at least a database operator for the BAM databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18dc8-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="18dc8-115">See Also</span></span>  
 [<span data-ttu-id="18dc8-116">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="18dc8-116">BAM Portal</span></span>](../core/bam-portal.md)