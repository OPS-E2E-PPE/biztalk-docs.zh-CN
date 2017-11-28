---
title: "如何将 BAM 侦听器行为添加到 Machine.config 文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ea09925-264f-4976-8e34-f63bad70f886
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abc8845333389c95ea52d440437935d4c4867dc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-the-bam-interceptor-behavior-to-the-machineconfig-file"></a><span data-ttu-id="d5210-102">如何将 BAM 侦听器行为添加到 Machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="d5210-102">How to Add the BAM Interceptor Behavior to the Machine.config File</span></span>
<span data-ttu-id="d5210-103">若要截获 BAM 中的数据，必须向 Microsoft .NET 的 machine.config 文件添加 BAM 侦听器行为。</span><span class="sxs-lookup"><span data-stu-id="d5210-103">To intercept data in BAM, you must add the BAM interceptor behavior to the Microsoft .NET machine.config file.</span></span> <span data-ttu-id="d5210-104">可以采取两种方式来实现此目的：</span><span class="sxs-lookup"><span data-stu-id="d5210-104">You can do this in two ways:</span></span>  
  
-   <span data-ttu-id="d5210-105">通过手动编辑 machine.config 文件来添加此行为。</span><span class="sxs-lookup"><span data-stu-id="d5210-105">Manually edit the machine.config file to include the behavior.</span></span>  
  
-   <span data-ttu-id="d5210-106">使用服务配置编辑器来添加此行为。</span><span class="sxs-lookup"><span data-stu-id="d5210-106">Use the Service Configuration Editor to include the behavior.</span></span>  
  
### <a name="to-manually-edit-the-machineconfig-file"></a><span data-ttu-id="d5210-107">手动编辑 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="d5210-107">To manually edit the machine.config file</span></span>  
  
1.  <span data-ttu-id="d5210-108">编辑位于 Microsoft .NET 配置文件夹中的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="d5210-108">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="d5210-109">若要执行此操作，请单击**启动**，单击**运行**，键入记事本 c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d5210-109">To do this, click **Start**, click **Run**, type notepad c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="d5210-110">使用下面的行为扩展更新 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="d5210-110">Update the machine.config file with the following behavior extensions.</span></span>  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="BAMEndPointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="d5210-111">关闭并保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="d5210-111">Close and save the machine.config file.</span></span>  
  
#### <a name="to-edit-the-machineconfig-file-using-the-service-configuration-editor"></a><span data-ttu-id="d5210-112">使用服务配置编辑器编辑 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="d5210-112">To edit the machine.config file using the Service Configuration Editor</span></span>  
  
1.  <span data-ttu-id="d5210-113">打开服务配置编辑器。</span><span class="sxs-lookup"><span data-stu-id="d5210-113">Open the Service Configuration Editor.</span></span> <span data-ttu-id="d5210-114">有关使用服务配置编辑器的信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=83557](http://go.microsoft.com/fwlink/?LinkId=83557)。</span><span class="sxs-lookup"><span data-stu-id="d5210-114">For information about using the Service Configuration Editor, see [http://go.microsoft.com/fwlink/?LinkId=83557](http://go.microsoft.com/fwlink/?LinkId=83557).</span></span>  
  
2.  <span data-ttu-id="d5210-115">在树视图窗格中 (标记为**配置**)，展开节点树。</span><span class="sxs-lookup"><span data-stu-id="d5210-115">In the tree view pane (labeled **Configuration**), expand the node tree.</span></span> <span data-ttu-id="d5210-116">单击**高级**文件夹中，单击**扩展**文件夹，，然后选择**行为元素扩展**元素。</span><span class="sxs-lookup"><span data-stu-id="d5210-116">Click the **Advanced** folder, click the **Extensions** folder, and then select the **behavior element extensions** element.</span></span>  
  
3.  <span data-ttu-id="d5210-117">创建新的行为元素扩展。</span><span class="sxs-lookup"><span data-stu-id="d5210-117">Create a new behavior element extension.</span></span> <span data-ttu-id="d5210-118">单击**新建**按钮以打开扩展配置元素编辑器对话框。</span><span class="sxs-lookup"><span data-stu-id="d5210-118">Click the **New** button to open the Extension Configuration Element Editor dialog box.</span></span> <span data-ttu-id="d5210-119">在**配置名称**输入的行为，例如 BAMEndPointBehaviorExtension 的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="d5210-119">In **Configuration Name** enter a unique name for the behavior, for example BAMEndPointBehaviorExtension.</span></span>  
  
     <span data-ttu-id="d5210-120">![扩展配置元素编辑器](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")</span><span class="sxs-lookup"><span data-stu-id="d5210-120">![Extension Configuration Element Editor](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")</span></span>  
  
4.  <span data-ttu-id="d5210-121">单击**类型**字段，然后再单击省略号按钮 (**...**) 按钮以打开行为扩展类型浏览器对话框。</span><span class="sxs-lookup"><span data-stu-id="d5210-121">Click the **Type** field, and then click the ellipsis button (**...**) button to open the Behavior Extension Type Browser dialog box.</span></span>  
  
5.  <span data-ttu-id="d5210-122">单击全局程序集缓存 (GAC) 图标以列出 GAC 中的 DLL。</span><span class="sxs-lookup"><span data-stu-id="d5210-122">Click the global assembly cache (GAC) icon to list the DLLs in GAC.</span></span>  
  
6.  <span data-ttu-id="d5210-123">选择 Microsoft.BizTalk.Bam.Interceptors 程序集。</span><span class="sxs-lookup"><span data-stu-id="d5210-123">Select the Microsoft.BizTalk.Bam.Interceptors assembly.</span></span>  
  
7.  <span data-ttu-id="d5210-124">单击**打开**按钮以选择该程序集，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="d5210-124">Click the **Open** button to select the assembly, and then close the dialog box.</span></span>  
  
     <span data-ttu-id="d5210-125">![Bejavopr 扩展类型浏览器](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")</span><span class="sxs-lookup"><span data-stu-id="d5210-125">![Bejavopr Extension Type Browser](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")</span></span>  
  
8.  <span data-ttu-id="d5210-126">在“行为扩展类型浏览器”对话框的“类型名称”窗格中，双击 Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior 类型（下面的屏幕截图中突出显示的类型）。</span><span class="sxs-lookup"><span data-stu-id="d5210-126">In the Type Name pane of the Behavior Extension Type Browser dialog box, double-click the Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior type (as highlighted in the following screen).</span></span>  
  
     <span data-ttu-id="d5210-127">![Bejavopr 扩展类型浏览器](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")</span><span class="sxs-lookup"><span data-stu-id="d5210-127">![Bejavopr Extension Type Browser](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")</span></span>  
  
     <span data-ttu-id="d5210-128">这将打开“扩展配置元素编辑器”。</span><span class="sxs-lookup"><span data-stu-id="d5210-128">This opens the Extension Configuration Element Editor.</span></span>  
  
9. <span data-ttu-id="d5210-129">单击**确定**以关闭扩展配置元素编辑器对话框。</span><span class="sxs-lookup"><span data-stu-id="d5210-129">Click **OK** to close the Extension Configuration Element Editor dialog box.</span></span>  
  
10. <span data-ttu-id="d5210-130">在服务配置编辑器的详细信息窗格中，验证 BAMEndPointBehaviorExtension 是否显示。</span><span class="sxs-lookup"><span data-stu-id="d5210-130">In the details pane of the Service Configuration Editor, verify that the BAMEndPointBehaviorExtension appears.</span></span>  
  
11. <span data-ttu-id="d5210-131">关闭服务配置编辑器。</span><span class="sxs-lookup"><span data-stu-id="d5210-131">Close the Service Configuration Editor.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d5210-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d5210-132">Next Steps</span></span>  
 [<span data-ttu-id="d5210-133">如何配置 BAM WCF 截获</span><span class="sxs-lookup"><span data-stu-id="d5210-133">How to Configure the BAM WCF Interception</span></span>](../core/how-to-configure-the-bam-wcf-interception.md)  
  
## <a name="see-also"></a><span data-ttu-id="d5210-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5210-134">See Also</span></span>  
 [<span data-ttu-id="d5210-135">配置 WCF 适配器以截获 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="d5210-135">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)