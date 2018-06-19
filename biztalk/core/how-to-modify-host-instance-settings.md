---
title: 更新主机实例设置 |Microsoft 文档
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
ms.openlocfilehash: d85635f7f7a3b2cfe05abaf041cac07913b36f96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254373"
---
# <a name="update-biztalk-host-instance-settings"></a><span data-ttu-id="b4f2f-103">更新 BizTalk 主机实例设置</span><span class="sxs-lookup"><span data-stu-id="b4f2f-103">Update BizTalk host instance settings</span></span>

## <a name="overview"></a><span data-ttu-id="b4f2f-104">概述</span><span class="sxs-lookup"><span data-stu-id="b4f2f-104">Overview</span></span>
<span data-ttu-id="b4f2f-105">使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]，您可以修改整个 BizTalk 组中给定主机实例的配置信息。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-105">Using the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)], you can modify the configuration information of a given host instance, across a BizTalk group.</span></span> <span data-ttu-id="b4f2f-106">本主题提供了用于修改 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中主机实例级别性能设置的分步过程。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-106">This topic provides the step-by-step procedure to modify the host instance level performance settings in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b4f2f-107">通常您将 BizTalk 设置（来自源环境）保存为 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-107">Often you have the BizTalk settings (from a source environment) saved as an XML file.</span></span> <span data-ttu-id="b4f2f-108">XML 文件包含允许您在目标计算机上复制设置的信息。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-108">The XML file contains information that allows you to replicate the settings on the target machine.</span></span> <span data-ttu-id="b4f2f-109">可以将这些设置导入设置仪表板，而无需设置新值。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-109">You can import those settings to Settings Dashboard, instead of setting up new values.</span></span> <span data-ttu-id="b4f2f-110">另一方面，为  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 设置新值后，您可以将其导出到 XML 文件以用于其他计算机。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-110">On the other hand, after setting up new values for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can export them to an XML file to be used in another machine.</span></span>  
  
 <span data-ttu-id="b4f2f-111">有关导入信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)和[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-111">For information on importing the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) and [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="b4f2f-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="b4f2f-112">Prerequisites</span></span>  
 <span data-ttu-id="b4f2f-113">若要执行此操作，你必须作为 BizTalk Server Administrators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-113">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="update-the-host-instance-level-settings"></a><span data-ttu-id="b4f2f-114">更新的主机实例级别设置</span><span class="sxs-lookup"><span data-stu-id="b4f2f-114">Update the host instance level settings</span></span>  
  
1.  <span data-ttu-id="b4f2f-115">在**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-115">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2.  <span data-ttu-id="b4f2f-116">在**BizTalk 设置仪表板**对话框中，在**主机实例**选项卡上，执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="b4f2f-116">In the **BizTalk Settings Dashboard** dialog box, on the **Host Instances** tab, do any of the following:</span></span>  
  
    -   <span data-ttu-id="b4f2f-117">修改主机实例的 .NET CLR 设置。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-117">Modify the .NET CLR settings for a host instance.</span></span> <span data-ttu-id="b4f2f-118">请参阅[更改.NET CLR 设置](../core/how-to-modify-net-clr-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-118">See [Change the .NET CLR Settings](../core/how-to-modify-net-clr-settings.md).</span></span>  
  
    -   <span data-ttu-id="b4f2f-119">修改业务流程内存阻止设置。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-119">Modify the orchestration memory throttling settings.</span></span> <span data-ttu-id="b4f2f-120">请参阅[将业务流程的内存限制设置更改](../core/how-to-modify-orchestration-memory-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="b4f2f-120">See [Change the Orchestration Memory Throttling Settings](../core/how-to-modify-orchestration-memory-throttling-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f2f-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4f2f-121">See Also</span></span>  
 [<span data-ttu-id="b4f2f-122">设置仪表板用于 BizTalk Server 性能优化</span><span class="sxs-lookup"><span data-stu-id="b4f2f-122">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)