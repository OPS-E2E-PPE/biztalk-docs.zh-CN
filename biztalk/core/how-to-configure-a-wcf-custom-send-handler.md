---
title: 如何配置 Wcf-custom 发送处理程序 |Microsoft Docs
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
ms.openlocfilehash: d0d0e00e154432b99ac8b39827cd881b3a405599
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342258"
---
# <a name="how-to-configure-a-wcf-custom-send-handler"></a><span data-ttu-id="78d34-102">如何配置 Wcf-custom 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="78d34-102">How to Configure a WCF-Custom Send Handler</span></span>
<span data-ttu-id="78d34-103">如果你想，则必须配置发送处理程序属性[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)]从 machine.config 之外的位置查找自定义行为扩展。</span><span class="sxs-lookup"><span data-stu-id="78d34-103">You must configure the send handler properties if you want the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] to look up the custom behavior extensions from locations other than machine.config.</span></span>  
  
## <a name="why-should-wcf-custom-adapter-look-up-custom-behavior-extensions-from-locations-other-than-machineconfig"></a><span data-ttu-id="78d34-104">为什么应从 machine.config 之外的位置的自定义行为扩展 WCF 自定义适配器查找？</span><span class="sxs-lookup"><span data-stu-id="78d34-104">Why Should WCF-Custom Adapter Look up Custom Behavior Extensions from Locations Other than machine.config?</span></span>  
 <span data-ttu-id="78d34-105">使用的自定义行为扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 machine.config 中注册。加载行为扩展之前[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)]行为扩展在 machine.config 中查找。但是，machine.config 最好用于存储在特定计算机上运行的所有应用程序所需的配置信息。</span><span class="sxs-lookup"><span data-stu-id="78d34-105">Custom behavior extensions used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is registered in the machine.config. Before loading the behavior extensions, the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] looks for the behavior extensions in machine.config. However, machine.config is ideally used to store configuration information that is required across all applications running on a particular computer.</span></span> <span data-ttu-id="78d34-106">但是，WCF 自定义行为扩展可能需要只能由[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]而不是由在计算机上运行的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="78d34-106">On the other hand, WCF custom behavior extensions may be required only by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and not by all the applications running on the computer.</span></span> <span data-ttu-id="78d34-107">因此，尽管在 machine.config 中存储自定义行为扩展用途，它不是最佳的位置。</span><span class="sxs-lookup"><span data-stu-id="78d34-107">So, while storing the custom behavior extensions in machine.config serves the purpose, it is not the most optimal location.</span></span>  
  
 <span data-ttu-id="78d34-108">与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，适配器处理程序属性提供的其他位置[!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)]可以查找自定义行为扩展。</span><span class="sxs-lookup"><span data-stu-id="78d34-108">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the adapter handler properties provide an additional location from which the [!INCLUDE[wcfadapter_short](../includes/wcfadapter-short-md.md)] can look up the custom behavior extensions.</span></span> <span data-ttu-id="78d34-109">请注意这不会替换已在 machine.config 中提供的行为扩展。</span><span class="sxs-lookup"><span data-stu-id="78d34-109">Note that this does not replace the behavior extensions already available in machine.config.</span></span>  
  
### <a name="additional-considerations"></a><span data-ttu-id="78d34-110">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="78d34-110">Additional Considerations</span></span>  
 <span data-ttu-id="78d34-111">配置 Wcf-custom 发送处理程序属性时请记住的以下几点：</span><span class="sxs-lookup"><span data-stu-id="78d34-111">Keep the following points in mind while configuring the WCF-Custom send handler properties:</span></span>  
  
-   <span data-ttu-id="78d34-112">自定义行为扩展必须在 machine.config 或适配器处理程序属性中可用。</span><span class="sxs-lookup"><span data-stu-id="78d34-112">The custom behavior extensions must be available either in the machine.config or in the adapter handler properties.</span></span> <span data-ttu-id="78d34-113">不能在这两个位置复制自定义行为扩展。</span><span class="sxs-lookup"><span data-stu-id="78d34-113">The custom behavior extensions must not be duplicated at both locations.</span></span>  
  
-   <span data-ttu-id="78d34-114">如果已在 machine.config 中提供自定义行为扩展，并且您尝试设置适用于适配器处理程序属性的相同行为扩展，只要您尝试设置该属性可能会出错。</span><span class="sxs-lookup"><span data-stu-id="78d34-114">If the custom behavior extension is already available in the machine.config and you try to set the same behavior extension for the adapter handler properties, you get an error as soon as you try to set the property.</span></span>  
  
-   <span data-ttu-id="78d34-115">如果自定义行为扩展已经安装的适配器处理程序属性，然后使用相同的行为扩展更新 machine.config，将获取运行时错误，它还会在事件日志中记录。</span><span class="sxs-lookup"><span data-stu-id="78d34-115">If the custom behavior extension is already set for the adapter handler properties and you then update the machine.config with the same behavior extension, you will get a runtime error and it is also logged in the event log.</span></span>  
  
-   <span data-ttu-id="78d34-116">设置适配器处理程序属性之前，在自定义行为扩展中引用的程序集必须在全局程序集缓存 (GAC) 中存在。</span><span class="sxs-lookup"><span data-stu-id="78d34-116">The assemblies referred in the custom behavior extension must be present in the Global Assembly Cache (GAC) before you set the adapter handler properties.</span></span>  
  
## <a name="configuring-the-adapter-handler-properties"></a><span data-ttu-id="78d34-117">配置适配器处理程序属性</span><span class="sxs-lookup"><span data-stu-id="78d34-117">Configuring the Adapter Handler Properties</span></span>  
 <span data-ttu-id="78d34-118">若要配置 WCF 自定义本主题中的过程使用发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="78d34-118">Use the procedure in this topic to configure a WCF-Custom send handler.</span></span>  
  
#### <a name="to-configure-the-adapter-handler-properties"></a><span data-ttu-id="78d34-119">若要配置适配器处理程序属性</span><span class="sxs-lookup"><span data-stu-id="78d34-119">To configure the adapter handler properties</span></span>  
  
1. <span data-ttu-id="78d34-120">在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="78d34-120">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2. <span data-ttu-id="78d34-121">在展开的适配器列表中，单击**WCF 自定义**，在右窗格中，右键单击你想要配置，发送处理程序，再单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="78d34-121">In the expanded adapter list, click **WCF-Custom**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="78d34-122">在中**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择将的主机与发送处理程序相关联，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="78d34-122">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the send handler will be associated, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="78d34-123">在中**Wcf-custom 传输属性**对话框中，在**WCF 扩展**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="78d34-123">In the **WCF-Custom Transport Properties** dialog box, on the **WCF Extensions** tab, do the following:</span></span>  
  
   |<span data-ttu-id="78d34-124">使用此选项</span><span class="sxs-lookup"><span data-stu-id="78d34-124">Use this</span></span>|<span data-ttu-id="78d34-125">执行的操作</span><span class="sxs-lookup"><span data-stu-id="78d34-125">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="78d34-126">**导入**</span><span class="sxs-lookup"><span data-stu-id="78d34-126">**Import**</span></span>|<span data-ttu-id="78d34-127">导入 WCF 配置文件与 WCF 自定义行为扩展。</span><span class="sxs-lookup"><span data-stu-id="78d34-127">Imports a WCF configuration file with WCF custom behavior extensions.</span></span> <span data-ttu-id="78d34-128">单击此按钮将打开**导入 WCF 配置**对话框可以浏览并找到 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="78d34-128">Clicking this button opens the **Import WCF configuration** dialog box to browse and locate a WCF configuration file.</span></span> <span data-ttu-id="78d34-129">请注意该文件应是有效的 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="78d34-129">Note that the file should be a valid WCF configuration file.</span></span> <span data-ttu-id="78d34-130">有关 WCF 配置架构的详细信息，请参阅"Windows Communication Foundation 配置架构"处[ http://go.microsoft.com/fwlink/?LinkId=163953 ](http://go.microsoft.com/fwlink/?LinkId=163953)。</span><span class="sxs-lookup"><span data-stu-id="78d34-130">For more information about WCF configuration schema, see “Windows Communication Foundation Configuration Schema” at [http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953).</span></span>|  
   |<span data-ttu-id="78d34-131">**导出**</span><span class="sxs-lookup"><span data-stu-id="78d34-131">**Export**</span></span>|<span data-ttu-id="78d34-132">将 WCF 自定义行为扩展导出到 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="78d34-132">Exports the WCF custom behavior extension to a WCF configuration file.</span></span> <span data-ttu-id="78d34-133">单击此按钮将打开**导出 WCF 配置**对话框，游览并保存 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="78d34-133">Clicking this button opens the **Export WCF configuration** dialog box to browse and save the WCF configuration file.</span></span>|  
   |<span data-ttu-id="78d34-134">**Clear**</span><span class="sxs-lookup"><span data-stu-id="78d34-134">**Clear**</span></span>|<span data-ttu-id="78d34-135">清除适配器处理程序属性中的现有 WCF 自定义行为扩展。</span><span class="sxs-lookup"><span data-stu-id="78d34-135">Clears the existing WCF custom behavior extension from the adapter handler properties.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78d34-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="78d34-136">See Also</span></span>  
 [<span data-ttu-id="78d34-137">配置 WCF-Custom 适配器</span><span class="sxs-lookup"><span data-stu-id="78d34-137">Configuring the WCF-Custom Adapter</span></span>](../core/configuring-the-wcf-custom-adapter.md)