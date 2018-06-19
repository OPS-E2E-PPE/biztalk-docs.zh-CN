---
title: 如何禁用 BAM 主导入数据库引用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d2d644-6ebb-4051-ae59-af7d0fb75753
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc9afef7bdcfad84f105abda158c5ed5c6461619
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968891"
---
# <a name="how-to-disable-a-bam-primary-import-database-reference"></a><span data-ttu-id="e6ec9-102">如何禁用 BAM 主导入数据库引用</span><span class="sxs-lookup"><span data-stu-id="e6ec9-102">How to Disable a BAM Primary Import Database Reference</span></span>
<span data-ttu-id="e6ec9-103">管理员使用**禁用引用**命令以禁用对指定的 BAM 主导入数据库的引用。</span><span class="sxs-lookup"><span data-stu-id="e6ec9-103">Administrators use the **disable-reference** command to disable a reference to a specified BAM Primary Import database.</span></span>  
  
### <a name="to-disable-a-reference-to-a-bam-primary-import-database"></a><span data-ttu-id="e6ec9-104">禁用对 BAM 主导入数据库的引用</span><span class="sxs-lookup"><span data-stu-id="e6ec9-104">To disable a reference to a BAM Primary Import database</span></span>  
  
1.  <span data-ttu-id="e6ec9-105">如下所示打开命令提示符： 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e6ec9-105">Open a command prompt as follows: Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="e6ec9-106">导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="e6ec9-106">Navigate to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3.  <span data-ttu-id="e6ec9-107">在命令行提示符下键入以下内容： **bm 禁用引用 TargetServer:\<目标服务器\>-TargetDatabase:\<目标数据库\>[-Server:\<服务器\> ][-数据库：\<数据库\>]**，其中 **\<** *目标服务器* **\>** 由在其上通过将指定的目标 BAM 主导入数据库的 SQL server 的名称替换\<*目标数据库*\>驻留。</span><span class="sxs-lookup"><span data-stu-id="e6ec9-107">Type the following at the command line prompt: **bm disable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**, where **\<***target server***\>** is replaced by the name of the SQL server on which the target BAM Primary Import database specified by \<*target database*\> resides.</span></span> <span data-ttu-id="e6ec9-108">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="e6ec9-108">Press **ENTER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6ec9-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6ec9-109">See Also</span></span>  
 [<span data-ttu-id="e6ec9-110">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="e6ec9-110">BAM Management Utility</span></span>](../core/bam-management-utility.md)