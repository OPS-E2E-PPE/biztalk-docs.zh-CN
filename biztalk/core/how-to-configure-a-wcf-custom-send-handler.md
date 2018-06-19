---
title: 如何配置 WCF 自定义发送处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00758b87-dffb-488b-9cf3-564d0ccd5938
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 723b28fca87171fa1cfd7ec18b57a4119f2343b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249333"
---
# <a name="how-to-configure-a-wcf-custom-send-handler"></a><span data-ttu-id="fb89e-102">如何配置 WCF 自定义发送处理程序</span><span class="sxs-lookup"><span data-stu-id="fb89e-102">How to Configure a WCF-Custom Send Handler</span></span>
<span data-ttu-id="fb89e-103">如果您希望 [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] 在 machine.config 以外的位置查找自定义行为扩展，就必须配置发送处理程序属性。</span><span class="sxs-lookup"><span data-stu-id="fb89e-103">You must configure the send handler properties if you want the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] to look up the custom behavior extensions from locations other than machine.config.</span></span>  
  
## <a name="why-should-wcf-custom-adapter-look-up-custom-behavior-extensions-from-locations-other-than-machineconfig"></a><span data-ttu-id="fb89e-104">为什么应 WCF 自定义适配器查找从 machine.config 以外的位置的自定义行为扩展？</span><span class="sxs-lookup"><span data-stu-id="fb89e-104">Why Should WCF-Custom Adapter Look up Custom Behavior Extensions from Locations Other than machine.config?</span></span>  
 <span data-ttu-id="fb89e-105">使用自定义行为扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 machine.config 中注册。在加载行为扩展之前[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)]查找 machine.config 中的行为扩展。但是，理想情况下用于 machine.config 存储在特定计算机上运行的所有应用程序所需的配置信息。</span><span class="sxs-lookup"><span data-stu-id="fb89e-105">Custom behavior extensions used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is registered in the machine.config. Before loading the behavior extensions, the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] looks for the behavior extensions in machine.config. However, machine.config is ideally used to store configuration information that is required across all applications running on a particular computer.</span></span> <span data-ttu-id="fb89e-106">另一方面，WCF 自定义行为扩展可能需要仅通过[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]而不是在计算机上运行的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb89e-106">On the other hand, WCF custom behavior extensions may be required only by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and not by all the applications running on the computer.</span></span> <span data-ttu-id="fb89e-107">因此，虽然在 machine.config 中存储的自定义行为扩展用途，它不是最大程度优化的位置。</span><span class="sxs-lookup"><span data-stu-id="fb89e-107">So, while storing the custom behavior extensions in machine.config serves the purpose, it is not the most optimal location.</span></span>  
  
 <span data-ttu-id="fb89e-108">与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，适配器处理程序属性提供了其他位置从中[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)]可以查找自定义行为扩展。</span><span class="sxs-lookup"><span data-stu-id="fb89e-108">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the adapter handler properties provide an additional location from which the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] can look up the custom behavior extensions.</span></span> <span data-ttu-id="fb89e-109">请注意这不会替换已在 machine.config 中提供的行为扩展。</span><span class="sxs-lookup"><span data-stu-id="fb89e-109">Note that this does not replace the behavior extensions already available in machine.config.</span></span>  
  
### <a name="additional-considerations"></a><span data-ttu-id="fb89e-110">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="fb89e-110">Additional Considerations</span></span>  
 <span data-ttu-id="fb89e-111">配置 WCF 自定义发送处理程序属性时，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="fb89e-111">Keep the following points in mind while configuring the WCF-Custom send handler properties:</span></span>  
  
-   <span data-ttu-id="fb89e-112">自定义行为扩展必须在 machine.config 或适配器处理程序属性中可用。</span><span class="sxs-lookup"><span data-stu-id="fb89e-112">The custom behavior extensions must be available either in the machine.config or in the adapter handler properties.</span></span> <span data-ttu-id="fb89e-113">在这两个位置中必须不能重复的自定义行为扩展。</span><span class="sxs-lookup"><span data-stu-id="fb89e-113">The custom behavior extensions must not be duplicated at both locations.</span></span>  
  
-   <span data-ttu-id="fb89e-114">如果您尝试设置适配器处理程序属性的相同行为扩展的自定义行为扩展已在 machine.config 中可用，你会收到错误，就会立即尝试设置属性。</span><span class="sxs-lookup"><span data-stu-id="fb89e-114">If the custom behavior extension is already available in the machine.config and you try to set the same behavior extension for the adapter handler properties, you get an error as soon as you try to set the property.</span></span>  
  
-   <span data-ttu-id="fb89e-115">如果已经为适配器处理程序属性设置了自定义行为扩展，然后用同样的行为扩展更新 machine.config 时，会收到运行时错误，并且还会在事件日志中记录此错误。</span><span class="sxs-lookup"><span data-stu-id="fb89e-115">If the custom behavior extension is already set for the adapter handler properties and you then update the machine.config with the same behavior extension, you will get a runtime error and it is also logged in the event log.</span></span>  
  
-   <span data-ttu-id="fb89e-116">设置适配器处理程序属性之前，必须存在在全局程序集缓存 (GAC) 中的自定义行为扩展所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="fb89e-116">The assemblies referred in the custom behavior extension must be present in the Global Assembly Cache (GAC) before you set the adapter handler properties.</span></span>  
  
## <a name="configuring-the-adapter-handler-properties"></a><span data-ttu-id="fb89e-117">配置适配器处理程序属性</span><span class="sxs-lookup"><span data-stu-id="fb89e-117">Configuring the Adapter Handler Properties</span></span>  
 <span data-ttu-id="fb89e-118">使用配置 WCF 自定义此主题中的过程发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="fb89e-118">Use the procedure in this topic to configure a WCF-Custom send handler.</span></span>  
  
#### <a name="to-configure-the-adapter-handler-properties"></a><span data-ttu-id="fb89e-119">若要配置的适配器处理程序属性</span><span class="sxs-lookup"><span data-stu-id="fb89e-119">To configure the adapter handler properties</span></span>  
  
1.  <span data-ttu-id="fb89e-120">在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="fb89e-120">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="fb89e-121">在展开的适配器列表中，单击**WCF 自定义**，而是在右窗格中，右键单击你想要配置，则发送处理程序，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="fb89e-121">In the expanded adapter list, click **WCF-Custom**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="fb89e-122">在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择的主机发送处理程序将与之相关联，并依次**属性**。</span><span class="sxs-lookup"><span data-stu-id="fb89e-122">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="fb89e-123">在**WCF 自定义传输属性**对话框中，在**WCF 扩展**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fb89e-123">In the **WCF-Custom Transport Properties** dialog box, on the **WCF Extensions** tab, do the following:</span></span>  
  
    |<span data-ttu-id="fb89e-124">使用此选项</span><span class="sxs-lookup"><span data-stu-id="fb89e-124">Use this</span></span>|<span data-ttu-id="fb89e-125">执行的操作</span><span class="sxs-lookup"><span data-stu-id="fb89e-125">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fb89e-126">**导入**</span><span class="sxs-lookup"><span data-stu-id="fb89e-126">**Import**</span></span>|<span data-ttu-id="fb89e-127">导入带有 WCF 自定义行为扩展的 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="fb89e-127">Imports a WCF configuration file with WCF custom behavior extensions.</span></span> <span data-ttu-id="fb89e-128">单击此按钮将打开**导入 WCF 配置**对话框中浏览并找到 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="fb89e-128">Clicking this button opens the **Import WCF configuration** dialog box to browse and locate a WCF configuration file.</span></span> <span data-ttu-id="fb89e-129">请注意，该文件应是有效的 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="fb89e-129">Note that the file should be a valid WCF configuration file.</span></span> <span data-ttu-id="fb89e-130">有关 WCF 配置架构的详细信息，请参阅"Windows Communication Foundation 配置架构"在[http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953)。</span><span class="sxs-lookup"><span data-stu-id="fb89e-130">For more information about WCF configuration schema, see “Windows Communication Foundation Configuration Schema” at [http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953).</span></span>|  
    |<span data-ttu-id="fb89e-131">**导出**</span><span class="sxs-lookup"><span data-stu-id="fb89e-131">**Export**</span></span>|<span data-ttu-id="fb89e-132">将 WCF 自定义行为扩展导出到 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="fb89e-132">Exports the WCF custom behavior extension to a WCF configuration file.</span></span> <span data-ttu-id="fb89e-133">单击此按钮将打开**导出 WCF 配置**对话框中，以浏览并保存 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="fb89e-133">Clicking this button opens the **Export WCF configuration** dialog box to browse and save the WCF configuration file.</span></span>|  
    |<span data-ttu-id="fb89e-134">**Clear**</span><span class="sxs-lookup"><span data-stu-id="fb89e-134">**Clear**</span></span>|<span data-ttu-id="fb89e-135">清除适配器处理程序属性中的现有 WCF 自定义行为扩展。</span><span class="sxs-lookup"><span data-stu-id="fb89e-135">Clears the existing WCF custom behavior extension from the adapter handler properties.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb89e-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb89e-136">See Also</span></span>  
 [<span data-ttu-id="fb89e-137">配置 WCF 自定义适配器</span><span class="sxs-lookup"><span data-stu-id="fb89e-137">Configuring the WCF-Custom Adapter</span></span>](../core/configuring-the-wcf-custom-adapter.md)