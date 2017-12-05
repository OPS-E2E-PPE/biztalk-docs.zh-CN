---
title: "步骤 7： 构建和部署 LOBWebApplication SDK 示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- double action tutorial, deploying solutions
ms.assetid: f61de666-ebda-4831-9669-598e9284e4c1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92b101b47e2f83a0390a47cf6b1e4fc9a210950d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-7-building-and-deploying-the-lobwebapplication-sdk-sample"></a><span data-ttu-id="5eb39-102">步骤 7： 构建和部署 LOBWebApplication SDK 示例</span><span class="sxs-lookup"><span data-stu-id="5eb39-102">Step 7: Building and Deploying the LOBWebApplication SDK Sample</span></span>
<span data-ttu-id="5eb39-103">在此步骤中，将创建业务线 (LOB) 应用程序，而 Fabrikam 将使用此应用程序向 Contoso 提交合作伙伴接口流程 (PIP) 请求。</span><span class="sxs-lookup"><span data-stu-id="5eb39-103">In this step, you create the line-of-business (LOB) application that Fabrikam uses to submit Partner Interface Process (PIP) requests to Contoso.</span></span> <span data-ttu-id="5eb39-104">你可以在 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 文件夹中找到 LOBWebApplication 项目。</span><span class="sxs-lookup"><span data-stu-id="5eb39-104">You can find the LOBWebApplication project in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK folder.</span></span> <span data-ttu-id="5eb39-105">若要运行 Web 应用程序，你必须创建[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Internet 信息服务 (IIS) 虚拟目录，然后生成 LOBWebApplication 项目。</span><span class="sxs-lookup"><span data-stu-id="5eb39-105">To run the Web application, you have to create a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Internet Information Services (IIS) virtual directory, and then build the LOBWebApplication project.</span></span>  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a><span data-ttu-id="5eb39-106">创建 LOBWebApplication 虚拟目录</span><span class="sxs-lookup"><span data-stu-id="5eb39-106">To create the LOBWebApplication virtual directory</span></span>  
  
1.  <span data-ttu-id="5eb39-107">单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="5eb39-107">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="5eb39-108">在 Internet 信息服务管理器窗口中，展开**< 计算机名 > （本地计算机）**，然后展开**网站**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-108">In the Internet Information Services Manager window, expand **<computer_name> (local computer)**, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="5eb39-109">右键单击**Default Web Site**，指向**新建**，然后单击**虚拟目录**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-109">Right-click **Default Web Site**, point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="5eb39-110">上**Welcometo 虚拟目录创建向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-110">On the **Welcometo the Virtual Directory Creation Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="5eb39-111">上**虚拟目录别名**页上，在**别名**框中，键入**LOBWebApplication**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-111">On the **Virtual Directory Alias** page, in the **Alias** box, type **LOBWebApplication**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="5eb39-112">上**网站内容目录**页上，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-112">On the **Web Site Content Directory** page, click **Browse**.</span></span> <span data-ttu-id="5eb39-113">在浏览文件夹对话框中，移动到 ***\<驱动器\>*: files\microsoft BizTalk\<版本\>RosettaNet\SDK\ 快捷键LOBWebApplication**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-113">In the Browse For Folder dialog box, move to ***\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication**, and then click **OK**.</span></span> <span data-ttu-id="5eb39-114">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-114">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="5eb39-115">上**虚拟目录访问权限**页上，取消选择**读取**，选择**运行脚本 （如 ASP)**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-115">On the **Virtual Directory Access Permissions** page, deselect **Read**, select **Run scripts (such as ASP)**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="5eb39-116">上**已成功完成虚拟目录创建向导**页上，单击**完成**可以创建虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="5eb39-116">On the **You have successfully completed the Virtual Directory Creation Wizard** page, click **Finish** to create the virtual directory.</span></span>  
  
### <a name="to-exclude-the-lobwebapplication-web-site-from-the-sharepoint-configuration"></a><span data-ttu-id="5eb39-117">从 SharePoint 配置中排除 LOBWebApplication 网站</span><span class="sxs-lookup"><span data-stu-id="5eb39-117">To exclude the LOBWebApplication Web site from the SharePoint configuration</span></span>  
  
1.  <span data-ttu-id="5eb39-118">单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-118">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
2.  <span data-ttu-id="5eb39-119">上**管理中心**Web 页上，在**虚拟服务器配置**部分中，选择**扩展或升级虚拟服务器**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-119">On the **Central Administration** Web page, in the **Virtual Server Configuration** section, select **Extend or upgrade virtual server**.</span></span>  
  
3.  <span data-ttu-id="5eb39-120">如果看不到计算机上配置的 URL，请单击**完整列表**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-120">If you do not see the URL configured on the computer, click **Complete list**.</span></span>  
  
4.  <span data-ttu-id="5eb39-121">上**虚拟服务器列表**页上，选择**Default Web Site**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-121">On the **Virtual Server List** page, select **Default Web Site**.</span></span>  
  
5.  <span data-ttu-id="5eb39-122">在**虚拟服务器管理**部分中，单击**定义管理路径**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-122">In the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
6.  <span data-ttu-id="5eb39-123">在**添加新路径**部分中，在**路径**框中，键入**/LOBWebApplication**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-123">In the **Add New Path** section, in the **Path** box, type **/LOBWebApplication**.</span></span>  
  
7.  <span data-ttu-id="5eb39-124">有关**类型**，选择**排除路径**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-124">For **Type**, select **Excluded Path**, and then click **OK**.</span></span>  
  
### <a name="to-build-the-lobwebapplication-project"></a><span data-ttu-id="5eb39-125">生成 LOBWebApplication 项目</span><span class="sxs-lookup"><span data-stu-id="5eb39-125">To build the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="5eb39-126">单击**启动**，指向**所有程序**，指向**Microsoft Visual Studio 2008**，然后单击**Microsoft Visual Studio 2008**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-126">Click **Start**, point to **All Programs**, point to **Microsoft Visual Studio 2008**, and then click **Microsoft Visual Studio 2008**.</span></span>  
  
2.  <span data-ttu-id="5eb39-127">在“文件”菜单中，指向“打开”，然后单击“项目”/“解决方案”。</span><span class="sxs-lookup"><span data-stu-id="5eb39-127">On the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="5eb39-128">在打开项目对话框中，移动到 ***\<驱动器\>*: files\microsoft BizTalk\<版本\>RosettaNet\SDK\LOBWebApplication 快捷键**，选择**LOBWebApplication.sln**解决方案文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-128">In the Open Project dialog box, move to ***\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication**, select the **LOBWebApplication.sln** solution file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="5eb39-129">在解决方案资源管理器，右键单击**http://localhost/LOBWebApplication**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-129">In Solution Explorer, right-click **http://localhost/LOBWebApplication**, and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="5eb39-130">在添加引用对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-130">In the Add Reference dialog box, click **Browse**.</span></span> <span data-ttu-id="5eb39-131">在添加引用对话框中，移动到 ***\<驱动器\>*: files\microsoft BizTalk\<版本\>Accelerator for RosettaNet\Bin**文件夹。</span><span class="sxs-lookup"><span data-stu-id="5eb39-131">In the Add Reference dialog box, move to ***\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin** folder.</span></span>  
  
6.  <span data-ttu-id="5eb39-132">从 Bin 文件夹中，选择**Microsoft.Solutions.BTARN.ConfigurationManager.dll**和**Microsoft.Solutions.BTARN.Shared.dll**程序集，，然后单击**打开。**</span><span class="sxs-lookup"><span data-stu-id="5eb39-132">From the Bin folder, select the **Microsoft.Solutions.BTARN.ConfigurationManager.dll** and **Microsoft.Solutions.BTARN.Shared.dll** assemblies, and then click **Open.**</span></span>  
  
7.  <span data-ttu-id="5eb39-133">单击**确定**关闭**添加引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="5eb39-133">Click **OK** to close the **Add Reference** dialog box.</span></span>  
  
8.  <span data-ttu-id="5eb39-134">在解决方案资源管理器，右键单击**解决方案 LOBWebApplication** ，然后单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-134">In Solution Explorer, right-click **Solution 'LOBWebApplication'** and then click **Build Solution**.</span></span>  
  
9. <span data-ttu-id="5eb39-135">右键单击**default.aspx**，然后单击**设为起始页**。</span><span class="sxs-lookup"><span data-stu-id="5eb39-135">Right-click **default.aspx**, and then click **Set as Start Page**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eb39-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5eb39-136">See Also</span></span>  
 [<span data-ttu-id="5eb39-137">测试双操作教程</span><span class="sxs-lookup"><span data-stu-id="5eb39-137">Testing the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)