---
title: "如何删除已部署的项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], undeploying artifacts
- Remove-All command
- undeploying, artifacts [BAM]
- artifacts, undeploying [BAM]
ms.assetid: 90135965-d18e-4a71-9877-d2b0c3caf59f
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1d3e395223840dd4caa534130061fac33e89b78
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-remove-deployed-artifacts"></a><span data-ttu-id="9ab10-102">如何删除已部署的项目</span><span class="sxs-lookup"><span data-stu-id="9ab10-102">How to Remove Deployed Artifacts</span></span>
<span data-ttu-id="9ab10-103">管理员使用**删除所有**命令，以删除部署 BAM 主导入数据库中的项目。</span><span class="sxs-lookup"><span data-stu-id="9ab10-103">Administrators use the **remove-all** command to remove artifacts deployed in the BAM Primary Import database.</span></span> <span data-ttu-id="9ab10-104">所提供的 BAM 定义为 XML 文件或 Excel 工作簿，其中包含有关要删除的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="9ab10-104">The supplied BAM definition is either an XML file or an Excel Workbook containing information about the artifacts to be removed.</span></span>  
  
### <a name="to-remove-deployed-artifacts"></a><span data-ttu-id="9ab10-105">删除已部署的项目</span><span class="sxs-lookup"><span data-stu-id="9ab10-105">To remove deployed artifacts</span></span>  
  
1.  <span data-ttu-id="9ab10-106">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9ab10-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="9ab10-107">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="9ab10-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="9ab10-108">类型**bm 删除全部-DefinitionFile:\<def 文件\>**。</span><span class="sxs-lookup"><span data-stu-id="9ab10-108">Type **bm remove-all -DefinitionFile:\<def file\>**.</span></span>  
  
4.  <span data-ttu-id="9ab10-109">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="9ab10-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab10-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ab10-110">See Also</span></span>  
 <span data-ttu-id="9ab10-111">[如何将一个 BAM 项目添加到应用程序](../core/how-to-add-a-bam-artifact-to-an-application.md) </span><span class="sxs-lookup"><span data-stu-id="9ab10-111">[How to Add a BAM Artifact to an Application](../core/how-to-add-a-bam-artifact-to-an-application.md) </span></span>  
 <span data-ttu-id="9ab10-112">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="9ab10-112">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="9ab10-113">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="9ab10-113">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="9ab10-114">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="9ab10-114">BAM Management Utility</span></span>](../core/bam-management-utility.md)