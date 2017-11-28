---
title: "自定义 Web 部件使用的 SAP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b7fecd2-a385-4b2d-a01b-3bfd65ecff3a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5712376abaa24d998f13612a3b74e11f2487e514
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-a-custom-web-part-with-the-sap-adapter"></a><span data-ttu-id="6d5cf-102">使用 SAP 适配器使用自定义 Web 部件</span><span class="sxs-lookup"><span data-stu-id="6d5cf-102">Use a Custom Web Part with the SAP adapter</span></span>
<span data-ttu-id="6d5cf-103">本部分提供有关使用 Microsoft Office SharePoint Server 的自定义 Web 部件的信息。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-103">This section provides information about using a custom Web Part with Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="6d5cf-104">若要使用自定义 Web 部件，您必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6d5cf-104">To use a custom Web Part, you must do the following:</span></span>  
  
1.  <span data-ttu-id="6d5cf-105">创建自定义 Web 部件</span><span class="sxs-lookup"><span data-stu-id="6d5cf-105">Create a custom Web Part</span></span>  
  
2.  <span data-ttu-id="6d5cf-106">将自定义 Web 部件部署到 SharePoint 门户网站</span><span class="sxs-lookup"><span data-stu-id="6d5cf-106">Deploy the custom Web Part to a SharePoint portal</span></span>  
  
3.  <span data-ttu-id="6d5cf-107">配置 SharePoint 门户以使用自定义 Web 部件</span><span class="sxs-lookup"><span data-stu-id="6d5cf-107">Configure the SharePoint portal to use the custom Web Part</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="6d5cf-108">开始之前</span><span class="sxs-lookup"><span data-stu-id="6d5cf-108">Before You Begin</span></span>  
 <span data-ttu-id="6d5cf-109">创建自定义 Web 部件之前：</span><span class="sxs-lookup"><span data-stu-id="6d5cf-109">Before you create a custom Web Part:</span></span>  
  
-   <span data-ttu-id="6d5cf-110">将 SAP 项目作为 WCF 服务发布。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-110">Publish the SAP artifacts as a  WCF service.</span></span> <span data-ttu-id="6d5cf-111">有关详细信息，请参阅[步骤 1： 发布 SAP 项目作为一个 WCF 服务](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md)中[教程 1： 从 SharePoint 站点上的 SAP 系统提供数据](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-111">For more information, see [Step 1: Publish the SAP Artifacts as a WCF Service](../../adapters-and-accelerators/adapter-sap/step-1-publish-the-sap-artifacts-as-a-wcf-service.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
-   <span data-ttu-id="6d5cf-112">创建在 Microsoft Office SharePoint Server 中使用业务数据目录的 SAP 项目的应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-112">Create an application definition file for the SAP artifacts using the Business Data Catalog in Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="6d5cf-113">有关详细信息，请参阅[步骤 2： 为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)中[教程 1： 从 SharePoint 站点上的 SAP 系统提供数据](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-113">For more information, see [Step 2: Create an Application Definition File for the SAP Artifacts](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md) in [Tutorial 1: Presenting Data from an SAP System on a SharePoint Site](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md).</span></span>  
  
##  <span data-ttu-id="6d5cf-114"><a name="Create_a_Custom_Web_Part"></a>步骤 1： 创建自定义 Web 部件</span><span class="sxs-lookup"><span data-stu-id="6d5cf-114"><a name="Create_a_Custom_Web_Part"></a> Step 1: Create a custom Web Part</span></span>  
 <span data-ttu-id="6d5cf-115">若要创建自定义 Web 部件使用 Visual Studio，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6d5cf-115">To create a custom Web Part using Visual Studio, do the following:</span></span>  
  
1.  <span data-ttu-id="6d5cf-116">启动 Visual Studio，然后创建一个项目。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-116">Start Visual Studio, and then create a project.</span></span>  
  
2.  <span data-ttu-id="6d5cf-117">在**新项目**对话框中，从**项目类型**窗格中，选择**Visual C#**。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-117">In the **New Project** dialog box, from the **Project types** pane, select **Visual C#**.</span></span> <span data-ttu-id="6d5cf-118">从**模板**窗格中，选择**类库**。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-118">From the **Templates** pane, select **Class Library**.</span></span>  
  
3.  <span data-ttu-id="6d5cf-119">指定的名称和解决方案的位置。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-119">Specify a name and location for the solution.</span></span> <span data-ttu-id="6d5cf-120">对于本主题中，指定`CustomWebPart`中**名称**和**解决方案名称**框。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-120">For this topic, specify `CustomWebPart` in the **Name** and **Solution Name** boxes.</span></span> <span data-ttu-id="6d5cf-121">指定一个位置，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-121">Specify a location, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="6d5cf-122">将对 System.Web 组件的引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-122">Add a reference to the System.Web component into the project.</span></span> <span data-ttu-id="6d5cf-123">右键单击中的项目名称**解决方案资源管理器**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-123">Right-click the project name in **Solution Explorer**, and then click **Add Reference**.</span></span> <span data-ttu-id="6d5cf-124">在**添加引用**对话框中，选择**System.Web**中**.NET**选项卡上，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-124">In the **Add Reference** dialog box, select **System.Web** in the **.NET** tab, and then click **OK**.</span></span> <span data-ttu-id="6d5cf-125">System.Web 组件包含 System.Web.UI.WebControls.WebParts 的所需命名空间。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-125">The System.Web component contains the required namespace of System.Web.UI.WebControls.WebParts.</span></span>  
  
5.  <span data-ttu-id="6d5cf-126">添加所需的代码，根据你在项目中的问题。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-126">Add the required code based on your issue in the project.</span></span> <span data-ttu-id="6d5cf-127">与某些问题相关的代码示例，请参阅"问题涉及自定义 Web 部件"中[注意事项与 SharePoint 使用 SAP 适配器时](../../adapters-and-accelerators/adapter-sap/considerations-when-using-the-sap-adapter-with-sharepoint.md)。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-127">For the code sample that is relevant to a certain issue, see “Issues Involving Custom Web Parts” in [Considerations when using the SAP adapter with SharePoint](../../adapters-and-accelerators/adapter-sap/considerations-when-using-the-sap-adapter-with-sharepoint.md).</span></span>  
  
6.  <span data-ttu-id="6d5cf-128">生成此项目。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-128">Build the project.</span></span> <span data-ttu-id="6d5cf-129">上的项目的成功生成，.dll 文件，CustomWebPart.dll，将生成在\<项目文件夹 >/bin/Debug 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-129">On successful build of the project, a .dll file, CustomWebPart.dll, will be generated in the \<project folder>/bin/Debug folder.</span></span>  
  
7.  <span data-ttu-id="6d5cf-130">**仅对 64 位计算机**： 在执行以下步骤之前签署 CustomWebPart.dll 文件所用强名称。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-130">**Only for 64-bit computer**: Sign the CustomWebPart.dll file with a strong name before performing the following steps.</span></span> <span data-ttu-id="6d5cf-131">否则，你将无法导入，并因此在 SharePoint 门户中使用 CustomWebPart.dll"步骤 3： 配置 SharePoint 门户以使用自定义 Web 部件。"</span><span class="sxs-lookup"><span data-stu-id="6d5cf-131">Otherwise, you will not be able to import, and hence use the CustomWebPart.dll in the SharePoint portal in “Step 3: Configure the SharePoint Portal to use the custom Web Part.”</span></span> <span data-ttu-id="6d5cf-132">请参阅[如何： 使用强名称为程序集签名](https://msdn.microsoft.com/library/xc31ft41.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-132">See [How to: Sign an Assembly with a Strong Name](https://msdn.microsoft.com/library/xc31ft41.aspx).</span></span>
  
## <a name="step-2-deploy-the-custom-web-part-to-a-sharepoint-portal"></a><span data-ttu-id="6d5cf-133">步骤 2： 将自定义 Web 部件部署到 SharePoint 门户网站</span><span class="sxs-lookup"><span data-stu-id="6d5cf-133">Step 2: Deploy the custom Web Part to a SharePoint Portal</span></span>  
 <span data-ttu-id="6d5cf-134">你必须执行以下操作来使 CustomWebPart.dll 文件 （自定义 Web 部件） 中创建"步骤 1： 创建自定义 Web 部件"的 SharePoint 门户网站上使用本主题：</span><span class="sxs-lookup"><span data-stu-id="6d5cf-134">You must do the following to make the CustomWebPart.dll file (custom Web Part) that is created in “Step 1: Create a custom Web Part” of this topic usable on the SharePoint portal:</span></span>  
  
-   <span data-ttu-id="6d5cf-135">**将 CustomWebPart.dll 文件复制到 SharePoint 门户网站的 bin 文件夹**: Microsoft Office SharePoint Server 创建门户下的\<根驱动器 >: \Inetpub\wwwroot\wss\VirtualDirectories 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-135">**Copy the CustomWebPart.dll file to the bin folder of the SharePoint Portal**: Microsoft Office SharePoint Server creates portals under the \<root drive>:\Inetpub\wwwroot\wss\VirtualDirectories folder.</span></span> <span data-ttu-id="6d5cf-136">文件夹为每个门户中，创建，并且可以使用的端口号来标识。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-136">A folder is created for each portal, and can be identified with the port number.</span></span> <span data-ttu-id="6d5cf-137">必须将复制中创建的 CustomWebPart.dll 文件"步骤 1： 创建自定义 Web 部件"到本主题的\<根驱动器 >: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number > \bin 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-137">You must copy the CustomWebPart.dll file created in “Step 1: Create a custom Web Part” of this topic to the \<root drive>:\Inetpub\wwwroot\wss\VirtualDirectories\\<Port_Number>\bin folder.</span></span> <span data-ttu-id="6d5cf-138">例如，如果你的 SharePoint 门户的端口号是 13614，你必须 CustomWebPart.dll 将文件复制到\<根驱动器 >: \Inetpub\wwwroot\wss\VirtualDirectories\13614\bin 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-138">For example, if the port number of your SharePoint portal is 13614, you must copy the CustomWebPart.dll file to the \<root drive>:\Inetpub\wwwroot\wss\VirtualDirectories\13614\bin folder.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="6d5cf-139">另一种方法来查找 SharePoint 门户网站的文件夹位置是使用**Internet Information Services (IIS) Manager**窗口 (**启动** > **运行** >  **inetmgr**)。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-139">Another way to find the folder location of your SharePoint portal is by using the **Internet Information Services (IIS) Manager** window (**Start** > **Run** > **inetmgr**).</span></span> <span data-ttu-id="6d5cf-140">找到你在中的 SharePoint 门户**Internet Information Services (IIS) Manager**窗口 ([computer_name] > 网站 > [门户名称])，右键单击，然后再单击**属性**中快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-140">Locate your SharePoint portal in the **Internet Information Services (IIS) Manager** window ([computer_name] > Web Sites > [Portal-Name]), right-click, and then click **Properties** in the shortcut menu.</span></span> <span data-ttu-id="6d5cf-141">在 SharePoint 门户的属性对话框中，单击**主目录**选项卡上，然后选择**本地路径**框。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-141">In the properties dialog box of the SharePoint portal, click the **Home Directory** tab, and then select the **Local path** box.</span></span>  
  
-   <span data-ttu-id="6d5cf-142">**在 web.config 文件中添加安全控制项**： 因为不同的计算机上以及由多个用户，则会使用 CustomWebPart.dll 文件，您必须声明为"安全"。 文件</span><span class="sxs-lookup"><span data-stu-id="6d5cf-142">**Add the Safe Control Entry in the web.config File**: Because the CustomWebPart.dll file will be used on different computers and by multiple users, you must declare the file as “safe.”</span></span> <span data-ttu-id="6d5cf-143">为此，请打开 web.config 文件位于 SharePoint 门户文件夹在\<根驱动器 >: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number >。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-143">To do so, open the web.config file located in the SharePoint portal folder at \<root drive>:\Inetpub\wwwroot\wss\VirtualDirectories\\<Port_Number>.</span></span> <span data-ttu-id="6d5cf-144">下`<SafeControls>`部分的 web.config 文件中，添加以下安全控件项：</span><span class="sxs-lookup"><span data-stu-id="6d5cf-144">Under the `<SafeControls>` section of the web.config file, add the following safe control entry:</span></span>  
  
    -   <span data-ttu-id="6d5cf-145">**在 32 位计算机：**</span><span class="sxs-lookup"><span data-stu-id="6d5cf-145">**On 32-bit computer:**</span></span>  
  
        ```  
        <SafeControl Assembly="CustomWebPart" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
        ```  
  
    -   <span data-ttu-id="6d5cf-146">**在 64 位计算机：**</span><span class="sxs-lookup"><span data-stu-id="6d5cf-146">**On 64-bit computer:**</span></span>  
  
        ```  
        <SafeControl Assembly="CustomWebPart, Version=1.0.0.0, Culture=neutral, PublicKeyToken=<PUBLICKKEYTOKEN_OF_CustomWebPart.dll>" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
        ```  
  
     <span data-ttu-id="6d5cf-147">保存 web.config 文件中，并将其关闭。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-147">Save the web.config file, and then close it.</span></span>  
  
## <a name="step-3-configure-the-sharepoint-portal-to-use-the-custom-web-part"></a><span data-ttu-id="6d5cf-148">步骤 3： 配置 SharePoint 门户以使用自定义 Web 部件</span><span class="sxs-lookup"><span data-stu-id="6d5cf-148">Step 3: Configure the SharePoint portal to use the custom Web Part</span></span>  
 <span data-ttu-id="6d5cf-149">你需要将自定义 Web 部件添加到 Microsoft Office SharePoint Server Web 部件库，以便 SharePoint 门户网站上使用它。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-149">You need to add the custom Web Part to the Microsoft Office SharePoint Server Web Part Gallery, so that you can use it on your SharePoint portal.</span></span> <span data-ttu-id="6d5cf-150">为此：</span><span class="sxs-lookup"><span data-stu-id="6d5cf-150">To do so:</span></span>  
  
1.  <span data-ttu-id="6d5cf-151">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-151">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="6d5cf-152">单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="6d5cf-152">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="6d5cf-153">在左侧的导航窗格中，单击名称的共享服务提供程序 (SSP) 你想要添加自定义 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-153">In the left navigation pane, click the name of the Shared Service Provider (SSP) to which you want to add the custom Web Part.</span></span>  
  
3.  <span data-ttu-id="6d5cf-154">在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-154">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
4.  <span data-ttu-id="6d5cf-155">在站点设置页上，单击**Web 部件**下**库**列。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-155">On the Site Settings page, click **Web Parts** under the **Galleries** column.</span></span>  
  
5.  <span data-ttu-id="6d5cf-156">在 Web 部件库页上，若要将自定义 Web 部件添加到库，请单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-156">On the Web Part Gallery page, to add the custom Web Part to the gallery,  click **New**.</span></span> <span data-ttu-id="6d5cf-157">此时没有 Web 部件库页上可用的自定义 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-157">At this point the custom Web Part is not available in the Web Part Gallery page.</span></span>  
  
6.  <span data-ttu-id="6d5cf-158">在新的 Web 部件页上，找到**CustomWebPart** （自定义 Web 部件的名称） 在列表中，选择左侧上的复选框，然后单击**导入库**页面顶部。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-158">On the New Web Parts page, locate **CustomWebPart** (name of the custom Web Part) in the list, select the check box on the left, and then click **Populate Gallery** on the top of the page.</span></span> <span data-ttu-id="6d5cf-159">这将添加**CustomWebPart** Web 部件库页中的条目。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-159">This will add the **CustomWebPart** entry in the Web Part Gallery page.</span></span>  
  
 <span data-ttu-id="6d5cf-160">现在，你可以使用自定义 Web 部件 (**CustomWebPart**) 在你的 SharePoint 门户中创建 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-160">Now you can use the custom Web Part (**CustomWebPart**) to create Web Parts in your SharePoint portal.</span></span> <span data-ttu-id="6d5cf-161">自定义 Web 部件 (**CustomWebPart**) 将出现在**杂项**中添加 Web 部件页的部分。</span><span class="sxs-lookup"><span data-stu-id="6d5cf-161">The custom Web Part (**CustomWebPart**) will appear under the **Miscellaneous** section in the Add Web Parts page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d5cf-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d5cf-162">See Also</span></span>  
[<span data-ttu-id="6d5cf-163">使用带有 SharePoint SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="6d5cf-163">Use the SAP adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)