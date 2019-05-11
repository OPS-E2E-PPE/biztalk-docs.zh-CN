---
title: 自动进行 BizTalk Server 性能优化 |Microsoft Docs
description: 使用 BTSTask 导入或导出 BizTalk Server 中的环境之间的性能设置
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07ff73b5-25d9-4f3f-9a4b-127c0b843741
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35c0ad345a480f10350b6fdf8a4ecc6eae4e9e74
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530655"
---
# <a name="automate-biztalk-server-performance-tuning"></a><span data-ttu-id="f3ca7-103">自动进行 BizTalk Server 性能优化</span><span class="sxs-lookup"><span data-stu-id="f3ca7-103">Automate BizTalk Server Performance Tuning</span></span>

## <a name="overview"></a><span data-ttu-id="f3ca7-104">概述</span><span class="sxs-lookup"><span data-stu-id="f3ca7-104">Overview</span></span>
<span data-ttu-id="f3ca7-105">可以自动调整[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能设置通过导入或导出 BizTalk 设置或操作使用的设置[WMI](http://go.microsoft.com/fwlink/?LinkId=200464)。</span><span class="sxs-lookup"><span data-stu-id="f3ca7-105">You can automate the tuning of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance settings either by importing or exporting the BizTalk settings or by manipulating the settings using [WMI](http://go.microsoft.com/fwlink/?LinkId=200464).</span></span>  
  
 <span data-ttu-id="f3ca7-106">之后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置环境以获得最佳性能，你可以导出或导入到 XML 文件的 BizTalk Server 设置。</span><span class="sxs-lookup"><span data-stu-id="f3ca7-106">After the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment is set up for optimum performance, you can export or import the BizTalk Server settings to an XML file.</span></span> <span data-ttu-id="f3ca7-107">您可以导入/导出 BizTalk Server 设置使用设置仪表板或 BTSTask 命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="f3ca7-107">You can import/export the BizTalk Server settings either using the Settings Dashboard or the BTSTask command-line utility.</span></span> <span data-ttu-id="f3ca7-108">**BTSTask.exe**与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，BizTalk 管理员可以创建新脚本时使用 BTSTask 命令。</span><span class="sxs-lookup"><span data-stu-id="f3ca7-108">**BTSTask.exe** with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] allows BizTalk administrators to use BTSTask commands when creating new scripts.</span></span>  
  
 <span data-ttu-id="f3ca7-109">有关导入/导出 BizTalk Server 设置信息从一个环境到另一个使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="f3ca7-109">For information about importing/exporting BizTalk Server settings from one environment to another using [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="f3ca7-110">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f3ca7-110">Next steps</span></span> 
  
-   [<span data-ttu-id="f3ca7-111">使用 BTSTask 导入或导出 BizTalk 设置</span><span class="sxs-lookup"><span data-stu-id="f3ca7-111">Import or export BizTalk Settings Using BTSTask</span></span>](../core/how-to-import-biztalk-settings-using-btstask.md)  
  
- [<span data-ttu-id="f3ca7-112">BTSTask 命令行参考</span><span class="sxs-lookup"><span data-stu-id="f3ca7-112">BTSTask Command-Line Reference</span></span>](btstask-command-line-reference.md)
  
## <a name="see-also"></a><span data-ttu-id="f3ca7-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f3ca7-113">See Also</span></span>  
 [<span data-ttu-id="f3ca7-114">管理 BizTalk Server 性能设置</span><span class="sxs-lookup"><span data-stu-id="f3ca7-114">Managing BizTalk Server Performance Settings</span></span>](../core/managing-biztalk-server-performance-settings.md)