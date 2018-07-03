---
title: 如何删除已部署的项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], undeploying artifacts
- Remove-All command
- undeploying, artifacts [BAM]
- artifacts, undeploying [BAM]
ms.assetid: 90135965-d18e-4a71-9877-d2b0c3caf59f
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7008b327564de3af2462f0fa077ca456f817584
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968230"
---
# <a name="how-to-remove-deployed-artifacts"></a><span data-ttu-id="dc179-102">如何删除已部署的项目</span><span class="sxs-lookup"><span data-stu-id="dc179-102">How to Remove Deployed Artifacts</span></span>
<span data-ttu-id="dc179-103">管理员使用**删除全部**命令以删除 BAM 主导入数据库中部署的项目。</span><span class="sxs-lookup"><span data-stu-id="dc179-103">Administrators use the **remove-all** command to remove artifacts deployed in the BAM Primary Import database.</span></span> <span data-ttu-id="dc179-104">所提供的 BAM 定义为 XML 文件或 Excel 工作簿，其中包含有关要删除的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="dc179-104">The supplied BAM definition is either an XML file or an Excel Workbook containing information about the artifacts to be removed.</span></span>  
  
### <a name="to-remove-deployed-artifacts"></a><span data-ttu-id="dc179-105">删除已部署的项目</span><span class="sxs-lookup"><span data-stu-id="dc179-105">To remove deployed artifacts</span></span>  
  
1. <span data-ttu-id="dc179-106">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dc179-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="dc179-107">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="dc179-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="dc179-108">类型**bm 全部删除-DefinitionFile:\<def 文件\>**。</span><span class="sxs-lookup"><span data-stu-id="dc179-108">Type **bm remove-all -DefinitionFile:\<def file\>**.</span></span>  
  
4. <span data-ttu-id="dc179-109">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="dc179-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc179-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc179-110">See Also</span></span>  
 <span data-ttu-id="dc179-111">[如何向应用程序添加 BAM 项目](../core/how-to-add-a-bam-artifact-to-an-application.md) </span><span class="sxs-lookup"><span data-stu-id="dc179-111">[How to Add a BAM Artifact to an Application](../core/how-to-add-a-bam-artifact-to-an-application.md) </span></span>  
 <span data-ttu-id="dc179-112">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="dc179-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="dc179-113">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="dc179-113">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="dc179-114">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="dc179-114">BAM Management Utility</span></span>](../core/bam-management-utility.md)