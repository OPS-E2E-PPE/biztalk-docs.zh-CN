---
title: 如何配置 WCF CustomIsolated 接收处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e90add2-1a5e-4509-a98c-b3c297b4213f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00e52daaaefc3f85537dc3c51f8700da30b74876
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248533"
---
# <a name="how-to-configure-a-wcf-customisolated-receive-handler"></a><span data-ttu-id="53558-102">如何配置 WCF-CustomIsolated 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="53558-102">How to Configure a WCF-CustomIsolated Receive Handler</span></span>
<span data-ttu-id="53558-103">如果希望 WCF-CustomIsolated 适配器在 machine.config 以外的位置查找自定义行为扩展，则必须配置接收处理程序属性。</span><span class="sxs-lookup"><span data-stu-id="53558-103">You must configure the receive handler properties if you want the WCF-CustomIsolated adapter to lookup the custom behavior extension from locations other than machine.config.</span></span>  
  
## <a name="why-should-wcf-customisolated-adapter-look-up-custom-behavior-extensions-from-locations-other-than-machineconfig"></a><span data-ttu-id="53558-104">为什么 WCF-CustomIsolated 适配器应从 machine.config 以外的位置查找自定义行为扩展？</span><span class="sxs-lookup"><span data-stu-id="53558-104">Why Should WCF-CustomIsolated Adapter Look up Custom Behavior Extensions from Locations Other than machine.config?</span></span>  
 <span data-ttu-id="53558-105">使用自定义行为扩展[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 machine.config 中注册。加载行为扩展之前, 的 WCF CustomIsolated 适配器查找 machine.config 中的行为扩展。但是，理想情况下用于 machine.config 存储在特定计算机上运行的所有应用程序所需的配置信息。</span><span class="sxs-lookup"><span data-stu-id="53558-105">Custom behavior extensions used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are registered in the machine.config. Before loading the behavior extensions, the WCF-CustomIsolated adapter looks for the behavior extensions in machine.config. However, machine.config is ideally used to store configuration information that is required across all applications running on a particular computer.</span></span> <span data-ttu-id="53558-106">另一方面，WCF 自定义行为扩展可能需要仅通过[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]而不是在计算机上运行的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="53558-106">On the other hand, WCF custom behavior extensions may be required only by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and not by all the applications running on the computer.</span></span> <span data-ttu-id="53558-107">因此，虽然在 machine.config 中存储的自定义行为扩展用途，它不是最大程度优化的位置。</span><span class="sxs-lookup"><span data-stu-id="53558-107">So, while storing the custom behavior extensions in machine.config serves the purpose, it is not the most optimal location.</span></span>  
  
 <span data-ttu-id="53558-108">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，适配器处理程序属性提供了 WCF-CustomIsolated 适配器可以从中查找自定义行为扩展的其他位置。</span><span class="sxs-lookup"><span data-stu-id="53558-108">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the adapter handler properties provide an additional location from which the WCF-CustomIsolated adapter can look up the custom behavior extensions.</span></span> <span data-ttu-id="53558-109">请注意这不会替换已在 machine.config 中提供的行为扩展。</span><span class="sxs-lookup"><span data-stu-id="53558-109">Note that this does not replace the behavior extensions already available in machine.config.</span></span>  
  
### <a name="additional-considerations"></a><span data-ttu-id="53558-110">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="53558-110">Additional Considerations</span></span>  
 <span data-ttu-id="53558-111">保留以下配置 WCF CustomIsolated 时点记住接收处理程序属性：</span><span class="sxs-lookup"><span data-stu-id="53558-111">Keep the following points in mind while configuring the WCF-CustomIsolated receive handler properties:</span></span>  
  
-   <span data-ttu-id="53558-112">自定义行为扩展必须在 machine.config 或适配器处理程序属性中可用。</span><span class="sxs-lookup"><span data-stu-id="53558-112">The custom behavior extensions must be available either in the machine.config or in the adapter handler properties.</span></span> <span data-ttu-id="53558-113">在这两个位置中必须不能重复的自定义行为扩展。</span><span class="sxs-lookup"><span data-stu-id="53558-113">The custom behavior extensions must not be duplicated at both locations.</span></span>  
  
-   <span data-ttu-id="53558-114">如果您尝试设置适配器处理程序属性的相同行为扩展的自定义行为扩展已在 machine.config 中可用，你会收到错误，就会立即尝试设置属性。</span><span class="sxs-lookup"><span data-stu-id="53558-114">If the custom behavior extension is already available in the machine.config and you try to set the same behavior extension for the adapter handler properties, you get an error as soon as you try to set the property.</span></span>  
  
-   <span data-ttu-id="53558-115">如果已经为适配器处理程序属性设置了自定义行为扩展，然后用同样的行为扩展更新 machine.config 时，会收到运行时错误，并且还会在事件日志中记录此错误。</span><span class="sxs-lookup"><span data-stu-id="53558-115">If the custom behavior extension is already set for the adapter handler properties and you then update the machine.config with the same behavior extension, you will get a runtime error and it is also logged in the event log.</span></span> <span data-ttu-id="53558-116">接收位置也被禁用。</span><span class="sxs-lookup"><span data-stu-id="53558-116">The receive location is also disabled.</span></span>  
  
-   <span data-ttu-id="53558-117">设置适配器处理程序属性之前，必须存在在全局程序集缓存 (GAC) 中的自定义行为扩展所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="53558-117">The assemblies referred in the custom behavior extension must be present in the Global Assembly Cache (GAC) before you set the adapter handler properties.</span></span>  
  
## <a name="configuring-the-adapter-handler-properties"></a><span data-ttu-id="53558-118">配置适配器处理程序属性</span><span class="sxs-lookup"><span data-stu-id="53558-118">Configuring the Adapter Handler Properties</span></span>  
 <span data-ttu-id="53558-119">使用以下过程来配置 WCF CustomIsolated 接收处理程序。</span><span class="sxs-lookup"><span data-stu-id="53558-119">Use the following procedure to configure a WCF-CustomIsolated receive handler.</span></span>  
  
#### <a name="to-configure-the-adapter-handler-properties"></a><span data-ttu-id="53558-120">若要配置的适配器处理程序属性</span><span class="sxs-lookup"><span data-stu-id="53558-120">To configure the adapter handler properties</span></span>  
  
1.  <span data-ttu-id="53558-121">在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**。</span><span class="sxs-lookup"><span data-stu-id="53558-121">In the BizTalk Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="53558-122">在展开的适配器列表中，单击**WCF CustomIsolated**，而是在右窗格中，右键单击你想要配置，接收处理程序，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="53558-122">In the expanded adapter list, click **WCF-CustomIsolated**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="53558-123">在**适配器处理程序属性**对话框中，在**常规**选项卡上，在**主机名**列表中，选择接收处理程序将与之相关联，该主机，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="53558-123">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="53558-124">在**WCF CustomIsolated 传输属性**对话框中，在**WCF 扩展**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="53558-124">In the **WCF-CustomIsolated Transport Properties** dialog box, on the **WCF Extensions** tab, do the following:</span></span>  
  
    |<span data-ttu-id="53558-125">使用此选项</span><span class="sxs-lookup"><span data-stu-id="53558-125">Use this</span></span>|<span data-ttu-id="53558-126">执行的操作</span><span class="sxs-lookup"><span data-stu-id="53558-126">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="53558-127">**导入**</span><span class="sxs-lookup"><span data-stu-id="53558-127">**Import**</span></span>|<span data-ttu-id="53558-128">导入带有 WCF 自定义行为扩展的 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="53558-128">Imports a WCF configuration file with WCF custom behavior extensions.</span></span> <span data-ttu-id="53558-129">单击此按钮将打开**导入 WCF 配置**对话框中浏览并找到 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="53558-129">Clicking this button opens the **Import WCF configuration** dialog box to browse and locate a WCF configuration file.</span></span> <span data-ttu-id="53558-130">请注意，该文件应是有效的 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="53558-130">Note that the file should be a valid WCF configuration file.</span></span> <span data-ttu-id="53558-131">有关 WCF 配置架构的详细信息，请参阅"Windows Communication Foundation 配置架构"在[http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953)。</span><span class="sxs-lookup"><span data-stu-id="53558-131">For more information about WCF configuration schema, see “Windows Communication Foundation Configuration Schema” at [http://go.microsoft.com/fwlink/?LinkId=163953](http://go.microsoft.com/fwlink/?LinkId=163953).</span></span>|  
    |<span data-ttu-id="53558-132">**导出**</span><span class="sxs-lookup"><span data-stu-id="53558-132">**Export**</span></span>|<span data-ttu-id="53558-133">将 WCF 自定义行为扩展导出到 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="53558-133">Exports the WCF custom behavior extension to a WCF configuration file.</span></span> <span data-ttu-id="53558-134">单击此按钮将打开**导出 WCF 配置**对话框中，以浏览并保存 WCF 配置文件。</span><span class="sxs-lookup"><span data-stu-id="53558-134">Clicking this button opens the **Export WCF configuration** dialog box to browse and save the WCF configuration file.</span></span>|  
    |<span data-ttu-id="53558-135">**Clear**</span><span class="sxs-lookup"><span data-stu-id="53558-135">**Clear**</span></span>|<span data-ttu-id="53558-136">清除适配器处理程序属性中的现有 WCF 自定义行为扩展。</span><span class="sxs-lookup"><span data-stu-id="53558-136">Clears the existing WCF custom behavior extension from the adapter handler properties.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53558-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53558-137">See Also</span></span>  
 [<span data-ttu-id="53558-138">配置 WCF CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="53558-138">Configuring the WCF-CustomIsolated Adapter</span></span>](../core/configuring-the-wcf-customisolated-adapter.md)