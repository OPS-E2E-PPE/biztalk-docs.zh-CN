---
title: 如何列出对 BAM 基础结构的更改 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definitions [BAM], listing infrastructure changes
- managing [BAM definitions], listing infrastructure changes
- Get-Changes command [BAM]
- infrastructure, listing changes [BAM]
ms.assetid: 3feacd7d-6f42-4626-835b-0dc3befc9fd6
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bb796c7572e00c0a66cf89eb61035a46ac361c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336880"
---
# <a name="how-to-list-changes-to-the-bam-infrastructure"></a><span data-ttu-id="09c13-102">如何列出对 BAM 基础结构的更改</span><span class="sxs-lookup"><span data-stu-id="09c13-102">How to List Changes to the BAM Infrastructure</span></span>
<span data-ttu-id="09c13-103">管理员使用**get 更改**列出有关已部署的 BAM 定义的当前信息，BAM 管理实用程序的命令。</span><span class="sxs-lookup"><span data-stu-id="09c13-103">Administrators use the **get-changes** command of the BAM Management utility to list current information about a deployed BAM definition.</span></span> <span data-ttu-id="09c13-104">您还可以使用 get-changes 命令列出当前 BAM 主导入数据库中的部署项目。</span><span class="sxs-lookup"><span data-stu-id="09c13-104">You can also use the get-changes command to list current deployment artifacts in the BAM Primary Import database.</span></span>  
  
 <span data-ttu-id="09c13-105">这些信息包括成功的部署和取消部署的服务、 BAM 定义文件的名称、 BAM 配置文件的名称、 所有活动和视图的定义文件，并应用了更改的用户帐户与关联的名称。</span><span class="sxs-lookup"><span data-stu-id="09c13-105">The information includes successful deployments and undeployments, the name of the BAM definition file, the name of the BAM configuration file, the names of all activities and views associated with the definition file, and the user account that applied the change.</span></span> <span data-ttu-id="09c13-106">Get-changes 列表显示了部署和定义删除及其关联的标识号。</span><span class="sxs-lookup"><span data-stu-id="09c13-106">The get-changes list shows deployments and definition removals with their associated identification numbers.</span></span>  
  
### <a name="to-list-changes-to-the-bam-definition"></a><span data-ttu-id="09c13-107">列出对 BAM 定义的更改</span><span class="sxs-lookup"><span data-stu-id="09c13-107">To list changes to the BAM definition</span></span>  
  
1. <span data-ttu-id="09c13-108">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="09c13-108">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="09c13-109">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。</span><span class="sxs-lookup"><span data-stu-id="09c13-109">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="09c13-110">类型**bm 获取更改。**</span><span class="sxs-lookup"><span data-stu-id="09c13-110">Type **bm get-changes.**</span></span>  
  
4. <span data-ttu-id="09c13-111">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="09c13-111">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09c13-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="09c13-112">See Also</span></span>  
 <span data-ttu-id="09c13-113">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="09c13-113">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="09c13-114">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="09c13-114">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="09c13-115">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="09c13-115">BAM Management Utility</span></span>](../core/bam-management-utility.md)