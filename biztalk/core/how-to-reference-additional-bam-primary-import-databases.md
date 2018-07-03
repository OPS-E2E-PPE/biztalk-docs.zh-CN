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
ms.openlocfilehash: 54982491ca8ce2c7ca7acd9e176a7341b2642c78
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992310"
---
# <a name="how-to-reference-additional-bam-primary-import-databases"></a><span data-ttu-id="ca05d-102">如何引用其他 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="ca05d-102">How to Reference Additional BAM Primary Import Databases</span></span>
<span data-ttu-id="ca05d-103">管理员使用**启用引用**命令引用其他 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="ca05d-103">Administrators use the **enable-reference** command to reference additional BAM Primary Import databases.</span></span> <span data-ttu-id="ca05d-104">引用多个 BAM 主导入数据库可更有效地查看分布式 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="ca05d-104">You reference multiple BAM Primary Import databases to facilitate viewing distributed BAM activities.</span></span>  
  
### <a name="to-enable-a-reference-to-an-additional-bam-primary-import-database"></a><span data-ttu-id="ca05d-105">启用对其他 BAM 主导入数据库的引用</span><span class="sxs-lookup"><span data-stu-id="ca05d-105">To enable a reference to an additional BAM Primary Import database</span></span>  
  
1. <span data-ttu-id="ca05d-106">按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca05d-106">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="ca05d-107">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="ca05d-107">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="ca05d-108">在命令行提示符下键入以下内容： **bm 启用引用-TargetServer:\<目标服务器\>-TargetDatabase:\<目标数据库\>**，其中\<*目标服务器*\>替换为在其通过将指定的目标 BAM 主导入数据库的 SQL server 的名称\<目标数据库\>驻留。</span><span class="sxs-lookup"><span data-stu-id="ca05d-108">Type the following at the command line prompt: **bm enable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>**, where \<*target server*\> is replaced by the name of the SQL server on which the target BAM Primary Import database specified by \<target database\> resides.</span></span> <span data-ttu-id="ca05d-109">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="ca05d-109">Press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca05d-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca05d-110">See Also</span></span>  
 [<span data-ttu-id="ca05d-111">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="ca05d-111">BAM Management Utility</span></span>](../core/bam-management-utility.md)