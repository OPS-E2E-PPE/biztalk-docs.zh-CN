---
title: 如何修改主机设置 |Microsoft Docs
description: 更改 BizTalk Server 管理来提高性能和带宽限制中的 BizTalk 主机设置
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0759b3a0-560e-4a11-92e6-9de0e15f463b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93b2ea993e044d1cb18efcc73f631e8ba3fcb8ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975838"
---
# <a name="update-biztalk-host-settings"></a><span data-ttu-id="3f421-103">更新 BizTalk 主机设置</span><span class="sxs-lookup"><span data-stu-id="3f421-103">Update BizTalk host settings</span></span>

## <a name="overview"></a><span data-ttu-id="3f421-104">概述</span><span class="sxs-lookup"><span data-stu-id="3f421-104">Overview</span></span>
<span data-ttu-id="3f421-105">使用设置仪表板，您可以修改整个 BizTalk 组中给定主机的配置信息。</span><span class="sxs-lookup"><span data-stu-id="3f421-105">Using the Settings Dashboard, you can modify the configuration information of a given host, across a BizTalk group.</span></span> <span data-ttu-id="3f421-106">本主题提供了用于修改 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中主机级别性能设置的分步过程。</span><span class="sxs-lookup"><span data-stu-id="3f421-106">This topic provides the step-by-step procedure to modify the host-level performance settings in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f421-107">您还可以修改组和主机实例设置。</span><span class="sxs-lookup"><span data-stu-id="3f421-107">You can also modify the group and host instance settings.</span></span> <span data-ttu-id="3f421-108">有关如何修改的设置的信息，请参阅[使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。</span><span class="sxs-lookup"><span data-stu-id="3f421-108">For information about how to modify the settings, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md).</span></span>  
  
 <span data-ttu-id="3f421-109">可以将当前的 BizTalk Server 设置导出到 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="3f421-109">The current BizTalk Server settings can be exported to an XML file.</span></span> <span data-ttu-id="3f421-110">然后，将这些设置导入到“设置仪表板”，而不是设置新值。</span><span class="sxs-lookup"><span data-stu-id="3f421-110">Later, you can import those settings to the Settings Dashboard instead of setting up new values.</span></span> <span data-ttu-id="3f421-111">有关导入信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]设置，请参阅[导入或导出 BizTalk 设置使用设置仪表板](how-to-import-biztalk-settings-using-settings-dashboard.md)并[导入或导出 BizTalk 设置使用 BTSTask](how-to-import-biztalk-settings-using-btstask.md)。</span><span class="sxs-lookup"><span data-stu-id="3f421-111">For information on importing the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) and [Import or export BizTalk Settings Using BTSTask](how-to-import-biztalk-settings-using-btstask.md).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="3f421-112">必要條件</span><span class="sxs-lookup"><span data-stu-id="3f421-112">Prerequisites</span></span>  
 <span data-ttu-id="3f421-113">若要执行此操作，必须以 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="3f421-113">To perform this operation, you must be signed in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="update-the-host-level-settings"></a><span data-ttu-id="3f421-114">更新主机级别设置</span><span class="sxs-lookup"><span data-stu-id="3f421-114">Update the host-level settings</span></span>  
  
1. <span data-ttu-id="3f421-115">在中**BizTalk Server 管理控制台**，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，右键单击**BizTalk 组**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="3f421-115">In the **BizTalk Server Administration Console**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
2. <span data-ttu-id="3f421-116">在中**BizTalk 设置仪表板**对话框中，在**主机**页上，执行一个或多个以下。</span><span class="sxs-lookup"><span data-stu-id="3f421-116">In the **BizTalk Settings Dashboard** dialog box, on the **Hosts** page, do one or more of the following.</span></span>  
  
   -   <span data-ttu-id="3f421-117">修改 BizTalk 主机的常规性能设置。</span><span class="sxs-lookup"><span data-stu-id="3f421-117">Modify the general performance settings of the BizTalk host.</span></span> <span data-ttu-id="3f421-118">请参阅[如何修改常规设置](../core/how-to-modify-general-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="3f421-118">See [How to Modify General Settings](../core/how-to-modify-general-settings.md).</span></span>  
  
   -   <span data-ttu-id="3f421-119">修改 BizTalk 主机基于资源的阻止设置。</span><span class="sxs-lookup"><span data-stu-id="3f421-119">Modify the resource-based throttling settings of the BizTalk host.</span></span> <span data-ttu-id="3f421-120">请参阅[基于如何修改资源的阻止设置](../core/how-to-modify-resource-based-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="3f421-120">See [How to Modify Resource Based Throttling Settings](../core/how-to-modify-resource-based-throttling-settings.md).</span></span>  
  
   -   <span data-ttu-id="3f421-121">修改 BizTalk 主机基于速率的阻止设置。</span><span class="sxs-lookup"><span data-stu-id="3f421-121">Modify the rate-based throttling settings of the BizTalk host.</span></span> <span data-ttu-id="3f421-122">请参阅[如何修改基于速率的阻止设置](../core/how-to-modify-rate-based-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="3f421-122">See [How to Modify Rate Based Throttling Settings](../core/how-to-modify-rate-based-throttling-settings.md).</span></span>  
  
   -   <span data-ttu-id="3f421-123">修改 BizTalk 主机的业务流程阻止设置。</span><span class="sxs-lookup"><span data-stu-id="3f421-123">Modify the orchestration throttling settings of the BizTalk host.</span></span> <span data-ttu-id="3f421-124">请参阅[如何修改业务流程阻止设置](../core/how-to-modify-orchestration-throttling-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="3f421-124">See [How to Modify Orchestration Throttling Settings](../core/how-to-modify-orchestration-throttling-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f421-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f421-125">See Also</span></span>  
 [<span data-ttu-id="3f421-126">使用设置仪表板进行 BizTalk Server 性能调整</span><span class="sxs-lookup"><span data-stu-id="3f421-126">Use Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)