---
title: 如何引用其他 BAM 主导入数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea80b32c-f2cb-4aca-89f4-d5b72e1ba021
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5c4d298f3dffa2722d7dc929bf69eb2e6024f1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335199"
---
# <a name="how-to-reference-additional-bam-primary-import-databases"></a><span data-ttu-id="990a7-102">如何引用其他 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="990a7-102">How to Reference Additional BAM Primary Import Databases</span></span>
<span data-ttu-id="990a7-103">管理员使用**启用引用**命令引用其他 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="990a7-103">Administrators use the **enable-reference** command to reference additional BAM Primary Import databases.</span></span> <span data-ttu-id="990a7-104">引用多个 BAM 主导入数据库，以便查看分布式的 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="990a7-104">You reference multiple BAM Primary Import databases to facilitate viewing distributed BAM activities.</span></span>  
  
### <a name="to-enable-a-reference-to-an-additional-bam-primary-import-database"></a><span data-ttu-id="990a7-105">若要启用对其他 BAM 主导入数据库的引用</span><span class="sxs-lookup"><span data-stu-id="990a7-105">To enable a reference to an additional BAM Primary Import database</span></span>  
  
1. <span data-ttu-id="990a7-106">打开命令提示符，如下所示：单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="990a7-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="990a7-107">导航到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]跟踪。</span><span class="sxs-lookup"><span data-stu-id="990a7-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="990a7-108">在命令行提示符下键入以下内容： **bm 启用引用-TargetServer:\<目标服务器\>-TargetDatabase:\<目标数据库\>**，其中\<*目标服务器*\>替换为在其通过将指定的目标 BAM 主导入数据库的 SQL server 的名称\<目标数据库\>驻留。</span><span class="sxs-lookup"><span data-stu-id="990a7-108">Type the following at the command line prompt: **bm enable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>**, where \<*target server*\> is replaced by the name of the SQL server on which the target BAM Primary Import database specified by \<target database\> resides.</span></span> <span data-ttu-id="990a7-109">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="990a7-109">Press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="990a7-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="990a7-110">See Also</span></span>  
 [<span data-ttu-id="990a7-111">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="990a7-111">BAM Management Utility</span></span>](../core/bam-management-utility.md)