---
title: "如何列出 BAM 基础结构更改 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- definitions [BAM], listing infrastructure changes
- managing [BAM definitions], listing infrastructure changes
- Get-Changes command [BAM]
- infrastructure, listing changes [BAM]
ms.assetid: 3feacd7d-6f42-4626-835b-0dc3befc9fd6
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d0ed240f156d853c18f28a52022eea585af513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-list-changes-to-the-bam-infrastructure"></a><span data-ttu-id="efd16-102">如何列出对 BAM 基础结构的更改</span><span class="sxs-lookup"><span data-stu-id="efd16-102">How to List Changes to the BAM Infrastructure</span></span>
<span data-ttu-id="efd16-103">管理员使用**获取变更**命令 BAM 管理实用程序列出有关已部署的 BAM 定义的当前信息。</span><span class="sxs-lookup"><span data-stu-id="efd16-103">Administrators use the **get-changes** command of the BAM Management utility to list current information about a deployed BAM definition.</span></span> <span data-ttu-id="efd16-104">您还可以使用 get-changes 命令列出 BAM 主导入数据库中当前的部署项目。</span><span class="sxs-lookup"><span data-stu-id="efd16-104">You can also use the get-changes command to list current deployment artifacts in the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="efd16-105">这些信息包括成功的部署和取消部署、BAM 定义文件的名称、BAM 配置文件的名称、与定义文件相关的所有活动和视图的名称，以及应用了更改的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="efd16-105">The information includes successful deployments and undeployments, the name of the BAM definition file, the name of the BAM configuration file, the names of all activities and views associated with the definition file, and the user account that applied the change.</span></span> <span data-ttu-id="efd16-106">get-changes 列表显示部署和定义删除及其相关标识号。</span><span class="sxs-lookup"><span data-stu-id="efd16-106">The get-changes list shows deployments and definition removals with their associated identification numbers.</span></span>  
  
### <a name="to-list-changes-to-the-bam-definition"></a><span data-ttu-id="efd16-107">列出对 BAM 定义所做的更改</span><span class="sxs-lookup"><span data-stu-id="efd16-107">To list changes to the BAM definition</span></span>  
  
1.  <span data-ttu-id="efd16-108">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="efd16-108">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="efd16-109">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="efd16-109">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="efd16-110">类型**bm 获取变更。**</span><span class="sxs-lookup"><span data-stu-id="efd16-110">Type **bm get-changes.**</span></span>  
  
4.  <span data-ttu-id="efd16-111">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="efd16-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efd16-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efd16-112">See Also</span></span>  
 <span data-ttu-id="efd16-113">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="efd16-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="efd16-114">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="efd16-114">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="efd16-115">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="efd16-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)