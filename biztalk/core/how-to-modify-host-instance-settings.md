---
title: 更新主机实例设置 |Microsoft Docs
description: 更改主机实例设置 BizTalk 服务器管理器中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2338255b-cc13-4f6a-86c3-9ecc666c43e5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e5b2eec6b252417f73f917f1293ffc925f0e1a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336084"
---
# <a name="update-biztalk-host-instance-settings"></a><span data-ttu-id="2dfb7-103">更新 BizTalk 主机实例设置</span><span class="sxs-lookup"><span data-stu-id="2dfb7-103">Update BizTalk host instance settings</span></span>

## <a name="overview"></a><span data-ttu-id="2dfb7-104">概述</span><span class="sxs-lookup"><span data-stu-id="2dfb7-104">Overview</span></span>
<span data-ttu-id="2dfb7-105">使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]，可以跨 BizTalk 组中修改给定的主机实例的配置信息。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-105">Using the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], you can modify the configuration information of a given host instance, across a BizTalk group.</span></span> <span data-ttu-id="2dfb7-106">本主题提供的分步过程来修改主机实例级别性能设置在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-106">This topic provides the step-by-step procedure to modify the host instance level performance settings in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2dfb7-107">通常可以另存为 XML 文件的 BizTalk 设置 （来自源环境）。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-107">Often you have the BizTalk settings (from a source environment) saved as an XML file.</span></span> <span data-ttu-id="2dfb7-108">XML 文件包含允许您复制目标计算机上的设置的信息。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-108">The XML file contains information that allows you to replicate the settings on the target machine.</span></span> <span data-ttu-id="2dfb7-109">而不是设置新值，您可以导入设置仪表板中，这些设置。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-109">You can import those settings to Settings Dashboard, instead of setting up new values.</span></span> <span data-ttu-id="2dfb7-110">但是，设置新值后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以将其导出到 XML 文件以在另一台计算机中使用。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-110">On the other hand, after setting up new values for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can export them to an XML file to be used in another machine.</span></span>  
  
 <span data-ttu-id="2dfb7-111">有关导入信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)并[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-111">For information on importing the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) and [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="2dfb7-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="2dfb7-112">Prerequisites</span></span>  
 <span data-ttu-id="2dfb7-113">若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-113">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="update-the-host-instance-level-settings"></a><span data-ttu-id="2dfb7-114">更新主机实例级别设置</span><span class="sxs-lookup"><span data-stu-id="2dfb7-114">Update the host instance level settings</span></span>  
  
1. <span data-ttu-id="2dfb7-115">在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-115">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2. <span data-ttu-id="2dfb7-116">在中**BizTalk 设置仪表板**对话框中，在**主机实例**选项卡上，执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="2dfb7-116">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instances** tab, do any of the following:</span></span>  
  
   -   <span data-ttu-id="2dfb7-117">修改主机实例的.NET CLR 设置。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-117">Modify the .NET CLR settings for a host instance.</span></span> <span data-ttu-id="2dfb7-118">请参阅[更改.NET CLR 设置](../core/how-to-modify-net-clr-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-118">See [Change the .NET CLR Settings](../core/how-to-modify-net-clr-settings.md).</span></span>  
  
   -   <span data-ttu-id="2dfb7-119">修改业务流程内存阻止设置。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-119">Modify the orchestration memory throttling settings.</span></span> <span data-ttu-id="2dfb7-120">请参阅[更改业务流程内存阻止设置](../core/how-to-modify-orchestration-memory-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2dfb7-120">See [Change the Orchestration Memory Throttling Settings](../core/how-to-modify-orchestration-memory-throttling-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dfb7-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="2dfb7-121">See Also</span></span>  
 [<span data-ttu-id="2dfb7-122">使用设置仪表板进行 BizTalk Server 性能调整</span><span class="sxs-lookup"><span data-stu-id="2dfb7-122">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)