---
title: 步骤 7： 生成和部署 LOBWebApplication SDK 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- double action tutorial, deploying solutions
ms.assetid: f61de666-ebda-4831-9669-598e9284e4c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a0716c854c20f5ea7fa7d2ad91576cb142f6a02
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996182"
---
# <a name="step-7-building-and-deploying-the-lobwebapplication-sdk-sample"></a><span data-ttu-id="facd9-102">步骤 7： 生成和部署 LOBWebApplication SDK 示例</span><span class="sxs-lookup"><span data-stu-id="facd9-102">Step 7: Building and Deploying the LOBWebApplication SDK Sample</span></span>
<span data-ttu-id="facd9-103">在此步骤中，将创建业务线 (LOB) 应用程序，而 Fabrikam 将使用此应用程序向 Contoso 提交合作伙伴接口流程 (PIP) 请求。</span><span class="sxs-lookup"><span data-stu-id="facd9-103">In this step, you create the line-of-business (LOB) application that Fabrikam uses to submit Partner Interface Process (PIP) requests to Contoso.</span></span> <span data-ttu-id="facd9-104">您可以 Microsoft® 中找到 LOBWebApplication 项目[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK 文件夹。</span><span class="sxs-lookup"><span data-stu-id="facd9-104">You can find the LOBWebApplication project in the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK folder.</span></span> <span data-ttu-id="facd9-105">若要运行的 Web 应用程序，您需要创建一个 Microsoft Internet 信息服务 (IIS) 虚拟目录，然后生成 LOBWebApplication 项目。</span><span class="sxs-lookup"><span data-stu-id="facd9-105">To run the Web application, you have to create a Microsoft Internet Information Services (IIS) virtual directory, and then build the LOBWebApplication project.</span></span>  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a><span data-ttu-id="facd9-106">创建 LOBWebApplication 虚拟目录</span><span class="sxs-lookup"><span data-stu-id="facd9-106">To create the LOBWebApplication virtual directory</span></span>  
  
1.  <span data-ttu-id="facd9-107">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="facd9-107">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="facd9-108">在 Internet 信息服务管理器窗口中，展开 **< 计算机名 > （本地计算机）**，然后展开**网站**。</span><span class="sxs-lookup"><span data-stu-id="facd9-108">In the Internet Information Services Manager window, expand **<computer_name> (local computer)**, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="facd9-109">右键单击**Default Web Site**，依次指向**新建**，然后单击**虚拟目录**。</span><span class="sxs-lookup"><span data-stu-id="facd9-109">Right-click **Default Web Site**, point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="facd9-110">上**Welcometo 虚拟目录创建向导**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="facd9-110">On the **Welcometo the Virtual Directory Creation Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="facd9-111">上**虚拟目录别名**页上，在**别名**框中，键入**LOBWebApplication**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="facd9-111">On the **Virtual Directory Alias** page, in the **Alias** box, type **LOBWebApplication**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="facd9-112">上**网站内容目录**页上，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="facd9-112">On the **Web Site Content Directory** page, click **Browse**.</span></span> <span data-ttu-id="facd9-113">在浏览文件夹对话框中，转到 ***\<驱动器\>*:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBWebApplication**，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="facd9-113">In the Browse For Folder dialog box, move to ***\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication**, and then click **OK**.</span></span> <span data-ttu-id="facd9-114">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="facd9-114">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="facd9-115">上**虚拟目录访问权限**页上，取消选中**读取**，选择**运行脚本 （如 ASP)**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="facd9-115">On the **Virtual Directory Access Permissions** page, deselect **Read**, select **Run scripts (such as ASP)**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="facd9-116">上**您已成功完成虚拟目录创建向导**页上，单击**完成**创建虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="facd9-116">On the **You have successfully completed the Virtual Directory Creation Wizard** page, click **Finish** to create the virtual directory.</span></span>  
  
### <a name="to-exclude-the-lobwebapplication-web-site-from-the-sharepoint-configuration"></a><span data-ttu-id="facd9-117">从 SharePoint 配置中排除 LOBWebApplication 网站</span><span class="sxs-lookup"><span data-stu-id="facd9-117">To exclude the LOBWebApplication Web site from the SharePoint configuration</span></span>  
  
1.  <span data-ttu-id="facd9-118">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="facd9-118">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
2.  <span data-ttu-id="facd9-119">上**Central Administration**中的 Web 页上，**虚拟服务器配置**部分中，选择**扩展或升级虚拟服务器**。</span><span class="sxs-lookup"><span data-stu-id="facd9-119">On the **Central Administration** Web page, in the **Virtual Server Configuration** section, select **Extend or upgrade virtual server**.</span></span>  
  
3.  <span data-ttu-id="facd9-120">如果看不到的计算机上配置的 URL，请单击**完整列表**。</span><span class="sxs-lookup"><span data-stu-id="facd9-120">If you do not see the URL configured on the computer, click **Complete list**.</span></span>  
  
4.  <span data-ttu-id="facd9-121">上**虚拟服务器列表**页上，选择**Default Web Site**。</span><span class="sxs-lookup"><span data-stu-id="facd9-121">On the **Virtual Server List** page, select **Default Web Site**.</span></span>  
  
5.  <span data-ttu-id="facd9-122">在中**虚拟服务器管理**部分中，单击**定义管理路径**。</span><span class="sxs-lookup"><span data-stu-id="facd9-122">In the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
6.  <span data-ttu-id="facd9-123">在中**添加新路径**部分中，在**路径**框中，键入 **/LOBWebApplication**。</span><span class="sxs-lookup"><span data-stu-id="facd9-123">In the **Add New Path** section, in the **Path** box, type **/LOBWebApplication**.</span></span>  
  
7.  <span data-ttu-id="facd9-124">有关**类型**，选择**排除的路径**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="facd9-124">For **Type**, select **Excluded Path**, and then click **OK**.</span></span>  
  
### <a name="to-build-the-lobwebapplication-project"></a><span data-ttu-id="facd9-125">生成 LOBWebApplication 项目</span><span class="sxs-lookup"><span data-stu-id="facd9-125">To build the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="facd9-126">单击**启动**，依次指向**所有程序**，指向**Microsoft Visual Studio 2008**，然后单击**Microsoft Visual Studio 2008**。</span><span class="sxs-lookup"><span data-stu-id="facd9-126">Click **Start**, point to **All Programs**, point to **Microsoft Visual Studio 2008**, and then click **Microsoft Visual Studio 2008**.</span></span>  
  
2.  <span data-ttu-id="facd9-127">在“文件”菜单中，指向“打开”，然后单击“项目”/“解决方案”。</span><span class="sxs-lookup"><span data-stu-id="facd9-127">On the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="facd9-128">在打开项目对话框中，转到 ***\<驱动器\>*:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBWebApplication**，选择**LOBWebApplication.sln**解决方案文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="facd9-128">In the Open Project dialog box, move to ***\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication**, select the **LOBWebApplication.sln** solution file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="facd9-129">在解决方案资源管理器中右键单击**http://localhost/LOBWebApplication**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="facd9-129">In Solution Explorer, right-click **http://localhost/LOBWebApplication**, and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="facd9-130">在添加引用对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="facd9-130">In the Add Reference dialog box, click **Browse**.</span></span> <span data-ttu-id="facd9-131">在添加引用对话框中，转到 ***\<驱动器\>*:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\Bin**文件夹。</span><span class="sxs-lookup"><span data-stu-id="facd9-131">In the Add Reference dialog box, move to ***\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin** folder.</span></span>  
  
6.  <span data-ttu-id="facd9-132">从 Bin 文件夹中，选择**Microsoft.Solutions.BTARN.ConfigurationManager.dll**并**Microsoft.Solutions.BTARN.Shared.dll**程序集，并单击**打开。**</span><span class="sxs-lookup"><span data-stu-id="facd9-132">From the Bin folder, select the **Microsoft.Solutions.BTARN.ConfigurationManager.dll** and **Microsoft.Solutions.BTARN.Shared.dll** assemblies, and then click **Open.**</span></span>  
  
7.  <span data-ttu-id="facd9-133">单击**确定**以关闭**添加引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="facd9-133">Click **OK** to close the **Add Reference** dialog box.</span></span>  
  
8.  <span data-ttu-id="facd9-134">在解决方案资源管理器中右键单击**解决方案 'LOBWebApplication'** ，然后单击**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="facd9-134">In Solution Explorer, right-click **Solution 'LOBWebApplication'** and then click **Build Solution**.</span></span>  
  
9. <span data-ttu-id="facd9-135">右键单击**default.aspx**，然后单击**设为起始页**。</span><span class="sxs-lookup"><span data-stu-id="facd9-135">Right-click **default.aspx**, and then click **Set as Start Page**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="facd9-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="facd9-136">See Also</span></span>  
 [<span data-ttu-id="facd9-137">测试双操作教程</span><span class="sxs-lookup"><span data-stu-id="facd9-137">Testing the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)