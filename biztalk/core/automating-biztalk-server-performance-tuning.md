---
title: "自动执行 BizTalk Server 性能优化 |Microsoft 文档"
description: "使用 BTSTask 导入或导出 BizTalk Server 中的环境之间的性能设置"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07ff73b5-25d9-4f3f-9a4b-127c0b843741
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e4ea364345ed9f2a8f642e11650cfcd9d09f10f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="automate-biztalk-server-performance-tuning"></a><span data-ttu-id="3b543-103">自动执行 BizTalk Server 性能优化</span><span class="sxs-lookup"><span data-stu-id="3b543-103">Automate BizTalk Server Performance Tuning</span></span>

## <a name="overview"></a><span data-ttu-id="3b543-104">概述</span><span class="sxs-lookup"><span data-stu-id="3b543-104">Overview</span></span>
<span data-ttu-id="3b543-105">你可以自动执行的优化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过导入或导出的 BizTalk 设置或操作使用的设置的性能设置[WMI](http://go.microsoft.com/fwlink/?LinkId=200464)。</span><span class="sxs-lookup"><span data-stu-id="3b543-105">You can automate the tuning of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance settings either by importing or exporting the BizTalk settings or by manipulating the settings using [WMI](http://go.microsoft.com/fwlink/?LinkId=200464).</span></span>  
  
 <span data-ttu-id="3b543-106">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境设置为最佳性能之后，可以向 XML 文件导出或导入 BizTalk Server 设置。</span><span class="sxs-lookup"><span data-stu-id="3b543-106">After the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment is set up for optimum performance, you can export or import the BizTalk Server settings to an XML file.</span></span> <span data-ttu-id="3b543-107">您可以使用设置仪表板或 BTSTask 命令行实用工具导入/导出 BizTalk Server 设置。</span><span class="sxs-lookup"><span data-stu-id="3b543-107">You can import/export the BizTalk Server settings either using the Settings Dashboard or the BTSTask command-line utility.</span></span> <span data-ttu-id="3b543-108">**BTSTask.exe**与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]允许 BizTalk 管理员在创建新脚本时使用 BTSTask 命令。</span><span class="sxs-lookup"><span data-stu-id="3b543-108">**BTSTask.exe** with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] allows BizTalk administrators to use BTSTask commands when creating new scripts.</span></span>  
  
 <span data-ttu-id="3b543-109">有关导入/导出 BizTalk Server 设置信息从一个环境到另一个使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="3b543-109">For information about importing/exporting BizTalk Server settings from one environment to another using [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="3b543-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3b543-110">Next steps</span></span> 
  
-   [<span data-ttu-id="3b543-111">导入或导出 BizTalk 设置使用 BTSTask</span><span class="sxs-lookup"><span data-stu-id="3b543-111">Import or export BizTalk Settings Using BTSTask</span></span>](../core/how-to-import-biztalk-settings-using-btstask.md)  
  
- [<span data-ttu-id="3b543-112">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="3b543-112">BTSTask Command-Line Reference</span></span>](btstask-command-line-reference.md)
  
## <a name="see-also"></a><span data-ttu-id="3b543-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b543-113">See Also</span></span>  
 [<span data-ttu-id="3b543-114">管理 BizTalk Server 性能设置</span><span class="sxs-lookup"><span data-stu-id="3b543-114">Managing BizTalk Server Performance Settings</span></span>](../core/managing-biztalk-server-performance-settings.md)