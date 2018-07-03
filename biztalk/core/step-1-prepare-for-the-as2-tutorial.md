---
title: 步骤 1： AS2 教程的准备工作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3421c33b-0ccd-4e9d-b1c3-b161278e4d98
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f394df645774752993064676345a371eb3135a0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003670"
---
# <a name="step-1-prepare-for-the-as2-tutorial"></a><span data-ttu-id="36044-102">AS2 教程的步骤 1： 准备工作</span><span class="sxs-lookup"><span data-stu-id="36044-102">Step 1: Prepare for the AS2 Tutorial</span></span>
<span data-ttu-id="36044-103">![步骤 1 部分，共 11](../core/media/tut-step1-of-11.gif "Tut_Step1_of_11")</span><span class="sxs-lookup"><span data-stu-id="36044-103">![Step 1 of 11](../core/media/tut-step1-of-11.gif "Tut_Step1_of_11")</span></span>  
  
 <span data-ttu-id="36044-104">AS2 教程在一台计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="36044-104">The AS2 tutorial is run on a single computer.</span></span> <span data-ttu-id="36044-105">若要准备本教程，必须安装和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中所述[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)部分。</span><span class="sxs-lookup"><span data-stu-id="36044-105">To prepare for the tutorial, you must install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as described in [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) section.</span></span> <span data-ttu-id="36044-106">你还必须添加对本主题中所述的 BizTalk Server EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="36044-106">You must also add a reference to the BizTalk Server EDI Application as described in this topic.</span></span> <span data-ttu-id="36044-107">AS2 教程所需的文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="36044-107">The files required for the AS2 tutorial are located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36044-108">为使此教程能够运行，你需要对进程内主机实例和独立主机实例使用相同的登录帐户。</span><span class="sxs-lookup"><span data-stu-id="36044-108">For this tutorial to work, you need to use the same logon account for both the in-process host instance and the isolated host instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36044-109">为了让此教程运行，用于此教程的 BizTalk Server 主机必须标记为 32 位。</span><span class="sxs-lookup"><span data-stu-id="36044-109">For this tutorial to work, the BizTalk Server host that is used for this tutorial must be marked as 32-bit.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36044-110">为了让此教程运行，必须将其在使用 IIS 7.0 或 IIS 7.5 的平台上运行，并且必须将“为应用程序池启用 32 位应用程序设置”设置为 True。</span><span class="sxs-lookup"><span data-stu-id="36044-110">For this tutorial to work, it must be run on a platform using IIS 7.0 or IIS 7.5, and the Enable 32-Bit Application Setting for the Application Pools must be set to True.</span></span>  
  
 <span data-ttu-id="36044-111">AS2 教程文件夹包括 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将向其中写入测试输出文件的三个文件夹（EDI 负载、997 和 MDN）。</span><span class="sxs-lookup"><span data-stu-id="36044-111">The AS2 tutorial folders include three folders that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will write test output files to (the EDI payload, 997, and MDN).</span></span> <span data-ttu-id="36044-112">这些文件夹已创建完成，但你必须为 997 和 MDN 这两个文件夹设置安全权限（参见下面的过程）。</span><span class="sxs-lookup"><span data-stu-id="36044-112">These folder have already been created, but you must set the security permissions for two of the 997 and MDN folders (see the procedure below).</span></span>  
  
 <span data-ttu-id="36044-113">此教程所需的文件夹和文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="36044-113">The folders and files required for the tutorial are as follows:</span></span>  
  
|<span data-ttu-id="36044-114">文件夹\文件</span><span class="sxs-lookup"><span data-stu-id="36044-114">Folder\File</span></span>|<span data-ttu-id="36044-115">用途</span><span class="sxs-lookup"><span data-stu-id="36044-115">Purpose</span></span>|  
|------------------|-------------|  
|<span data-ttu-id="36044-116">\\_997ToFabrikam</span><span class="sxs-lookup"><span data-stu-id="36044-116">\\_997ToFabrikam</span></span>|<span data-ttu-id="36044-117">此空文件夹将接收 EDI 处理之后返回的 997 确认消息。</span><span class="sxs-lookup"><span data-stu-id="36044-117">This empty folder will receive the 997 acknowledgment message returned after EDI processing.</span></span> <span data-ttu-id="36044-118">此文件夹模拟在 Fabrikam 参与方发起 EDI 消息的应用程序。</span><span class="sxs-lookup"><span data-stu-id="36044-118">The folder simulates the application originating the EDI message at the Fabrikam party.</span></span>|  
|<span data-ttu-id="36044-119">\\_EDIXMLToContoso</span><span class="sxs-lookup"><span data-stu-id="36044-119">\\_EDIXMLToContoso</span></span>|<span data-ttu-id="36044-120">在 BizTalk Server 处理 EDI 消息后，此空文件夹将接收 XML 负载文件。</span><span class="sxs-lookup"><span data-stu-id="36044-120">This empty folder will receive the XML payload file after BizTalk Server has processed the EDI message.</span></span> <span data-ttu-id="36044-121">此文件夹模拟作为 EDI 负载的最终目标的业务线应用程序。</span><span class="sxs-lookup"><span data-stu-id="36044-121">This folder simulates the line-of-business application that is the final destination of the EDI payload.</span></span>|  
|<span data-ttu-id="36044-122">\\_MDNToFabrikam</span><span class="sxs-lookup"><span data-stu-id="36044-122">\\_MDNToFabrikam</span></span>|<span data-ttu-id="36044-123">此空文件夹将接收 AS2 处理之后从 BizTalk Server 返回的 MDN 消息。</span><span class="sxs-lookup"><span data-stu-id="36044-123">This empty folder will receive the MDN message returned from BizTalk Server after AS2 processing.</span></span> <span data-ttu-id="36044-124">此文件夹模拟 Fabrikam 参与方的应用程序。</span><span class="sxs-lookup"><span data-stu-id="36044-124">The folder simulates an application at the Fabrikam party.</span></span>|  
|<span data-ttu-id="36044-125">\Fabrikam</span><span class="sxs-lookup"><span data-stu-id="36044-125">\Fabrikam</span></span>|<span data-ttu-id="36044-126">此文件夹包含将 997 保存到 _997ToFabrikam 文件夹中并将 MDN 保存到 _MDNToFabrikam 文件夹中的 Default.aspx 文件。</span><span class="sxs-lookup"><span data-stu-id="36044-126">This folder contains the Default.aspx file that saves the 997 into the _997ToFabrikam folder and saves the MDN into the _MDNToFabrikam folder.</span></span>|  
|<span data-ttu-id="36044-127">\Schemas</span><span class="sxs-lookup"><span data-stu-id="36044-127">\Schemas</span></span>|<span data-ttu-id="36044-128">此文件夹包含 BizTalk 用于处理 EDI 消息的 X12_00401_864.xsd 架构和其他架构。</span><span class="sxs-lookup"><span data-stu-id="36044-128">This folder contains the X12_00401_864.xsd schema and other schemas that BizTalk uses to process the EDI message.</span></span> <span data-ttu-id="36044-129">此文件夹还包含你为了部署架构而将生成并部署的 Schemas.btproj 项目。</span><span class="sxs-lookup"><span data-stu-id="36044-129">The folder also contains the Schemas.btproj project that you will build and deploy in order to deploy the schemas.</span></span>|  
|<span data-ttu-id="36044-130">\Sender</span><span class="sxs-lookup"><span data-stu-id="36044-130">\Sender</span></span>|<span data-ttu-id="36044-131">此文件夹包含你为了创建用于发送 X12_00401_864.edi 测试消息（在 \AS2 Tutorial 文件夹中）和返回 MDN 的 Sender.exe 而将生成并编译的 Sender.csproj 项目。</span><span class="sxs-lookup"><span data-stu-id="36044-131">This folder contains the Sender.csproj project that you will build and compile to create Sender.exe, which you use to send the X12_00401_864.edi test message (in the \AS2 Tutorial folder) and to return the MDN.</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="36044-132">必要條件</span><span class="sxs-lookup"><span data-stu-id="36044-132">Prerequisites</span></span>  
 <span data-ttu-id="36044-133">你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="36044-133">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="36044-134">过程</span><span class="sxs-lookup"><span data-stu-id="36044-134">Procedures</span></span>  
  
#### <a name="to-set-the-security-permission-for-the-997-and-mdn-folders"></a><span data-ttu-id="36044-135">为 997 和 MDN 文件夹设置安全权限</span><span class="sxs-lookup"><span data-stu-id="36044-135">To set the security permission for the 997 and MDN folders</span></span>  
  
1. <span data-ttu-id="36044-136">在 Windows 资源管理器，转至[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_997ToFabrikam 文件夹。</span><span class="sxs-lookup"><span data-stu-id="36044-136">In Windows Explorer, move to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_997ToFabrikam folder.</span></span> <span data-ttu-id="36044-137">右键单击\\_997ToFabrikam 文件夹，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="36044-137">Right-click the \\_997ToFabrikam folder, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="36044-138">单击**安全**选项卡，然后依次**编辑**。</span><span class="sxs-lookup"><span data-stu-id="36044-138">Click the **Security** tab, and then click **Edit**.</span></span> <span data-ttu-id="36044-139">在中**权限**对话框中，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="36044-139">In the **Permissions** dialog box, click **Add**.</span></span>  
  
3. <span data-ttu-id="36044-140">在中**选择用户、 计算机、 服务帐户或组**对话框中的，在对象名称窗格中，输入`Everyone`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="36044-140">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, in the object names pane, enter `Everyone`, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="36044-141">选择**每个人都**中**组或用户名**框中，单击复选框**编写**(下**允许**列) 中**权限**窗格中，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="36044-141">Select **Everyone** in the **Group or user names** box, click the check box for **Write** (under the **Allow** column) in the **Permissions** pane, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="36044-142">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="36044-142">Click **OK**.</span></span>  
  
6. <span data-ttu-id="36044-143">重复上述步骤\\_MDNToFabrikam 文件夹。</span><span class="sxs-lookup"><span data-stu-id="36044-143">Repeat these steps for the \\_MDNToFabrikam folder.</span></span>  
  
#### <a name="to-mark-the-biztalk-server-host-as-32-bit"></a><span data-ttu-id="36044-144">将 BizTalk Server 主机标记为 32 位</span><span class="sxs-lookup"><span data-stu-id="36044-144">To mark the BizTalk Server Host as 32-Bit</span></span>  
  
1. > [!NOTE]
   >  <span data-ttu-id="36044-145">AS2 管道只能在 32 位进程中使用。</span><span class="sxs-lookup"><span data-stu-id="36044-145">The AS2 pipelines can only be used in a 32-bit process.</span></span> <span data-ttu-id="36044-146">如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装在 64 位操作系统上，则必须执行以下步骤将主机进程标记为仅限 32 位。</span><span class="sxs-lookup"><span data-stu-id="36044-146">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed on a 64-bit operating system, the following steps must be performed to mark the host processes as 32-bit only.</span></span>  
  
    <span data-ttu-id="36044-147">选择**启动**，选择**所有程序**，选择**Microsoft BizTalk Server**，然后选择**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="36044-147">Select **Start**, select **All Programs**, select **Microsoft BizTalk Server**, and then select **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="36044-148">在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，选择**平台设置**，然后选择**主机**。</span><span class="sxs-lookup"><span data-stu-id="36044-148">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, select **Platform Settings**, and then select **Hosts**.</span></span>  
  
3. <span data-ttu-id="36044-149">在详细信息窗格中，右键单击你想要使用本教程中，然后选择该进程内主机**属性**。</span><span class="sxs-lookup"><span data-stu-id="36044-149">In the details pane, right-click the in-process host you want to use for this tutorial and then select **Properties**.</span></span>  
  
4. <span data-ttu-id="36044-150">在中**主机属性**对话框中，在**常规**选项卡上，选择**仅限 32 位**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="36044-150">In the **Host Properties** dialog box, on the **General** tab, select **32-bit only**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="36044-151">为独立主机重复步骤 3-4。</span><span class="sxs-lookup"><span data-stu-id="36044-151">Repeat steps 3-4 for the isolated host.</span></span>  
  
   <span data-ttu-id="36044-152">如果 BizTalk Server 安装在 64 位操作系统上，则在使用 32 位 BizTalk 主机进程时，还必须将 IIS 设置为在 32 位模式下运行。</span><span class="sxs-lookup"><span data-stu-id="36044-152">If BizTalk Server is installed on a 64-bit operating system, you must also set IIS to run in 32-bit mode when using a 32-bit BizTalk host process.</span></span> <span data-ttu-id="36044-153">如何设置 IIS 中的显示[步骤 5： 配置贸易合作伙伴网页](../core/step-5-configure-the-trading-partner-web-pages.md)，如 IIS 可以设置 32 位工作进程上每个应用程序池。</span><span class="sxs-lookup"><span data-stu-id="36044-153">The instructions for setting IIS are presented within [Step 5: Configure the Trading Partner Web Pages](../core/step-5-configure-the-trading-partner-web-pages.md), as IIS allows you to set the 32-bit worker process on a per application pool basis.</span></span>  
  
#### <a name="to-add-reference-to-the-biztalk-edi-application"></a><span data-ttu-id="36044-154">若要添加到 BizTalk EDI 应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="36044-154">To add reference to the BizTalk EDI Application</span></span>  
  
1. <span data-ttu-id="36044-155">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在**应用程序**节点，右键单击你想要为 EDI，如 BizTalk Application 1 使用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="36044-155">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **Applications** node, right-click the application that you want to use for EDI, such as BizTalk Application 1.</span></span> <span data-ttu-id="36044-156">指向**添加**，然后单击引用。</span><span class="sxs-lookup"><span data-stu-id="36044-156">Point to **Add**, and then click References.</span></span>  
  
2. <span data-ttu-id="36044-157">在中**添加应用程序引用**对话框中，选择**BizTalk EDI 应用程序**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="36044-157">In the **Add Application Reference** dialog box, select **BizTalk EDI Application**, and then click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="36044-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="36044-158">Next Steps</span></span>  
 <span data-ttu-id="36044-159">如中所述部署示例 X12 架构[步骤 2： 创建和部署示例 X12 架构](../core/step-2-create-and-deploy-the-sample-x12-schema.md)</span><span class="sxs-lookup"><span data-stu-id="36044-159">You deploy the sample X12 schema as described in [Step 2: Create and Deploy the Sample X12 Schema](../core/step-2-create-and-deploy-the-sample-x12-schema.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36044-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="36044-160">See Also</span></span>  
 [<span data-ttu-id="36044-161">教程 3: AS2 教程</span><span class="sxs-lookup"><span data-stu-id="36044-161">Tutorial 3: AS2 Tutorial</span></span>](../core/tutorial-3-as2-tutorial.md)