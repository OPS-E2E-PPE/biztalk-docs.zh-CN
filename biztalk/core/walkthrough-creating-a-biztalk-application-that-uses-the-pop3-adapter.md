---
title: "演练： 创建 BizTalk 应用程序将使用 POP3 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tutorials, POP3 adapters
- configuring [POP3 adapters], mailboxes
- configuring [POP3 adapters], tutorials
- POP3 adapters, mailboxes
- POP3 adapters, tutorials
- configuring [POP3 adapters], Outlook Express
ms.assetid: b44c3b1d-7b4f-425c-831a-1ce5f6379595
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e677a4fb68ad4f6991585c191c8065a60b3fc337
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter"></a><span data-ttu-id="0c31a-102">演练： 创建使用 POP3 适配器 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="0c31a-102">Walkthrough: Creating a BizTalk Application That Uses the POP3 Adapter</span></span>
<span data-ttu-id="0c31a-103">本部分将指导您创建一个使用 POP3 适配器的简单 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c31a-103">This section takes you through creating a simple Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application using the POP3 adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c31a-104">该应用程序假设您有权限访问安装并配置了电子邮件服务的 Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 运行所在的计算机。</span><span class="sxs-lookup"><span data-stu-id="0c31a-104">The application assumes that you have access to a computer running Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] with Email Services installed and configured.</span></span> <span data-ttu-id="0c31a-105">有关配置具有电子邮件服务的 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 的信息，请参阅 Windows Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="0c31a-105">For information about configuring [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] with Email Services see Windows Server Help.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c31a-106">在本示例中，Microsoft Outlook Express 用作电子邮件客户端，[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 用作电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="0c31a-106">In this example Microsoft Outlook Express is used as the e-mail client and [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] is used as the e-mail server.</span></span> <span data-ttu-id="0c31a-107">不过，任何 POP3 电子邮件客户端和符合 RFC 的 POP3 服务器均可用于此方案。</span><span class="sxs-lookup"><span data-stu-id="0c31a-107">However, any POP3 e-mail client and RFC-compliant POP3 server could be used for this scenario.</span></span>  
  
 <span data-ttu-id="0c31a-108">此应用程序假设您尚未创建任何发送端口或接收位置。</span><span class="sxs-lookup"><span data-stu-id="0c31a-108">This application assumes that you have not yet created any send ports or receive locations.</span></span> <span data-ttu-id="0c31a-109">如果已存在发送端口或接收位置，请在执行以下步骤时替换相应的名称。</span><span class="sxs-lookup"><span data-stu-id="0c31a-109">If you have existing send ports or receive locations, substitute appropriate names when you work through the steps.</span></span>  
  
 <span data-ttu-id="0c31a-110">该应用程序是一个简单的基于内容的路由应用程序，仅使用一个接收位置和一个发送端口。</span><span class="sxs-lookup"><span data-stu-id="0c31a-110">The application is a simple content-based routing application using only a receive location and a send port.</span></span> <span data-ttu-id="0c31a-111">接收位置读取从运行的服务器上邮箱[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("Windows server"\)。</span><span class="sxs-lookup"><span data-stu-id="0c31a-111">The receive location reads from a mailbox on the server running [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("the Windows server"\).</span></span> <span data-ttu-id="0c31a-112">发送端口从该接收位置获取消息，并将其发送到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 本地文件系统的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0c31a-112">The send port takes the message from the receive location and sends it to a folder on the local file system of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0c31a-113">若要创建该应用程序，您必须执行以下操作：创建邮箱、设置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置和发送端口、启动发送端口并启用接收位置，以及向邮箱发送测试邮件。</span><span class="sxs-lookup"><span data-stu-id="0c31a-113">To create the application, you have to create the mailbox, set up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location and send port, start the send port and enable the receive location, and send a test message to the mailbox.</span></span> <span data-ttu-id="0c31a-114">请遵循以下步骤来创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c31a-114">Follow the steps below to create the application.</span></span>  
  
## <a name="create-a-mailbox-on-windows-server-2003"></a><span data-ttu-id="0c31a-115">在 Windows Server 2003 上创建邮箱</span><span class="sxs-lookup"><span data-stu-id="0c31a-115">Create a mailbox on Windows Server 2003</span></span>  
 <span data-ttu-id="0c31a-116">若要在安装了电子邮件服务的 Windows Server 2003 上创建邮箱，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0c31a-116">To create a mailbox on Windows Server 2003 with Email Services installed, follow these steps:</span></span>  
  
1.  <span data-ttu-id="0c31a-117">单击**启动**，指向**程序**，指向**管理工具**，然后单击**POP3 服务**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-117">Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **POP3 Service**.</span></span>  
  
2.  <span data-ttu-id="0c31a-118">展开 *\<servername\>*  ，单击想要创建邮箱的域。</span><span class="sxs-lookup"><span data-stu-id="0c31a-118">Expand *\<servername\>* and click the domain where you would like to create a mailbox.</span></span>  
  
3.  <span data-ttu-id="0c31a-119">在**POP3 服务**对话框中，在右窗格中，单击**添加邮箱**选项。</span><span class="sxs-lookup"><span data-stu-id="0c31a-119">In the **POP3 Service** dialog box, in the right pane, click the **Add Mailbox** option.</span></span>  
  
4.  <span data-ttu-id="0c31a-120">在**添加邮箱**对话框中，在**邮箱名称**框中，键入**EmailTest**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-120">In the **Add Mailbox** dialog box, in the **Mailbox Name** box, type **EmailTest**.</span></span>  
  
5.  <span data-ttu-id="0c31a-121">选择**创建相关的用户输入此邮箱**复选框。</span><span class="sxs-lookup"><span data-stu-id="0c31a-121">Select the **Create associated user for this mailbox** check box.</span></span>  
  
6.  <span data-ttu-id="0c31a-122">在**密码**和**确认密码**框中，键入一个密码，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-122">In the **Password** and **Confirm Password** boxes, type a password, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="0c31a-123">记下**帐户名称**和**邮件服务器**登录以明文形式中的身份验证用于显示的信息**POP3 服务**对话框中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-123">Make a note of the **Account name** and **Mail Server** log on information displayed for use with clear text authentication in the **POP3 Service** dialog box, and then click **OK**.</span></span> <span data-ttu-id="0c31a-124">为 POP3 传输类型配置的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置将使用此信息。</span><span class="sxs-lookup"><span data-stu-id="0c31a-124">This information will be used by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location that you configure with the POP3 transport type.</span></span>  
  
## <a name="create-the-receive-location"></a><span data-ttu-id="0c31a-125">创建接收位置</span><span class="sxs-lookup"><span data-stu-id="0c31a-125">Create the receive location</span></span>  
 <span data-ttu-id="0c31a-126">请遵循以下步骤创建接收位置：</span><span class="sxs-lookup"><span data-stu-id="0c31a-126">Follow these steps to create the receive location:</span></span>  
  
1.  <span data-ttu-id="0c31a-127">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台双击的默认数据库 **\<**  *machine_name***\>。BizTalkMgmtDb.dbo**，其中*machine_name*是你的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="0c31a-127">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console double-click the default database **\<***machine_name***\>.BizTalkMgmtDb.dbo**, where *machine_name* is the name of your computer.</span></span> <span data-ttu-id="0c31a-128">单击**应用程序**，然后单击**BizTalk.Application.1**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-128">Click **Applications**, then click **BizTalk.Application.1**.</span></span>  
  
2.  <span data-ttu-id="0c31a-129">右键单击**接收端口**，单击**新建**，单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-129">Right-click **Receive Ports**, click **New**, click **One-way receive port**.</span></span>  
  
3.  <span data-ttu-id="0c31a-130">在**接收端口属性**对话框中，在**名称**框中，键入**POP3Receive**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-130">In the **Receive Port Properties** dialog box, in the **Name** box, type **POP3Receive**.</span></span>  
  
4.  <span data-ttu-id="0c31a-131">单击**接收位置**，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-131">Click **Receive Locations**, and then click **New**.</span></span>  <span data-ttu-id="0c31a-132">在**接收位置属性**对话框中，在**名称**框中，键入**POP3Receive**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-132">In the **Receive Location Properties** dialog box, in the **Name** box, type **POP3Receive**.</span></span>  
  
5.  <span data-ttu-id="0c31a-133">在**传输类型**框中，选择**POP3**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-133">In the **Transport Type** box, select **POP3**.</span></span>  
  
6.  <span data-ttu-id="0c31a-134">在**接收处理程序**框中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-134">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
7.  <span data-ttu-id="0c31a-135">在**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-135">In the **Receive Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
8.  <span data-ttu-id="0c31a-136">在**传输**框中，单击**配置**按钮。</span><span class="sxs-lookup"><span data-stu-id="0c31a-136">In the **Transport** box, click the **Configure** button.</span></span>  
  
9. <span data-ttu-id="0c31a-137">在**POP3 传输属性**对话框中，在**应用 MIME 解码**框中，选择**False**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-137">In the **POP3 Transport Properties** dialog box, in the **Apply MIME Decoding** box, select **False**.</span></span>  
  
10. <span data-ttu-id="0c31a-138">在**邮件服务器**框中，键入您在其中创建邮箱的基于 Windows Server 的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="0c31a-138">In the **Mail Server** box, type the name of the Windows Server-based server where you created a mailbox.</span></span>  
  
11. <span data-ttu-id="0c31a-139">在**身份验证方案**框中，选择**基本**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-139">In the **Authentication Scheme** box, select **Basic**.</span></span>  
  
12. <span data-ttu-id="0c31a-140">在**密码**框中，单击下拉箭头，然后键入邮箱的密码。</span><span class="sxs-lookup"><span data-stu-id="0c31a-140">In the **Password** box, click the drop-down arrow and type the password for the mailbox.</span></span>  
  
13. <span data-ttu-id="0c31a-141">在**用户名**框中，键入邮箱，完全限定的用户名，例如 *username@host.domain.toplevel_domain。*</span><span class="sxs-lookup"><span data-stu-id="0c31a-141">In the **User Name** box, type the fully qualified user name for the mailbox, for example *username@host.domain.toplevel_domain.*</span></span>  
  
14. <span data-ttu-id="0c31a-142">在**轮询间隔**框中，键入**1**，单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="0c31a-142">In the **Polling Interval** box, type **1**, click **OK**, and then click **OK** again.</span></span>  
  
## <a name="create-the-send-port-and-destination-folder-on-the-biztalk-server"></a><span data-ttu-id="0c31a-143">在 BizTalk Server 上创建发送端口和目标文件夹</span><span class="sxs-lookup"><span data-stu-id="0c31a-143">Create the send port and destination folder on the BizTalk server</span></span>  
 <span data-ttu-id="0c31a-144">请遵循以下步骤在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上创建发送端口和目标文件夹：</span><span class="sxs-lookup"><span data-stu-id="0c31a-144">Follow these steps to create the send port and destination folder on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
1.  <span data-ttu-id="0c31a-145">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文件系统上创建一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="0c31a-145">Create a folder on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] file system.</span></span> <span data-ttu-id="0c31a-146">它将成为发送端口的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="0c31a-146">This will be the destination for the send port.</span></span>  
  
2.  <span data-ttu-id="0c31a-147">右键单击**发送端口**，单击**新建，**然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="0c31a-147">Right-click **Send Ports**, click **New,** then click **Static one-way Send Port.**</span></span>  
  
3.  <span data-ttu-id="0c31a-148">在**发送端口属性**对话框中，在**传输类型**框中，选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-148">In the **Send Port Properties** dialog box, in the **Transport Type** box, select **FILE**.</span></span>  
  
4.  <span data-ttu-id="0c31a-149">在**名称**框中，键入**SendToFile**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-149">In the **Name** box, type **SendToFile**.</span></span>  
  
5.  <span data-ttu-id="0c31a-150">在**传输**框中，单击**配置**按钮。</span><span class="sxs-lookup"><span data-stu-id="0c31a-150">In the **Transport** box, click the **Configure** button.</span></span>  
  
6.  <span data-ttu-id="0c31a-151">旁边**目标文件夹**框中，单击**浏览**，选择你在创建的文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-151">Next to the **Destination folder** box, click **Browse**, select the folder that you created on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="0c31a-152">在**文件名**框中，键入**%MessageID%.txt**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-152">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="0c31a-153">在**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-153">In the **Send Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
9. <span data-ttu-id="0c31a-154">单击 **“筛选器”**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-154">Click **Filters**.</span></span>  
  
10. <span data-ttu-id="0c31a-155">在**属性**框中，选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-155">In the **Property** box, select **BTS.ReceivePortName**.</span></span>  
  
11. <span data-ttu-id="0c31a-156">在**值**框中，键入**POP3Receive**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-156">In the **Value** box, type **POP3Receive**, and then click **OK**.</span></span>  
  
## <a name="enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="0c31a-157">启用接收位置和启动发送端口</span><span class="sxs-lookup"><span data-stu-id="0c31a-157">Enable the receive location and start the send port</span></span>  
 <span data-ttu-id="0c31a-158">请遵循以下步骤来启用接收位置和启动发送端口：</span><span class="sxs-lookup"><span data-stu-id="0c31a-158">Follow these steps to enable the receive location and start the send port:</span></span>  
  
1.  <span data-ttu-id="0c31a-159">右键单击**POP3Receive**接收位置，并依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-159">Right-click the **POP3Receive** receive location, and then click **Enable**.</span></span>  
  
2.  <span data-ttu-id="0c31a-160">右键单击**SendToFile**发送端口，并依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-160">Right-click the **SendToFile** send port, and then click **Start**.</span></span>  
  
 <span data-ttu-id="0c31a-161">下一步就是通过向接收位置监视的邮箱发送测试邮件来测试该应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c31a-161">The next step is to test the application by sending a test message to the mailbox monitored by the receive location.</span></span>  
  
## <a name="configure-outlook-express-to-send-an-e-mail-message-to-the-mailbox"></a><span data-ttu-id="0c31a-162">配置 Outlook Express 以便向邮箱发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="0c31a-162">Configure Outlook Express to send an e-mail message to the mailbox</span></span>  
 <span data-ttu-id="0c31a-163">请遵循以下步骤来配置 Outlook Express 向邮箱发送一封电子邮件：</span><span class="sxs-lookup"><span data-stu-id="0c31a-163">Follow these steps to configure Outlook Express to send an e-mail message to the mailbox:</span></span>  
  
1.  <span data-ttu-id="0c31a-164">单击**启动**，指向**程序**，然后单击**Outlook Express**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-164">Click **Start**, point to **Programs**, and then click **Outlook Express**.</span></span>  
  
2.  <span data-ttu-id="0c31a-165">在 Outlook Express 中，在**工具**菜单上，单击**帐户**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-165">In Outlook Express, on the **Tools** menu, click **Accounts**.</span></span>  
  
3.  <span data-ttu-id="0c31a-166">单击**添加**，然后单击**邮件**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-166">Click **Add** and then click **Mail**.</span></span>  
  
4.  <span data-ttu-id="0c31a-167">在**显示名称**框中，键入显示名称，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-167">In the **Display name** box, type a display name, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="0c31a-168">在**Internet 电子邮件地址**对话框中，在**电子邮件地址**框中，键入**EmailTest @< 域名 >**，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="0c31a-168">In the **Internet E-mail address** dialog box, in the **E-mail address** box, type **EmailTest@<domain_name>**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="0c31a-169">请确保输入的相应值*< 域名 >*。</span><span class="sxs-lookup"><span data-stu-id="0c31a-169">Make sure to enter the appropriate value for *<domain_name>*.</span></span> <span data-ttu-id="0c31a-170">此值应与在 Windows 服务器上 POP3 服务管理用户界面中创建此邮箱使用的域名匹配。</span><span class="sxs-lookup"><span data-stu-id="0c31a-170">This value should match the name of the domain under which this mailbox was created in the POP3 Service Administration interface on the Windows server.</span></span>  
  
6.  <span data-ttu-id="0c31a-171">在**电子邮件服务器名称**对话框中，在**传入邮件**和**传出邮件**框中，键入服务器名称或 Windows server 的 IP 地址，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-171">In the **E-mail Server names** dialog box, in the **Incoming mail** and **Outgoing mail** boxes, type the server name or IP address of the Windows server, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="0c31a-172">在**Internet 邮件登录**对话框中，在**帐户名称**框中，键入**EmailTest**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-172">In the **Internet Mail Logon** dialog box, in the **Account name** box, type **EmailTest**.</span></span>  
  
8.  <span data-ttu-id="0c31a-173">在**密码**框中，键入 EmailTest 帐户，请选择的密码**记住密码**选项，请单击**下一步**，然后单击**完成**.</span><span class="sxs-lookup"><span data-stu-id="0c31a-173">In the **Password** box, type the password for the EmailTest account, select the **Remember password** option, click **Next**, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="0c31a-174">单击以选择你刚刚创建的帐户，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-174">Click to select the account that you just created, and then click **Properties**.</span></span>  
  
10. <span data-ttu-id="0c31a-175">在**属性**对话框中，单击**高级**选项卡上，单击以选择该选项以**在服务器上保留一份消息**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="0c31a-175">In the **Properties** dialog box, click the **Advanced** tab, click to select the option to **Leave a copy of messages on the server**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="0c31a-176">在**Internet 帐户**对话框中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="0c31a-176">In the **Internet Accounts** dialog box, click **Close**.</span></span>  
  
12. <span data-ttu-id="0c31a-177">使用 Outlook Express 撰写一条测试消息，类型**测试**到**主题**字段和类型**EmailTest @< 域名 >**到**到**字段。</span><span class="sxs-lookup"><span data-stu-id="0c31a-177">Use Outlook Express to compose a test message, type **Test** into the **Subject** field, and type **EmailTest@<domain_name>** into the **To** field.</span></span>  
  
13. <span data-ttu-id="0c31a-178">单击**发送**发送测试消息。</span><span class="sxs-lookup"><span data-stu-id="0c31a-178">Click **Send** to send the test message.</span></span> <span data-ttu-id="0c31a-179">若要确保，Outlook Express 立即发送测试消息，请单击**发送/接收**Outlook Express 工具栏中的按钮。</span><span class="sxs-lookup"><span data-stu-id="0c31a-179">To ensure that Outlook Express sends the test message immediately, click the **Send/Recv** button in the Outlook Express toolbar.</span></span>  
  
## <a name="view-the-message"></a><span data-ttu-id="0c31a-180">查看邮件</span><span class="sxs-lookup"><span data-stu-id="0c31a-180">View the message</span></span>  
 <span data-ttu-id="0c31a-181">请遵循以下步骤查看消息：</span><span class="sxs-lookup"><span data-stu-id="0c31a-181">Follow these steps to view the message:</span></span>  
  
1.  <span data-ttu-id="0c31a-182">使用 Windows 资源管理器打开的文件夹，指定为**目标文件夹**发送端口。</span><span class="sxs-lookup"><span data-stu-id="0c31a-182">Use Windows Explorer to open the folder that you specified as the **Destination Folder** for the send port.</span></span>  
  
2.  <span data-ttu-id="0c31a-183">双击该文件夹中的文档，以便用记事本查看该文档的内容。</span><span class="sxs-lookup"><span data-stu-id="0c31a-183">Double click the document in the folder to view the contents of the document in Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c31a-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c31a-184">See Also</span></span>  
 [<span data-ttu-id="0c31a-185">POP3 适配器概述</span><span class="sxs-lookup"><span data-stu-id="0c31a-185">What Is the POP3 Adapter?</span></span>](../core/what-is-the-pop3-adapter.md)