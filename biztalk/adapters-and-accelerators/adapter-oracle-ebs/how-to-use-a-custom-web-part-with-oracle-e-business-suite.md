---
title: 如何使用自定义 web 部件与 Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf420061-41d1-4d97-9be1-403cd101e41c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83f1dc0b3b46ff8e76ce4dc6dbd9bffd1acdf919
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988238"
---
# <a name="how-to-use-a-custom-web-part-with-oracle-e-business-suite"></a><span data-ttu-id="2c205-102">如何使用 Oracle E-business Suite 的自定义 web 部件</span><span class="sxs-lookup"><span data-stu-id="2c205-102">How to use a custom web part with Oracle E-Business Suite</span></span>
<span data-ttu-id="2c205-103">本部分提供有关 Microsoft Office SharePoint Server 中使用自定义 Web 部件的信息。</span><span class="sxs-lookup"><span data-stu-id="2c205-103">This section provides information about using a custom Web Part with Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="2c205-104">若要使用自定义 Web 部件，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2c205-104">To use a custom Web Part, you must do the following:</span></span>  
  
1.  <span data-ttu-id="2c205-105">创建自定义 Web 部件</span><span class="sxs-lookup"><span data-stu-id="2c205-105">Create a custom Web Part</span></span>  
  
2.  <span data-ttu-id="2c205-106">将自定义 Web 部件部署到 SharePoint 门户网站</span><span class="sxs-lookup"><span data-stu-id="2c205-106">Deploy the custom Web Part to a SharePoint portal</span></span>  
  
3.  <span data-ttu-id="2c205-107">配置 SharePoint 门户以使用自定义 Web 部件</span><span class="sxs-lookup"><span data-stu-id="2c205-107">Configure the SharePoint portal to use the custom Web Part</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="2c205-108">开始之前</span><span class="sxs-lookup"><span data-stu-id="2c205-108">Before You Begin</span></span>  
 <span data-ttu-id="2c205-109">创建自定义 Web 部件之前：</span><span class="sxs-lookup"><span data-stu-id="2c205-109">Before you create a custom Web Part:</span></span>  
  
-   <span data-ttu-id="2c205-110">将 Oracle E-business Suite 项目发布为 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="2c205-110">Publish the Oracle E-Business Suite artifacts as a  WCF service.</span></span> <span data-ttu-id="2c205-111">有关详细信息，请参阅[步骤 1： 使用 Oracle E-business 适配器创建和发布 WCF 服务](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md)中[教程： 从 Oracle E-business Suite 的 SharePoint 站点上呈现数据](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)。</span><span class="sxs-lookup"><span data-stu-id="2c205-111">For more information, see [Step 1: Use the Oracle E-Business Adapter to create and publish a WCF service](../../adapters-and-accelerators/adapter-oracle-ebs/step-1-use-the-oracle-e-business-adapter-to-create-and-publish-a-wcf-service.md) in [Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md).</span></span>  
  
-   <span data-ttu-id="2c205-112">创建使用 Microsoft Office SharePoint Server 中的业务数据目录的 Oracle E-business Suite 项目应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="2c205-112">Create an application definition file for the Oracle E-Business Suite artifacts using the Business Data Catalog in Microsoft Office SharePoint Server.</span></span> <span data-ttu-id="2c205-113">有关详细信息，请参阅[步骤 2： 创建用于 Oracle E-business Suite 项目的应用程序定义文件](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)中[教程： 从 Oracle E-business Suite 的 SharePoint 站点上呈现数据](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)。</span><span class="sxs-lookup"><span data-stu-id="2c205-113">For more information, see [Step 2: Create an application definition file for the Oracle E-Business Suite artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md) in [Tutorial: Present data from Oracle E-Business Suite on a SharePoint Site](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md).</span></span>  
  
##  <a name="Create_a_Custom_Web_Part"></a> <span data-ttu-id="2c205-114">步骤 1： 创建自定义 Web 部件</span><span class="sxs-lookup"><span data-stu-id="2c205-114">Step 1: Create a custom Web Part</span></span>  
  
1.  <span data-ttu-id="2c205-115">启动 Visual Studio 中，并创建一个项目。</span><span class="sxs-lookup"><span data-stu-id="2c205-115">Start Visual Studio, and then create a project.</span></span>  
  
2.  <span data-ttu-id="2c205-116">在中**新的项目**对话框中，从**项目类型**窗格中，选择**Visual C#**。</span><span class="sxs-lookup"><span data-stu-id="2c205-116">In the **New Project** dialog box, from the **Project types** pane, select **Visual C#**.</span></span> <span data-ttu-id="2c205-117">从**模板**窗格中，选择**类库**。</span><span class="sxs-lookup"><span data-stu-id="2c205-117">From the **Templates** pane, select **Class Library**.</span></span>  
  
3.  <span data-ttu-id="2c205-118">指定的名称和位置的解决方案。</span><span class="sxs-lookup"><span data-stu-id="2c205-118">Specify a name and location for the solution.</span></span> <span data-ttu-id="2c205-119">对于本主题中，指定`CustomWebPart`中**名称**并**解决方案名称**框。</span><span class="sxs-lookup"><span data-stu-id="2c205-119">For this topic, specify `CustomWebPart` in the **Name** and **Solution Name** boxes.</span></span> <span data-ttu-id="2c205-120">指定一个位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="2c205-120">Specify a location, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="2c205-121">将对 System.Web 组件的引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="2c205-121">Add a reference to the System.Web component into the project.</span></span> <span data-ttu-id="2c205-122">右键单击项目名称在**解决方案资源管理器**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="2c205-122">Right-click the project name in **Solution Explorer**, and then click **Add Reference**.</span></span> <span data-ttu-id="2c205-123">在中**添加引用**对话框中，选择**System.Web**中 **.NET**选项卡，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="2c205-123">In the **Add Reference** dialog box, select **System.Web** in the **.NET** tab, and then click **OK**.</span></span> <span data-ttu-id="2c205-124">System.Web 组件包含所需的 System.Web.UI.WebControls.WebParts 命名空间。</span><span class="sxs-lookup"><span data-stu-id="2c205-124">The System.Web component contains the required namespace of System.Web.UI.WebControls.WebParts.</span></span>  
  
5.  <span data-ttu-id="2c205-125">添加基于你在项目中的问题所需的代码。</span><span class="sxs-lookup"><span data-stu-id="2c205-125">Add the required code based on your issue in the project.</span></span> <span data-ttu-id="2c205-126">与某些问题相关的代码示例，请参阅"问题涉及自定义 Web 部件"中[与 SharePoint 结合使用 Oracle Business Suite 适配器时的注意事项](../../adapters-and-accelerators/adapter-oracle-ebs/considerations-using-the-oracle-business-suite-adapter-with-sharepoint.md)。</span><span class="sxs-lookup"><span data-stu-id="2c205-126">For the code sample that is relevant to a certain issue, see “Issues Involving Custom Web Parts” in [Considerations using the Oracle-Business Suite adapter with SharePoint](../../adapters-and-accelerators/adapter-oracle-ebs/considerations-using-the-oracle-business-suite-adapter-with-sharepoint.md).</span></span>  
  
6.  <span data-ttu-id="2c205-127">生成此项目。</span><span class="sxs-lookup"><span data-stu-id="2c205-127">Build the project.</span></span> <span data-ttu-id="2c205-128">在项目的成功生成，.dll 文件，CustomWebPart.dll，将在其中生成\<项目文件夹 \> /bin/Debug 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2c205-128">On successful build of the project, a .dll file, CustomWebPart.dll, will be generated in the \<project folder\>/bin/Debug folder.</span></span>  
  
7.  <span data-ttu-id="2c205-129">**只为 64 位计算机**： 使用强名称为 CustomWebPart.dll 文件签名然后再执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="2c205-129">**Only for 64-bit computer**: Sign the CustomWebPart.dll file with a strong name before performing the following steps.</span></span> <span data-ttu-id="2c205-130">否则，你将无法导入，并因此在 SharePoint 门户中使用 CustomWebPart.dll"步骤 3： 配置 SharePoint 门户以使用自定义 Web 部件。"</span><span class="sxs-lookup"><span data-stu-id="2c205-130">Otherwise, you will not be able to import, and hence use the CustomWebPart.dll in the SharePoint portal in “Step 3: Configure the SharePoint Portal to use the custom Web Part.”</span></span> <span data-ttu-id="2c205-131">有关如何为程序集具有强名称签名的信息，请参阅[如何： 使用强名称为程序集签名](https://msdn.microsoft.com/library/xc31ft41.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2c205-131">For information about how to sign an assembly with a strong name, see [How to: Sign an Assembly with a Strong Name](https://msdn.microsoft.com/library/xc31ft41.aspx).</span></span>
  
## <a name="step-2-deploy-the-custom-web-part-to-a-sharepoint-portal"></a><span data-ttu-id="2c205-132">步骤 2： 将自定义 Web 部件部署到 SharePoint 门户网站</span><span class="sxs-lookup"><span data-stu-id="2c205-132">Step 2: Deploy the custom Web Part to a SharePoint Portal</span></span>  
 <span data-ttu-id="2c205-133">必须执行以下操作来使 CustomWebPart.dll 文件 （自定义 Web 部件） 中创建的"步骤 1： 创建自定义 Web 部件"的 SharePoint 门户上可使用本主题：</span><span class="sxs-lookup"><span data-stu-id="2c205-133">You must do the following to make the CustomWebPart.dll file (custom Web Part) that is created in “Step 1: Create a custom Web Part” of this topic usable on the SharePoint portal:</span></span>  
  
- <span data-ttu-id="2c205-134">**将 CustomWebPart.dll 文件复制到 bin 文件夹中的 SharePoint Portal**: Microsoft Office SharePoint Server 创建下的门户网站\<根驱动器\>: \Inetpub\wwwroot\wss\VirtualDirectories 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2c205-134">**Copy the CustomWebPart.dll file to the bin folder of the SharePoint Portal**: Microsoft Office SharePoint Server creates portals under the \<root drive\>:\Inetpub\wwwroot\wss\VirtualDirectories folder.</span></span> <span data-ttu-id="2c205-135">文件夹创建每个门户中，并可以使用的端口号标识。</span><span class="sxs-lookup"><span data-stu-id="2c205-135">A folder is created for each portal, and can be identified with the port number.</span></span> <span data-ttu-id="2c205-136">必须将 CustomWebPart.dll 文件中创建"步骤 1： 创建自定义 Web 部件"到本主题的\<根驱动器\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number\>\bin 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2c205-136">You must copy the CustomWebPart.dll file created in “Step 1: Create a custom Web Part” of this topic to the \<root drive\>:\Inetpub\wwwroot\wss\VirtualDirectories\\<Port_Number\>\bin folder.</span></span> <span data-ttu-id="2c205-137">例如，如果你的 SharePoint 门户的端口号是 13614，您必须 CustomWebPart.dll 文件复制到\<根驱动器\>: \Inetpub\wwwroot\wss\VirtualDirectories\13614\bin 文件夹。</span><span class="sxs-lookup"><span data-stu-id="2c205-137">For example, if the port number of your SharePoint portal is 13614, you must copy the CustomWebPart.dll file to the \<root drive\>:\Inetpub\wwwroot\wss\VirtualDirectories\13614\bin folder.</span></span>  
  
  > [!TIP]
  >  <span data-ttu-id="2c205-138">若要查找你的 SharePoint 门户的文件夹位置的另一种方法是使用**Internet 信息服务 (IIS) 管理器**窗口 (**启动** > **运行** >  **inetmgr**)。</span><span class="sxs-lookup"><span data-stu-id="2c205-138">Another way to find the folder location of your SharePoint portal is by using the **Internet Information Services (IIS) Manager** window (**Start** > **Run** > **inetmgr**).</span></span> <span data-ttu-id="2c205-139">找到你的 SharePoint 门户中**Internet 信息服务 (IIS) 管理器**窗口 ([computer_name] > 网站 > [门户名称])，右键单击，然后单击**属性**中快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="2c205-139">Locate your SharePoint portal in the **Internet Information Services (IIS) Manager** window ([computer_name] > Web Sites > [Portal-Name]), right-click, and then click **Properties** in the shortcut menu.</span></span> <span data-ttu-id="2c205-140">在 SharePoint 门户的属性对话框中，单击**主目录**选项卡，然后选择**本地路径**框。</span><span class="sxs-lookup"><span data-stu-id="2c205-140">In the properties dialog box of the SharePoint portal, click the **Home Directory** tab, and then select the **Local path** box.</span></span>  
  
- <span data-ttu-id="2c205-141">**在 web.config 文件中添加安全控件项**： 因为 CustomWebPart.dll 文件用于不同的计算机上，并由多个用户，必须声明为"安全"。 文件</span><span class="sxs-lookup"><span data-stu-id="2c205-141">**Add the Safe Control Entry in the web.config File**: Because the CustomWebPart.dll file will be used on different computers and by multiple users, you must declare the file as “safe.”</span></span> <span data-ttu-id="2c205-142">为此，请打开 web.config 文件位于 SharePoint 门户文件夹在\<根驱动器\>: \Inetpub\wwwroot\wss\VirtualDirectories\\< Port_Number\>。</span><span class="sxs-lookup"><span data-stu-id="2c205-142">To do so, open the web.config file located in the SharePoint portal folder at \<root drive\>:\Inetpub\wwwroot\wss\VirtualDirectories\\<Port_Number\>.</span></span> <span data-ttu-id="2c205-143">下`<SafeControls>`部分中的 web.config 文件中，添加以下安全控件项：</span><span class="sxs-lookup"><span data-stu-id="2c205-143">Under the `<SafeControls>` section of the web.config file, add the following safe control entry:</span></span>  
  
  - <span data-ttu-id="2c205-144">**在 32 位计算机：**</span><span class="sxs-lookup"><span data-stu-id="2c205-144">**On 32-bit computer:**</span></span>  
  
    ```  
    <SafeControl Assembly="CustomWebPart" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
  - <span data-ttu-id="2c205-145">**在 64 位计算机：**</span><span class="sxs-lookup"><span data-stu-id="2c205-145">**On 64-bit computer:**</span></span>  
  
    ```  
    <SafeControl Assembly="CustomWebPart, Version=1.0.0.0, Culture=neutral, PublicKeyToken=<PUBLICKKEYTOKEN_OF_CustomWebPart.dll>" Namespace="CustomWebPart" TypeName="*" Safe="True" />  
    ```  
  
    <span data-ttu-id="2c205-146">保存 web.config 文件中，并将其关闭。</span><span class="sxs-lookup"><span data-stu-id="2c205-146">Save the web.config file, and then close it.</span></span>  
  
## <a name="step-3-configure-the-sharepoint-portal-to-use-the-custom-web-part"></a><span data-ttu-id="2c205-147">步骤 3： 配置 SharePoint 门户以使用自定义 Web 部件</span><span class="sxs-lookup"><span data-stu-id="2c205-147">Step 3: Configure the SharePoint portal to use the custom Web Part</span></span>  
 <span data-ttu-id="2c205-148">需要将自定义 Web 部件添加到 Microsoft Office SharePoint Server Web 部件库，以便 SharePoint 门户网站上使用它。</span><span class="sxs-lookup"><span data-stu-id="2c205-148">You need to add the custom Web Part to the Microsoft Office SharePoint Server Web Part Gallery, so that you can use it on your SharePoint portal.</span></span> <span data-ttu-id="2c205-149">为此：</span><span class="sxs-lookup"><span data-stu-id="2c205-149">To do so:</span></span>  
  
1. <span data-ttu-id="2c205-150">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="2c205-150">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="2c205-151">单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="2c205-151">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2. <span data-ttu-id="2c205-152">在左侧的导航窗格中，单击名称的共享服务提供程序 (SSP) 你想要添加自定义 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="2c205-152">In the left navigation pane, click the name of the Shared Service Provider (SSP) to which you want to add the custom Web Part.</span></span>  
  
3. <span data-ttu-id="2c205-153">在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="2c205-153">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
4. <span data-ttu-id="2c205-154">在站点设置页上单击**Web 部件**下**库**列。</span><span class="sxs-lookup"><span data-stu-id="2c205-154">On the Site Settings page, click **Web Parts** under the **Galleries** column.</span></span>  
  
5. <span data-ttu-id="2c205-155">在 Web 部件库页上，若要将自定义 Web 部件添加到库，请单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="2c205-155">On the Web Part Gallery page, to add the custom Web Part to the gallery,  click **New**.</span></span> <span data-ttu-id="2c205-156">此时不可用的 Web 部件库页中自定义 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="2c205-156">At this point the custom Web Part is not available in the Web Part Gallery page.</span></span>  
  
6. <span data-ttu-id="2c205-157">在新的 Web 部件页上，找到**CustomWebPart** （自定义 Web 部件的名称） 在列表中，选择左侧上的复选框，然后单击**导入库**页面顶部。</span><span class="sxs-lookup"><span data-stu-id="2c205-157">On the New Web Parts page, locate **CustomWebPart** (name of the custom Web Part) in the list, select the check box on the left, and then click **Populate Gallery** on the top of the page.</span></span> <span data-ttu-id="2c205-158">这将添加**CustomWebPart** Web 部件库页面中的条目。</span><span class="sxs-lookup"><span data-stu-id="2c205-158">This will add the **CustomWebPart** entry in the Web Part Gallery page.</span></span>  
  
   <span data-ttu-id="2c205-159">现在，可以使用自定义 Web 部件 (**CustomWebPart**) 以在你的 SharePoint 门户中创建 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="2c205-159">Now you can use the custom Web Part (**CustomWebPart**) to create Web Parts in your SharePoint portal.</span></span> <span data-ttu-id="2c205-160">自定义 Web 部件 (**CustomWebPart**) 将显示在下面**杂项**添加 Web 部件页部分中的。</span><span class="sxs-lookup"><span data-stu-id="2c205-160">The custom Web Part (**CustomWebPart**) will appear under the **Miscellaneous** section in the Add Web Parts page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c205-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c205-161">See Also</span></span>  
[<span data-ttu-id="2c205-162">使用包含 SharePoint 的 Oracle E-business Suite 适配器</span><span class="sxs-lookup"><span data-stu-id="2c205-162">Use the Oracle E-Business Suite adapter with SharePoint</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)