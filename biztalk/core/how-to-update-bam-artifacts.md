---
title: 如何更新 BAM 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Update-All command [BAM]
- managing [BAM definitions], updating artifacts
- updating, artifacts
- artifacts, updating
ms.assetid: bc28159e-df51-499b-bd51-7b682b849891
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8bd9abbf0e466097744f6a02f7ae3aa0ccdf372
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383639"
---
# <a name="how-to-update-bam-artifacts"></a><span data-ttu-id="f8991-102">如何更新 BAM 项目</span><span class="sxs-lookup"><span data-stu-id="f8991-102">How to Update BAM Artifacts</span></span>
<span data-ttu-id="f8991-103">管理员使用**更新所有**命令以更新 BAM 主导入数据库中部署的项目。</span><span class="sxs-lookup"><span data-stu-id="f8991-103">Administrators use the **update-all** command to update artifacts deployed in the BAM Primary Import database.</span></span> <span data-ttu-id="f8991-104">提供的 BAM 定义是一个 XML 文件或 Excel 工作簿包含有关要更新的项目信息。</span><span class="sxs-lookup"><span data-stu-id="f8991-104">The supplied BAM definition is either an XML file or an Excel Workbook containing information about the artifacts to be updated.</span></span>  
  
### <a name="to-update-bam-artifacts"></a><span data-ttu-id="f8991-105">若要更新 BAM 项目</span><span class="sxs-lookup"><span data-stu-id="f8991-105">To update BAM Artifacts</span></span>  
  
1. <span data-ttu-id="f8991-106">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f8991-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="f8991-107">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。</span><span class="sxs-lookup"><span data-stu-id="f8991-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="f8991-108">类型**bm 更新全部-DefinitionFile:\<def 文件\>**。</span><span class="sxs-lookup"><span data-stu-id="f8991-108">Type **bm update-all -DefinitionFile:\<def file\>**.</span></span>  
  
4. <span data-ttu-id="f8991-109">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="f8991-109">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8991-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8991-110">See Also</span></span>  
 <span data-ttu-id="f8991-111">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="f8991-111">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="f8991-112">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="f8991-112">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="f8991-113">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="f8991-113">BAM Management Utility</span></span>](../core/bam-management-utility.md)