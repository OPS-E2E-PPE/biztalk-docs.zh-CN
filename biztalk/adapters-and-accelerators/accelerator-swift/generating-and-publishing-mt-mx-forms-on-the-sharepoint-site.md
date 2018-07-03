---
title: 生成和发布 MT MX SharePoint 站点上的窗体 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4adf7117-11ad-4a8e-8d6a-fd78c5e496a3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 492eda3b4bf3d3950c084bc9234b52b911b84a2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980046"
---
# <a name="generating-and-publishing-mtmx-forms-on-the-sharepoint-site"></a><span data-ttu-id="f259f-102">生成和发布在 SharePoint 站点上的 MT/MX 表单</span><span class="sxs-lookup"><span data-stu-id="f259f-102">Generating and Publishing MT/MX Forms on the SharePoint Site</span></span>
<span data-ttu-id="f259f-103">**若要生成和发布 MT/MX 表单上的 SharePoint 站点：**</span><span class="sxs-lookup"><span data-stu-id="f259f-103">**To generate and publish MT/MX forms on a SharePoint site:**</span></span>  

1. <span data-ttu-id="f259f-104">下载表单生成器实用程序，并将其保存在计算机上的本地。</span><span class="sxs-lookup"><span data-stu-id="f259f-104">Download the Form Generator Utility and save it locally on the computer.</span></span>  

2. <span data-ttu-id="f259f-105">打开**FormGenerator.sln**从文件夹上面的下载和编译解决方案。</span><span class="sxs-lookup"><span data-stu-id="f259f-105">Open the **FormGenerator.sln** from the folder downloaded above and compile the solution.</span></span>  

3. <span data-ttu-id="f259f-106">在命令提示符下，访问已编译可执行文件 (FormGenerator.exe) 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f259f-106">At a command prompt, access the folder of compiled executable (FormGenerator.exe).</span></span> <span data-ttu-id="f259f-107">例如，如果您已经生成实用工具在调试模式下，访问 **...\bin\debug**文件夹。</span><span class="sxs-lookup"><span data-stu-id="f259f-107">For example, if you have built the utility in debug mode, access the **..\bin\debug** folder.</span></span>  

4. <span data-ttu-id="f259f-108">键入 FormGenerator.exe [-b] [-\<不可以。</span><span class="sxs-lookup"><span data-stu-id="f259f-108">Type FormGenerator.exe [-b] [-\<No.</span></span> <span data-ttu-id="f259f-109">模板文件夹路径的\>]</span><span class="sxs-lookup"><span data-stu-id="f259f-109">of Template folder paths\>]</span></span>  

    <span data-ttu-id="f259f-110">`<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`的用户。</span><span class="sxs-lookup"><span data-stu-id="f259f-110">`<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`.</span></span> <span data-ttu-id="f259f-111">参数替换为新创建的文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="f259f-111">Replace the parameters with the newly-created folder names.</span></span>  

5. <span data-ttu-id="f259f-112">上述命令还将生成所需的 MX 消息修复的信封架构。</span><span class="sxs-lookup"><span data-stu-id="f259f-112">The above command will also generate the Envelope schema needed for MX message repair.</span></span>  

6. <span data-ttu-id="f259f-113">转到输出文件夹\<DestinationFolderPath\>。</span><span class="sxs-lookup"><span data-stu-id="f259f-113">Go to output folder \<DestinationFolderPath\>.</span></span> <span data-ttu-id="f259f-114">在中\<DestinationFolderPath\>，打开你想要生成窗体的 InfoPath 表单模板的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f259f-114">In \<DestinationFolderPath\>, open the folder of the InfoPath form template for which you want to generate the form.</span></span> <span data-ttu-id="f259f-115">例如，如果你想要生成 MT103 InfoPath 窗体，然后打开在 DestinationFolderPath MT103 文件夹并打开 TemplateDS.sln。</span><span class="sxs-lookup"><span data-stu-id="f259f-115">For example, if you want to generate the MT103 InfoPath form, then open the MT103 folder at the DestinationFolderPath and open the TemplateDS.sln.</span></span>  

7. <span data-ttu-id="f259f-116">在解决方案资源管理器，双击**manifest.xsf**。</span><span class="sxs-lookup"><span data-stu-id="f259f-116">In the Solution Explorer, double click the **manifest.xsf**.</span></span> <span data-ttu-id="f259f-117">它将打开 InfoPath 窗体将需要一些时间才能获取打开的设计的文件。</span><span class="sxs-lookup"><span data-stu-id="f259f-117">It will open the design file of the InfoPath form which will take some time to get opened.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="f259f-118">MX 消息 manifest.xsf 可能需要 2 到 5 分钟，以获取打开。</span><span class="sxs-lookup"><span data-stu-id="f259f-118">The MX messages manifest.xsf might take 2-5 minutes to get opened.</span></span>  

8. <span data-ttu-id="f259f-119">在 manifest.xsf，转到**工具-> 窗体选项-> 安全和信任**菜单选项。</span><span class="sxs-lookup"><span data-stu-id="f259f-119">In the manifest.xsf, go to **Tools ->Form Options-> Security and Trust** menu option.</span></span> <span data-ttu-id="f259f-120">检查**完全信任**必须启用选项的权限。</span><span class="sxs-lookup"><span data-stu-id="f259f-120">Check the **Full Trust** option must be enabled for the permission.</span></span>  

9. <span data-ttu-id="f259f-121">选择**登录此窗体模板**复选框。</span><span class="sxs-lookup"><span data-stu-id="f259f-121">Select the **Sign this form Template** checkbox.</span></span> <span data-ttu-id="f259f-122">单击**选择证书**。</span><span class="sxs-lookup"><span data-stu-id="f259f-122">Click **Select certificate**.</span></span> <span data-ttu-id="f259f-123">在中，选择你想对表单进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="f259f-123">In this, select the certificate with which you want to sign the form.</span></span> <span data-ttu-id="f259f-124">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="f259f-124">Click **OK**.</span></span>  

10. <span data-ttu-id="f259f-125">保存**manifest.xsf**。</span><span class="sxs-lookup"><span data-stu-id="f259f-125">Save **manifest.xsf**.</span></span>  

11. <span data-ttu-id="f259f-126">转到**视图-> 的设计任务**。</span><span class="sxs-lookup"><span data-stu-id="f259f-126">Go to **View -> Design Tasks**.</span></span> <span data-ttu-id="f259f-127">在设计任务窗格中，单击**发布窗体模板**选项。</span><span class="sxs-lookup"><span data-stu-id="f259f-127">On the Design Tasks pane, click **Publish Form Template** option.</span></span>  

12. <span data-ttu-id="f259f-128">在发布向导窗口中，选择**到网络位置**然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f259f-128">In the publishing wizard window, select **To a network location** and click **Next**.</span></span>  

13. <span data-ttu-id="f259f-129">在窗体模板路径和文件名称文本框中，键入<strong>http://localhost/sites/BASSite/Templates/\<MessageType\>.xsn</strong>并键入**\<MessageType\>** 窗体模板中命名文本框，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="f259f-129">In the Form template path and file name textbox, type <strong>http://localhost/sites/BASSite/Templates/\<MessageType\>.xsn</strong> and type **\<MessageType\>** in the Form Template name textbox and click **Next**.</span></span>  

14. <span data-ttu-id="f259f-130">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="f259f-130">Click **Next**.</span></span>  

15. <span data-ttu-id="f259f-131">单击**发布并关闭**。</span><span class="sxs-lookup"><span data-stu-id="f259f-131">Click **Publish and close**.</span></span>  

16. <span data-ttu-id="f259f-132">在 Internet Explorer 中，打开您的 SharePoint 站点**http://localhost/sites/bassite/templates**。</span><span class="sxs-lookup"><span data-stu-id="f259f-132">In the Internet Explorer, open your SharePoint site **http://localhost/sites/bassite/templates**.</span></span>  

17. <span data-ttu-id="f259f-133">指向 **\<MessageType\>**，单击它，旁边的向下箭头，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="f259f-133">Point to **\<MessageType\>**, click the down arrow next to it, and then click **Edit Properties**.</span></span>  

18. <span data-ttu-id="f259f-134">在模板中：\< MessageType\>窗口中的，在 Namespace 框中：</span><span class="sxs-lookup"><span data-stu-id="f259f-134">In the Templates:\< MessageType\> window, in the Namespace box:</span></span>  

    - <span data-ttu-id="f259f-135">如果生成 MT InfoPath 窗体，请键入： **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**</span><span class="sxs-lookup"><span data-stu-id="f259f-135">If you are generating MT InfoPath forms, type: **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**</span></span>  

    - <span data-ttu-id="f259f-136">如果生成 MX InfoPath 表单，请键入： <strong>http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageName\></strong></span><span class="sxs-lookup"><span data-stu-id="f259f-136">If you are generating MX InfoPath forms, type: <strong>http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageName\></strong></span></span>  

       <span data-ttu-id="f259f-137">这将有助于标识与相应的模板的消息实例。</span><span class="sxs-lookup"><span data-stu-id="f259f-137">This will help in identifying the message instance with the corresponding template.</span></span>  

19. <span data-ttu-id="f259f-138">单击**保存并关闭**。</span><span class="sxs-lookup"><span data-stu-id="f259f-138">Click **Save and Close**.</span></span>
