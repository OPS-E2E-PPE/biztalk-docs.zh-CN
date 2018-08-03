---
title: LOBWebApplication |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services, LOBWebApplication
- ASPX pages, LOBWebApplication utility
- virtual servers
- ASPX pages, submitting actions
- LOBWebApplication
- ASPX pages, response messages
- LOBWebApplication utility
ms.assetid: 2d578efd-72a9-4621-9274-30792bf94b6c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9120d9078303092740fdbfc27b6932b7849cc6a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002102"
---
# <a name="lobwebapplication"></a><span data-ttu-id="8f8ef-102">LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="8f8ef-102">LOBWebApplication</span></span>
<span data-ttu-id="8f8ef-103">使用 LOBWebApplication 实用工具可以将 ASPX 页中的操作或响应消息提交给贸易合作伙伴，从而模拟实际的业务线 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-103">You use the LOBWebApplication utility to submit an action or response message from an ASPX page to a trading partner, simulating an actual line-of-business Web application.</span></span>  
  
 <span data-ttu-id="8f8ef-104">设置 ASPX 页后，您启动该页，输入消息的参数：本组织和合作伙伴组织；PIP 代码、版本和实例 ID；以及消息类别。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-104">After you have set up the ASPX page, you start the page, and enter the parameters for a message: the home and partner organizations; the PIP code, version, and instance ID; and the message category.</span></span> <span data-ttu-id="8f8ef-105">然后你可以修改服务内容并提交消息。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-105">You can then modify the service content, and submit the message.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="8f8ef-106">在 SDK 中的位置</span><span class="sxs-lookup"><span data-stu-id="8f8ef-106">Location in SDK</span></span>  
 <span data-ttu-id="8f8ef-107">\<*驱动器*\>\Program Files (86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="8f8ef-107">\<*drive*\>\Program Files (86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication</span></span>  
  
## <a name="adding-a-virtual-server-for-lobwebapplication"></a><span data-ttu-id="8f8ef-108">为 LOBWebApplication 添加虚拟服务器</span><span class="sxs-lookup"><span data-stu-id="8f8ef-108">Adding a Virtual Server for LOBWebApplication</span></span>  
  
#### <a name="to-add-a-virtual-server"></a><span data-ttu-id="8f8ef-109">添加虚拟服务器</span><span class="sxs-lookup"><span data-stu-id="8f8ef-109">To add a virtual server</span></span>  
  
1.  <span data-ttu-id="8f8ef-110">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="8f8ef-110">Click **Start**, point to **AllPrograms**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="8f8ef-111">在信息服务管理器中，展开**\<计算机名\>（本地计算机）**，展开**网站**，然后右键单击**Default Web Site**.</span><span class="sxs-lookup"><span data-stu-id="8f8ef-111">In Information Services Manager, expand **\<Computer name\> (local computer)**, expand **Web Sites**, and then right-click **Default Web Site**.</span></span>  
  
3.  <span data-ttu-id="8f8ef-112">指向**新建**，然后单击**虚拟目录**。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-112">Point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="8f8ef-113">上**虚拟目录创建向导**页上，单击**下一步**，然后键入别名的站点，如**LOBWebApplication**。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-113">On the **Virtual Directory Creation Wizard** page, click **Next**, and then type an alias for the site, such as **LOBWebApplication**.</span></span>  
  
5.  <span data-ttu-id="8f8ef-114">上**网站内容目录**页上，单击**浏览**，将移到\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk \<版本\>Accelerator for RosettaNet\SDK\LOBWebApplication，单击**确定**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-114">On the **Web Site Content Directory** page, click **Browse**, move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication, click **OK**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="8f8ef-115">上**虚拟目录访问权限**页上，选择**读取**并**运行脚本**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-115">On the **Virtual Directory Access Permissions** page, select **Read** and **Run scripts**, and then click **Next**.</span></span> <span data-ttu-id="8f8ef-116">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-116">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="8f8ef-117">将用于配置 BTARN 的服务帐户用户（如 hostsvc）添加到 STS_WPG。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-117">Add the service account user that was used to configure BTARN, for example, hostsvc, to the STS_WPG.</span></span>  
  
8.  <span data-ttu-id="8f8ef-118">删除 C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary ASP.NET Files 中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-118">Delete all files from C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary ASP.NET Files.</span></span> <span data-ttu-id="8f8ef-119">在删除这些文件之前，你可能需要运行 iisreset 程序来取消这些文件的锁定。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-119">You may have to run the iisreset program to unlock the files before you can delete them.</span></span>  
  
9. <span data-ttu-id="8f8ef-120">在 IIS 管理器中，将 LOBWebApplication 设置为在应用程序池 BTARNHTTPReceivePool 下运行。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-120">In IIS Manager, set the LOBWebApplication to run under the Application Pool BTARNHTTPReceivePool.</span></span>  
  
10. <span data-ttu-id="8f8ef-121">在 IIS 管理器中 LOBWebApplication 实用工具的“目录安全性属性”部分中，禁用以匿名运行虚拟目录的选项。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-121">In IIS Manager, in the Directory Security Properties section for the LOBWebApplication utility, disable the option for the virtual directory to run as anonymous.</span></span>  
  
## <a name="building-lobwebapplication"></a><span data-ttu-id="8f8ef-122">生成 LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="8f8ef-122">Building LOBWebApplication</span></span>  
  
#### <a name="to-build-lobwebapplication"></a><span data-ttu-id="8f8ef-123">生成 LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="8f8ef-123">To build LOBWebApplication</span></span>  
  
1. <span data-ttu-id="8f8ef-124">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-124">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="8f8ef-125">上**文件**，依次指向**打开**，然后单击**打开的解决方案**。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-125">On the **File**, point to **Open**, and then click **Open Solution**.</span></span>  
  
3. <span data-ttu-id="8f8ef-126">将移动到\<*驱动器*\>\Program 文件 (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\LOBWebApplication，选择**LOBWebApplication.sln**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-126">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication, select **LOBWebApplication.sln**, and then click **Open**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8f8ef-127">如果未为 LOBWebApplication 添加虚拟服务器，将不会打开该解决方案中正确地[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-127">If you have not added a virtual server for LOBWebApplication, the solution will not open correctly in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
4. <span data-ttu-id="8f8ef-128">右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-128">Right-click **References**, and then click **Add Reference**.</span></span>  
  
5. <span data-ttu-id="8f8ef-129">在中**添加引用**对话框中，单击**浏览**，将移到\<*驱动器*\>: \Program 文件 (x86) \Microsoft BizTalk \<版本\>Accelerator for RosettaNet\Bin，选择 Microsoft.Solutions.BTARN.ConfigurationManager.dll 和 Microsoft.Solutions.BTARN.Shared.dll 文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-129">In the **Add Reference** dialog box, click **Browse**, move to \<*drive*\>:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin, select the Microsoft.Solutions.BTARN.ConfigurationManager.dll and Microsoft.Solutions.BTARN.Shared.dll files, and then click **Open**.</span></span>  
  
6. <span data-ttu-id="8f8ef-130">右键单击**LOBWebApplication**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-130">Right-click **LOBWebApplication**, and then click **Build**.</span></span>  
  
## <a name="running-lobwebapplication"></a><span data-ttu-id="8f8ef-131">运行 LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="8f8ef-131">Running LOBWebApplication</span></span>  
  
#### <a name="to-run-lobwebapplication-and-submit-a-message"></a><span data-ttu-id="8f8ef-132">运行 LOBWebApplication 并提交消息</span><span class="sxs-lookup"><span data-stu-id="8f8ef-132">To run LOBWebApplication and submit a message</span></span>  
  
1.  <span data-ttu-id="8f8ef-133">单击**启动**，依次指向**所有程序**，然后单击**Internet Explorer**。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-133">Click **Start**, point to **All Programs**, and then click **Internet Explorer**.</span></span>  
  
2.  <span data-ttu-id="8f8ef-134">在 Internet Explorer 中，在**地址**框中，键入http://localhost/LOBWebApplication，然后单击**转**。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-134">In Internet Explorer, in the **Address** box, type http://localhost/LOBWebApplication, and then click **Go**.</span></span>  
  
3.  <span data-ttu-id="8f8ef-135">在中**提交消息**对话框框中，键入本组织、 合作伙伴组织、 PIP 代码、 PIP 版本、 PIP 实例 ID 和消息类别。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-135">In the **Submit Message** dialog box, type the home organization, the partner organization, the PIP code, the PIP version, the PIP Instance ID, and the message category.</span></span>  
  
4.  <span data-ttu-id="8f8ef-136">根据需要修改服务内容。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-136">Modify the service content as needed.</span></span>  
  
5.  <span data-ttu-id="8f8ef-137">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-137">Click **Submit**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f8ef-138">Remarks</span><span class="sxs-lookup"><span data-stu-id="8f8ef-138">Remarks</span></span>  
 <span data-ttu-id="8f8ef-139">LOBWebApplication 实用工具从指定的 PIP 生成消息的实例，并将所生成的消息实例的服务内容输入到 ASPX 页。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-139">The LOBWebApplication utility generates an instance of the message from the specified PIP, and enters service content from the generated message instance into the ASPX page.</span></span> <span data-ttu-id="8f8ef-140">为此，该实用工具采用直接从 PIP 生成格式正确的消息实例时所用的技术。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-140">To do this, the utility uses the same technique that it uses to generate a well-formed message instance directly from a PIP.</span></span> <span data-ttu-id="8f8ef-141">有关详细信息，请参阅[根据 PIP 创建格式正确的消息实例](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md)。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-141">For more information, see [Creating a Well-Formed Message Instance from a PIP](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md).</span></span> <span data-ttu-id="8f8ef-142">你可以使用实际数据填充 ASPX 页中服务内容的任何字段，以生成实际消息实例。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-142">You can populate any field of the service content in the ASPX page with actual data to generate an actual message instance.</span></span>  
  
 <span data-ttu-id="8f8ef-143">使用 LOBWebApplication 实用工具还可以模拟业务线 Web 应用程序提交消息的过程。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-143">You use the LOBWebApplication utility to simulate a line-of-business Web application submitting a message.</span></span> <span data-ttu-id="8f8ef-144">使用 LOBApplication 实用工具还可以模拟业务线桌面应用程序提交消息的过程。</span><span class="sxs-lookup"><span data-stu-id="8f8ef-144">You use the LOBApplication utility to simulate a line-of-business desktop application submitting a message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f8ef-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f8ef-145">See Also</span></span>  
 <span data-ttu-id="8f8ef-146">[实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="8f8ef-146">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="8f8ef-147">LOBApplication</span><span class="sxs-lookup"><span data-stu-id="8f8ef-147">LOBApplication</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)
