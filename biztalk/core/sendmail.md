---
title: "SendMail |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SMTP adapters, examples
- examples, SMTP adapters
- SMTP adapters
ms.assetid: a0258619-b195-4c8a-8326-77add6e6f04d
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2fce9c39fad76ad0e621fb4773cc39efc3488cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sendmail"></a><span data-ttu-id="0a4cb-102">SendMail</span><span class="sxs-lookup"><span data-stu-id="0a4cb-102">SendMail</span></span>
<span data-ttu-id="0a4cb-103">SendMail 示例演示如何使用简单邮件传输协议 (SMTP) 适配器在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程内发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-103">The SendMail sample demonstrates how you can use the Simple Mail Transfer Protocol (SMTP) adapter to send e-mail messages from within a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span> <span data-ttu-id="0a4cb-104">用于发送电子邮件的动态信息是通过使用属性升级功能从 XML 消息中检索得到的。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-104">Dynamic information used to send the e-mail messages is retrieved from an XML message using property promotion functionality.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="0a4cb-105">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="0a4cb-105">What This Sample Does</span></span>  
 <span data-ttu-id="0a4cb-106">本示例使用升级自传入 XML 采购订单 (PO) 消息的属性中的信息来发送电子邮件，其具体的操作步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-106">This sample sends an e-mail message using information obtained from properties promoted out of an incoming XML purchase order (PO) message, using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="0a4cb-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程检索输入的 XML PO 消息。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-107">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration retrieves an input XML PO message.</span></span>  
  
2.  <span data-ttu-id="0a4cb-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Orchestration 提升**PONumber**和**电子邮件**为将来便于访问的属性。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-108">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration promotes the **PONumber** and **Email** properties for easier access in the future.</span></span>  
  
3.  <span data-ttu-id="0a4cb-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程使用升级属性的值设置动态发送端口的目标地址和电子邮件的主题。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration uses the values of the promoted properties to set the destination address of the dynamic send port and to set the subject of the e-mail message.</span></span>  
  
4.  <span data-ttu-id="0a4cb-110">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程通过 SMTP 适配器发送构造好的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-110">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration sends the constructed e-mail message through the SMTP adapter.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="0a4cb-111">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="0a4cb-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="0a4cb-112">\<*示例路径*> \AdaptersUsage\SendMail\\</span><span class="sxs-lookup"><span data-stu-id="0a4cb-112">\<*Samples Path*>\AdaptersUsage\SendMail\\</span></span>  
  
 <span data-ttu-id="0a4cb-113">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-113">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="0a4cb-114">文件</span><span class="sxs-lookup"><span data-stu-id="0a4cb-114">File(s)</span></span>|<span data-ttu-id="0a4cb-115">Description</span><span class="sxs-lookup"><span data-stu-id="0a4cb-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a4cb-116">AssemblyInfo.cs、SendMail.btproj、SendMail.sln</span><span class="sxs-lookup"><span data-stu-id="0a4cb-116">AssemblyInfo.cs, SendMail.btproj, SendMail.sln</span></span>|<span data-ttu-id="0a4cb-117">提供本示例的项目、解决方案和程序集信息文件。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-117">Provides project, solution, and assembly information files for this sample.</span></span>|  
|<span data-ttu-id="0a4cb-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="0a4cb-118">Cleanup.bat</span></span>|<span data-ttu-id="0a4cb-119">取消部署程序集并将其从全局程序集缓存 (GAC) 中删除；删除发送和接收端口；根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-119">Undeploys assemblies and removes them from the global assembly cache (GAC); removes send and receive ports; removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="0a4cb-120">PropertySchema.xsd、PurchaseOrder.xsd</span><span class="sxs-lookup"><span data-stu-id="0a4cb-120">PropertySchema.xsd, PurchaseOrder.xsd</span></span>|<span data-ttu-id="0a4cb-121">分别为要升级的属性和 XML PO 消息提供架构。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-121">Provides schemas for the properties that you want to promote, and for the XML PO message, respectively.</span></span>|  
|<span data-ttu-id="0a4cb-122">ReceiveSend.odx</span><span class="sxs-lookup"><span data-stu-id="0a4cb-122">ReceiveSend.odx</span></span>|<span data-ttu-id="0a4cb-123">提供用于处理传入 XML PO 消息并根据消息中的信息发送电子邮件的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-123">Provides a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that processes the incoming XML PO message and sends an e-mail message based on information in the message.</span></span>|  
|<span data-ttu-id="0a4cb-124">SendMailInput.xml</span><span class="sxs-lookup"><span data-stu-id="0a4cb-124">SendMailInput.xml</span></span>|<span data-ttu-id="0a4cb-125">包含具有使用 XML 指定的 PO 的示例输入文件。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-125">Contains a sample input file with a PO specified using XML.</span></span>|  
|<span data-ttu-id="0a4cb-126">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="0a4cb-126">Setup.bat</span></span>|<span data-ttu-id="0a4cb-127">生成并初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-127">Builds and initializes this sample.</span></span> <span data-ttu-id="0a4cb-128">**注意：**和此安装程序文件创建并将绑定的端口，在其他方面，使用另一种机制比大部分安装程序文件的 SDK 示例。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-128">**Note:**  This setup file creates and binds ports, and so on, using a different mechanism than most of the setup files for the SDK samples.</span></span> <span data-ttu-id="0a4cb-129">它不需要 companion .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-129">It does not require a companion .xml file.</span></span>|  
  
### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="0a4cb-130">构建和初始化此示例</span><span class="sxs-lookup"><span data-stu-id="0a4cb-130">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="0a4cb-131">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-131">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="0a4cb-132">\<*示例路径*> \AdaptersUsage\SendMail</span><span class="sxs-lookup"><span data-stu-id="0a4cb-132">\<*Samples Path*>\AdaptersUsage\SendMail</span></span>  
  
2.  <span data-ttu-id="0a4cb-133">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-133">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="0a4cb-134">为本示例创建以下输入文件夹：</span><span class="sxs-lookup"><span data-stu-id="0a4cb-134">Creates the following input folder for this sample:</span></span>  
  
         <span data-ttu-id="0a4cb-135">\<*示例路径*> \AdaptersUsage\SendMail\In</span><span class="sxs-lookup"><span data-stu-id="0a4cb-135">\<*Samples Path*>\AdaptersUsage\SendMail\In</span></span>  
  
    -   <span data-ttu-id="0a4cb-136">编译[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例项目。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-136">Compiles the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample.</span></span>  
  
    -   <span data-ttu-id="0a4cb-137">启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-137">Starts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0a4cb-138">在尝试运行本示例之前，应确认在生成和初始化过程中 BizTalk 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-138">You should confirm that BizTalk did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0a4cb-139">如果选择在不运行 Setup.bat 文件的情况下打开并生成本示例中的项目，则必须首先使用 .NET Framework 强名称实用工具 (sn.exe) 创建一个强名称密钥对。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-139">If you choose to open and build the project in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="0a4cb-140">使用此密钥对生成的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-140">Use this key pair to sign the resulting assembly.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0a4cb-141">若要撤消由 Setup.bat 进行的更改，请运行 Cleanup.bat 和删除所有接收和发送端口 SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail 带有前缀。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-141">To undo changes made by Setup.bat, run Cleanup.bat and delete all receive and send ports prefixed with SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail.</span></span> <span data-ttu-id="0a4cb-142">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-142">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
3.  <span data-ttu-id="0a4cb-143">在**BizTalk Server 管理**控制台，找到前缀 SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail 接收端口。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-143">In the **BizTalk Server Administration** console, locate the receive port prefixed by SendMail_1.0.0.0_Microsoft.Samples.BizTalk.SendMail.</span></span> <span data-ttu-id="0a4cb-144">更新此接收端口以指向您要用作输入的位置的文件系统上的目录的接收位置。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-144">Update the receive location for this receive port to point to a directory on your file system to use as the input location.</span></span>  
  
4.  <span data-ttu-id="0a4cb-145">使用 （如记事本） 程序修改文件 SendMailInput.xml 以便**电子邮件**元素指定想要接收此示例由生成的电子邮件消息的合法的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-145">Using a program such as Notepad, modify the file SendMailInput.xml so that the **Email** element specifies a legitimate e-mail address at which you want to receive the e-mail message generated by this sample.</span></span>  
  
5.  <span data-ttu-id="0a4cb-146">单击**启动**，指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-146">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
6.  <span data-ttu-id="0a4cb-147">在**BizTalk Server 管理**控制台中，展开 BizTalk 组树。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-147">In the **BizTalk Server Administration** console, expand the BizTalk Group tree.</span></span>  
  
7.  <span data-ttu-id="0a4cb-148">展开**平台设置**的左窗格中的树。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-148">Expand the **Platform Settings** tree in the left pane.</span></span>  
  
8.  <span data-ttu-id="0a4cb-149">展开**适配器**文件夹中，单击**SMTP**节点，然后再双击 SMTP 适配器行在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-149">Expand the **Adapters** folder, click the **SMTP** node, and then double-click the SMTP adapter row in the right pane.</span></span>  
  
9. <span data-ttu-id="0a4cb-150">在**SMTP-适配器处理程序属性**对话框中，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-150">In the **SMTP - Adapter Handler Properties** dialog box, click **Properties**.</span></span>  
  
10. <span data-ttu-id="0a4cb-151">在**SMTP 传输属性**对话框中，在**属性**选项卡上，提供相应的值为**SMTP 服务器名称**和**从 （电子邮件地址）**属性，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-151">In the **SMTP Transport Properties** dialog box, on the **Properties** tab, provide appropriate values for the **SMTP server name** and **From (e-mail address)** properties, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0a4cb-152">这些值将用于构造为通过此 SMTP 适配器发送任何电子邮件的 From 电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-152">These values will be used to construct the From e-mail address for any e-mail messages sent through this SMTP adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a4cb-153">如果你需要使用 SMTP 服务器进行身份验证，则必须确保发电子邮件地址属于同一个帐户可用于身份验证。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-153">If you need to authenticate with your SMTP server, you must ensure that the From e-mail address belongs to the same account that you use for authentication.</span></span>  
  
11. <span data-ttu-id="0a4cb-154">停止，然后重新启动 BizTalk 服务 (BizTalkServerApplication)，以便业务流程将采用这些更改。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-154">Stop and then restart the BizTalk service (BizTalkServerApplication) so that the orchestration will adopt these changes.</span></span>  
  
### <a name="to-run-this-sample"></a><span data-ttu-id="0a4cb-155">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="0a4cb-155">To run this sample</span></span>  
  
1.  <span data-ttu-id="0a4cb-156">将修改的 SendMailInput.xml 文件的副本放到输入文件夹下。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-156">Put a copy of the modified file SendMailInput.xml into the input folder.</span></span>  
  
2.  <span data-ttu-id="0a4cb-157">观察发送给你在前面的过程中指定的电子邮件地址的电子邮件消息的到达。</span><span class="sxs-lookup"><span data-stu-id="0a4cb-157">Observe the arrival of an e-mail message to the e-mail address you specified in the previous procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4cb-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a4cb-158">See Also</span></span>  
 [<span data-ttu-id="0a4cb-159">适配器示例-使用情况</span><span class="sxs-lookup"><span data-stu-id="0a4cb-159">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)