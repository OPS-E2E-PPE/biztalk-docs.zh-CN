---
title: 如何将 BAM 侦听器行为添加到 Machine.config 文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ea09925-264f-4976-8e34-f63bad70f886
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20ef2ac191a50929be06fb5093d93382b63d2959
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387304"
---
# <a name="how-to-add-the-bam-interceptor-behavior-to-the-machineconfig-file"></a><span data-ttu-id="8e5d1-102">如何将 BAM 侦听器行为添加到 Machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="8e5d1-102">How to Add the BAM Interceptor Behavior to the Machine.config File</span></span>
<span data-ttu-id="8e5d1-103">若要截获 BAM 中的数据，必须将 BAM 侦听器行为添加到 Microsoft.NET 的 machine.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-103">To intercept data in BAM, you must add the BAM interceptor behavior to the Microsoft .NET machine.config file.</span></span> <span data-ttu-id="8e5d1-104">可以通过两种方式来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="8e5d1-104">You can do this in two ways:</span></span>  
  
-   <span data-ttu-id="8e5d1-105">手动编辑 machine.config 文件来添加此行为。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-105">Manually edit the machine.config file to include the behavior.</span></span>  
  
-   <span data-ttu-id="8e5d1-106">使用服务配置编辑器来添加此行为。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-106">Use the Service Configuration Editor to include the behavior.</span></span>  
  
### <a name="to-manually-edit-the-machineconfig-file"></a><span data-ttu-id="8e5d1-107">若要手动编辑 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="8e5d1-107">To manually edit the machine.config file</span></span>  
  
1.  <span data-ttu-id="8e5d1-108">编辑 machine.config 文件位于 Microsoft.NET 配置文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-108">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="8e5d1-109">若要执行此操作，请单击**启动**，单击**运行**，键入记事本 c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-109">To do this, click **Start**, click **Run**, type notepad c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="8e5d1-110">使用以下行为扩展更新 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-110">Update the machine.config file with the following behavior extensions.</span></span>  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="BAMEndPointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="8e5d1-111">关闭并保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-111">Close and save the machine.config file.</span></span>  
  
#### <a name="to-edit-the-machineconfig-file-using-the-service-configuration-editor"></a><span data-ttu-id="8e5d1-112">若要编辑使用服务配置编辑器的 machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="8e5d1-112">To edit the machine.config file using the Service Configuration Editor</span></span>  
  
1.  <span data-ttu-id="8e5d1-113">打开服务配置编辑器。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-113">Open the Service Configuration Editor.</span></span> <span data-ttu-id="8e5d1-114">有关使用服务配置编辑器的信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=83557 ](http://go.microsoft.com/fwlink/?LinkId=83557)。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-114">For information about using the Service Configuration Editor, see [http://go.microsoft.com/fwlink/?LinkId=83557](http://go.microsoft.com/fwlink/?LinkId=83557).</span></span>  
  
2.  <span data-ttu-id="8e5d1-115">在树视图窗格中 (标记为**配置**)，展开节点树。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-115">In the tree view pane (labeled **Configuration**), expand the node tree.</span></span> <span data-ttu-id="8e5d1-116">单击**高级**文件夹中，单击**扩展**文件夹，，然后选择**行为元素扩展**元素。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-116">Click the **Advanced** folder, click the **Extensions** folder, and then select the **behavior element extensions** element.</span></span>  
  
3.  <span data-ttu-id="8e5d1-117">创建一个新的行为元素扩展。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-117">Create a new behavior element extension.</span></span> <span data-ttu-id="8e5d1-118">单击**新建**按钮以打开扩展配置元素编辑器对话框。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-118">Click the **New** button to open the Extension Configuration Element Editor dialog box.</span></span> <span data-ttu-id="8e5d1-119">在中**配置名称**输入的行为，例如 BAMEndPointBehaviorExtension 的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-119">In **Configuration Name** enter a unique name for the behavior, for example BAMEndPointBehaviorExtension.</span></span>  
  
     <span data-ttu-id="8e5d1-120">![扩展配置元素编辑器](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")</span><span class="sxs-lookup"><span data-stu-id="8e5d1-120">![Extension Configuration Element Editor](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")</span></span>  
  
4.  <span data-ttu-id="8e5d1-121">单击**类型**字段，，然后单击省略号按钮 (**...**) 按钮以打开行为扩展类型浏览器对话框。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-121">Click the **Type** field, and then click the ellipsis button (**...**) button to open the Behavior Extension Type Browser dialog box.</span></span>  
  
5.  <span data-ttu-id="8e5d1-122">单击全局程序集缓存 (GAC) 图标以列出 GAC 中的 Dll。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-122">Click the global assembly cache (GAC) icon to list the DLLs in GAC.</span></span>  
  
6.  <span data-ttu-id="8e5d1-123">选择 Microsoft.BizTalk.Bam.Interceptors 程序集。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-123">Select the Microsoft.BizTalk.Bam.Interceptors assembly.</span></span>  
  
7.  <span data-ttu-id="8e5d1-124">单击**打开**按钮以选择的程序集，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-124">Click the **Open** button to select the assembly, and then close the dialog box.</span></span>  
  
     <span data-ttu-id="8e5d1-125">![Bejavopr 扩展类型浏览器](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")</span><span class="sxs-lookup"><span data-stu-id="8e5d1-125">![Bejavopr Extension Type Browser](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")</span></span>  
  
8.  <span data-ttu-id="8e5d1-126">在行为扩展类型浏览器对话框中的类型名称窗格中，双击 Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior 类型 （如以下屏幕中，突出显示部分）。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-126">In the Type Name pane of the Behavior Extension Type Browser dialog box, double-click the Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior type (as highlighted in the following screen).</span></span>  
  
     <span data-ttu-id="8e5d1-127">![Bejavopr 扩展类型浏览器](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")</span><span class="sxs-lookup"><span data-stu-id="8e5d1-127">![Bejavopr Extension Type Browser](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")</span></span>  
  
     <span data-ttu-id="8e5d1-128">这将打开扩展配置元素编辑器。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-128">This opens the Extension Configuration Element Editor.</span></span>  
  
9. <span data-ttu-id="8e5d1-129">单击**确定**以关闭扩展配置元素编辑器对话框。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-129">Click **OK** to close the Extension Configuration Element Editor dialog box.</span></span>  
  
10. <span data-ttu-id="8e5d1-130">在服务配置编辑器的详细信息窗格中，验证 bamendpointbehaviorextension 显示。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-130">In the details pane of the Service Configuration Editor, verify that the BAMEndPointBehaviorExtension appears.</span></span>  
  
11. <span data-ttu-id="8e5d1-131">关闭服务配置编辑器。</span><span class="sxs-lookup"><span data-stu-id="8e5d1-131">Close the Service Configuration Editor.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8e5d1-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8e5d1-132">Next Steps</span></span>  
 [<span data-ttu-id="8e5d1-133">如何配置 BAM WCF 侦听</span><span class="sxs-lookup"><span data-stu-id="8e5d1-133">How to Configure the BAM WCF Interception</span></span>](../core/how-to-configure-the-bam-wcf-interception.md)  
  
## <a name="see-also"></a><span data-ttu-id="8e5d1-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e5d1-134">See Also</span></span>  
 [<span data-ttu-id="8e5d1-135">配置 WCF 适配器以侦听 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="8e5d1-135">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)