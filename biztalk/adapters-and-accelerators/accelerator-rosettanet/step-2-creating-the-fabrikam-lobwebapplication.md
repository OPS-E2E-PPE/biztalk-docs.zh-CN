---
title: "步骤 2： 创建 Fabrikam LOBWebApplication |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOBWebApplication
- LOBWebApplication
ms.assetid: 2ff8bd20-7fbc-4e16-b177-bb4afac7f7c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed64aac8ea0cf4073f3085f4491f607373d721b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-creating-the-fabrikam-lobwebapplication"></a><span data-ttu-id="d7fc5-102">步骤 2： 创建 Fabrikam LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="d7fc5-102">Step 2: Creating the Fabrikam LOBWebApplication</span></span>
<span data-ttu-id="d7fc5-103">在此步骤中，你将创建 Fabrikam 用于向 Contoso 提交 3A2 PIP 请求的 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-103">In this step, you create the LOB application that Fabrikam uses to submit a 3A2 PIP request to Contoso.</span></span> <span data-ttu-id="d7fc5-104">LOBWebApplication 项目安装在 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK 中。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-104">The LOBWebApplication project is installed in the [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="d7fc5-105">若要运行 Web 应用程序，必须创建 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Internet 信息服务 (IIS) 虚拟目录，然后构建 LOBWebApplication 项目。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-105">To run the Web application, you have to create a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Internet Information Services (IIS) virtual directory and build the LOBWebApplication project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7fc5-106">如果已完成双操作教程，你无需执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-106">If you completed the DoubleAction tutorial, you do not need to perform this step.</span></span>  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a><span data-ttu-id="d7fc5-107">创建 LOBWebApplication 虚拟目录</span><span class="sxs-lookup"><span data-stu-id="d7fc5-107">To create the LOBWebApplication virtual directory</span></span>  
  
1.  <span data-ttu-id="d7fc5-108">单击**启动**，指向**管理工具**，然后单击**Internet Information Services Manager**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-108">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services Manager**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7fc5-109">如果已完成双操作教程，则应已在该教程中创建了 LOBWebApplication 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-109">If you have already done the Double Action tutorial, you will already have created the LOBWebApplication virtual directory for that tutorial.</span></span> <span data-ttu-id="d7fc5-110">如果是这样，你无需执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-110">If so, you do not have to perform these steps.</span></span> <span data-ttu-id="d7fc5-111">但是，将需要更改从的虚拟目录的权限**运行脚本**到**读取**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-111">You will, however, have to change the permissions for the virtual directory from **Run scripts** to **Read**.</span></span>  
  
2.  <span data-ttu-id="d7fc5-112">在 Internet 信息服务管理器中，展开**< 计算机名 > （本地计算机）**，然后展开**网站**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-112">In Internet Information Services Manager, expand **<computer_name> (local computer)**, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="d7fc5-113">右键单击**Default Web Site**，指向**新建**，然后单击**虚拟目录**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-113">Right-click **Default Web Site**, point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="d7fc5-114">上**Welcometo 虚拟目录创建向导页**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-114">On the **Welcometo the Virtual Directory Creation Wizard page**, click **Next**.</span></span>  
  
5.  <span data-ttu-id="d7fc5-115">上**虚拟目录别名**页上，在**别名**框中，键入**LOBWebApplication**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-115">On the **Virtual Directory Alias** page, in the **Alias** box, type **LOBWebApplication**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="d7fc5-116">上**网站内容目录**页上，单击**浏览**，选择**\<驱动器 >: files\microsoft BizTalk\<版本 > 快捷键RosettaNet\SDK\LOBWebApplication**文件夹，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-116">On the **Web Site Content Directory** page, click **Browse**, select the **\<drive>:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\LOBWebApplication** folder, and then click **OK**.</span></span> <span data-ttu-id="d7fc5-117">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-117">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="d7fc5-118">上**虚拟目录访问权限**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-118">On the **Virtual Directory Access Permissions** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="d7fc5-119">单击**完成**可以创建虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-119">Click **Finish** to create the virtual directory.</span></span>  
  
### <a name="excluding-lobwebapplication-from-sharepoint"></a><span data-ttu-id="d7fc5-120">从 SharePoint 中排除 LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="d7fc5-120">Excluding LOBWebApplication from SharePoint</span></span>  
  
1.  <span data-ttu-id="d7fc5-121">单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-121">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d7fc5-122">如果已完成双操作教程，则应已在该教程中将 LOBWebApplication 虚拟目录从 SharePoint 中排除。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-122">If you have already done the Double Action tutorial, you will already have excluded the LOBWebApplication virtual directory from SharePoint for that tutorial.</span></span> <span data-ttu-id="d7fc5-123">如果是这样，你无需执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-123">If so, you do not have to perform these steps.</span></span>  
  
2.  <span data-ttu-id="d7fc5-124">上**管理中心**页上，在**虚拟服务器配置**部分中，选择**扩展或升级虚拟服务器**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-124">On the **Central Administration** page, in the **Virtual Server Configuration** section, select **Extend or upgrade virtual server**.</span></span>  
  
3.  <span data-ttu-id="d7fc5-125">如果看不到计算机上配置的 URL，请单击**完整列表**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-125">If you do not see the URL configured on the computer, click **Complete list**.</span></span>  
  
4.  <span data-ttu-id="d7fc5-126">选择**Default Web Site**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-126">Select **Default Web Site**.</span></span>  
  
5.  <span data-ttu-id="d7fc5-127">在**虚拟服务器管理**部分中，单击**定义管理路径**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-127">In the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
6.  <span data-ttu-id="d7fc5-128">在**添加新路径**部分中，在**路径**框中，键入"/ LOBWebApplication"。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-128">In the **Add New Path** section, in the **Path** box, type "/LOBWebApplication".</span></span> <span data-ttu-id="d7fc5-129">有关**类型**，选择**排除路径**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-129">For **Type**, select **Excluded Path**, and then click **OK**.</span></span>  
  
### <a name="to-build-the-lobwebapplication-project"></a><span data-ttu-id="d7fc5-130">生成 LOBWebApplication 项目</span><span class="sxs-lookup"><span data-stu-id="d7fc5-130">To build the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="d7fc5-131">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-131">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="d7fc5-132">从**文件**菜单上，指向**打开**，然后单击**Project\Solution**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-132">From the **File** menu, point to **Open**, and then click **Project\Solution**.</span></span>  
  
3.  <span data-ttu-id="d7fc5-133">在打开项目对话框中，在**查找中**，将移到**\<驱动器 >: files\microsoft BizTalk\<版本 > Accelerator for RosettaNet\ SDK\LOBWebApplication**选择**LOBWebApplication.sln**解决方案，然后再单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-133">In the Open Project dialog box, in **Look In**, move to **\<drive>:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\ SDK\LOBWebApplication**, select the **LOBWebApplication.sln** solution, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="d7fc5-134">在解决方案资源管理器，右键单击顶级节点 (http://localhost/LOBWebApplication)，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-134">In Solution Explorer, right-click the top node (http://localhost/LOBWebApplication), and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="d7fc5-135">在添加引用对话框中，单击**浏览**并转向**\<驱动器 >: files\microsoft BizTalk\<版本 > Accelerator for RosettaNet\bin**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-135">In the Add Reference dialog box, click **Browse** and move to **\<drive>:\Program Files\Microsoft  BizTalk \<version> Accelerator for RosettaNet\bin**.</span></span>  
  
6.  <span data-ttu-id="d7fc5-136">**选择 Microsoft.Solutions.BTARN.ConfigurationManager.dll 和 Microsoft.Solutions.BTARN.Shared.dll**程序集**，然后单击确定。**</span><span class="sxs-lookup"><span data-stu-id="d7fc5-136">**Select the Microsoft.Solutions.BTARN.ConfigurationManager.dll and Microsoft.Solutions.BTARN.Shared.dll** assemblies **and then click OK.**</span></span>  
  
7.  <span data-ttu-id="d7fc5-137">上**生成**菜单上，单击**生成网站**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-137">On the **Build** menu, click **Build Web Site**.</span></span>  
  
### <a name="to-run-the-lobwebapplication-project"></a><span data-ttu-id="d7fc5-138">运行 LOBWebApplication 项目</span><span class="sxs-lookup"><span data-stu-id="d7fc5-138">To run the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="d7fc5-139">在解决方案资源管理器，右键单击**default.aspx**，然后选择**设为起始页**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-139">In Solution Explorer, right-click **default.aspx**, and then select **Set As Start Page**.</span></span>  
  
2.  <span data-ttu-id="d7fc5-140">上**调试**菜单上，单击**启动但不调试**。</span><span class="sxs-lookup"><span data-stu-id="d7fc5-140">On the **Debug** menu, click **Start Without Debugging**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7fc5-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7fc5-141">See Also</span></span>  
 [<span data-ttu-id="d7fc5-142">测试解决方案</span><span class="sxs-lookup"><span data-stu-id="d7fc5-142">Testing the Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)