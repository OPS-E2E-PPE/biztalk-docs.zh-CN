---
title: 演练：创建 BizTalk 应用程序使用 POP3 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorials, POP3 adapters
- configuring [POP3 adapters], mailboxes
- configuring [POP3 adapters], tutorials
- POP3 adapters, mailboxes
- POP3 adapters, tutorials
- configuring [POP3 adapters], Outlook Express
ms.assetid: b44c3b1d-7b4f-425c-831a-1ce5f6379595
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f94c34361eb69f2e9838da26a3ea30f95cb3a85
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250233"
---
# <a name="walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter"></a><span data-ttu-id="5861f-102">演练：创建 BizTalk 应用程序使用 POP3 适配器</span><span class="sxs-lookup"><span data-stu-id="5861f-102">Walkthrough: Creating a BizTalk Application That Uses the POP3 Adapter</span></span>
<span data-ttu-id="5861f-103">本部分将指导您创建的简单 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 POP3 适配器的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5861f-103">This section takes you through creating a simple Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application using the POP3 adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5861f-104">该应用程序假设您有权访问运行 Microsoft 的计算机[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]了电子邮件服务安装和配置。</span><span class="sxs-lookup"><span data-stu-id="5861f-104">The application assumes that you have access to a computer running Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] with Email Services installed and configured.</span></span> <span data-ttu-id="5861f-105">璝惠砞[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]了电子邮件服务，请参阅 Windows Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="5861f-105">For information about configuring [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] with Email Services see Windows Server Help.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="5861f-106">在此示例中 Microsoft Outlook Express 用作电子邮件客户端和[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]用作电子邮件服务器。</span><span class="sxs-lookup"><span data-stu-id="5861f-106">In this example Microsoft Outlook Express is used as the e-mail client and [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] is used as the e-mail server.</span></span> <span data-ttu-id="5861f-107">但是，任何 POP3 电子邮件客户端和符合 RFC 的 POP3 服务器无法用于此方案。</span><span class="sxs-lookup"><span data-stu-id="5861f-107">However, any POP3 e-mail client and RFC-compliant POP3 server could be used for this scenario.</span></span>  
  
 <span data-ttu-id="5861f-108">此应用程序假定你尚未创建任何发送端口或接收位置。</span><span class="sxs-lookup"><span data-stu-id="5861f-108">This application assumes that you have not yet created any send ports or receive locations.</span></span> <span data-ttu-id="5861f-109">在执行以下步骤时，如果您有现有发送端口或接收位置，请替换相应的名称。</span><span class="sxs-lookup"><span data-stu-id="5861f-109">If you have existing send ports or receive locations, substitute appropriate names when you work through the steps.</span></span>  
  
 <span data-ttu-id="5861f-110">应用程序是一个简单的基于内容的路由应用程序使用接收位置和发送端口。</span><span class="sxs-lookup"><span data-stu-id="5861f-110">The application is a simple content-based routing application using only a receive location and a send port.</span></span> <span data-ttu-id="5861f-111">接收位置从运行的服务器上的邮箱中读取[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("Windows server"\)。</span><span class="sxs-lookup"><span data-stu-id="5861f-111">The receive location reads from a mailbox on the server running [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]("the Windows server"\).</span></span> <span data-ttu-id="5861f-112">发送端口从接收位置获取消息，并将其发送到的本地文件系统上的文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5861f-112">The send port takes the message from the receive location and sends it to a folder on the local file system of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5861f-113">若要创建应用程序，您需要创建邮箱、 设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置和发送端口、 启动发送端口并启用接收位置，并向邮箱发送测试消息。</span><span class="sxs-lookup"><span data-stu-id="5861f-113">To create the application, you have to create the mailbox, set up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location and send port, start the send port and enable the receive location, and send a test message to the mailbox.</span></span> <span data-ttu-id="5861f-114">请按照以下步骤来创建应用程序。</span><span class="sxs-lookup"><span data-stu-id="5861f-114">Follow the steps below to create the application.</span></span>  
  
## <a name="create-a-mailbox-on-windows-server-2003"></a><span data-ttu-id="5861f-115">在 Windows Server 2003 上创建邮箱</span><span class="sxs-lookup"><span data-stu-id="5861f-115">Create a mailbox on Windows Server 2003</span></span>  
 <span data-ttu-id="5861f-116">若要安装的电子邮件服务与 Windows Server 2003 上创建邮箱，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="5861f-116">To create a mailbox on Windows Server 2003 with Email Services installed, follow these steps:</span></span>  
  
1. <span data-ttu-id="5861f-117">单击**启动**，依次指向**程序**，指向**管理工具**，然后单击**POP3 服务**。</span><span class="sxs-lookup"><span data-stu-id="5861f-117">Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **POP3 Service**.</span></span>  
  
2. <span data-ttu-id="5861f-118">展开*\<servername\>* 单击你想要创建邮箱的域。</span><span class="sxs-lookup"><span data-stu-id="5861f-118">Expand *\<servername\>* and click the domain where you would like to create a mailbox.</span></span>  
  
3. <span data-ttu-id="5861f-119">在中**POP3 服务**对话框中，在右窗格中，单击**添加邮箱**选项。</span><span class="sxs-lookup"><span data-stu-id="5861f-119">In the **POP3 Service** dialog box, in the right pane, click the **Add Mailbox** option.</span></span>  
  
4. <span data-ttu-id="5861f-120">在中**添加邮箱**对话框中**邮箱名称**框中，键入**EmailTest**。</span><span class="sxs-lookup"><span data-stu-id="5861f-120">In the **Add Mailbox** dialog box, in the **Mailbox Name** box, type **EmailTest**.</span></span>  
  
5. <span data-ttu-id="5861f-121">选择**创建相关的用户提供此邮箱**复选框。</span><span class="sxs-lookup"><span data-stu-id="5861f-121">Select the **Create associated user for this mailbox** check box.</span></span>  
  
6. <span data-ttu-id="5861f-122">在中**密码**并**确认密码**框中，键入一个密码，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5861f-122">In the **Password** and **Confirm Password** boxes, type a password, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="5861f-123">请记下的**帐户名称**并**邮件服务器**登录信息显示的用于明文形式中的身份验证**POP3 服务**对话框中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5861f-123">Make a note of the **Account name** and **Mail Server** log on information displayed for use with clear text authentication in the **POP3 Service** dialog box, and then click **OK**.</span></span> <span data-ttu-id="5861f-124">此信息将由[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]POP3 传输类型配置的接收位置。</span><span class="sxs-lookup"><span data-stu-id="5861f-124">This information will be used by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location that you configure with the POP3 transport type.</span></span>  
  
## <a name="create-the-receive-location"></a><span data-ttu-id="5861f-125">创建接收位置</span><span class="sxs-lookup"><span data-stu-id="5861f-125">Create the receive location</span></span>  
 <span data-ttu-id="5861f-126">请执行以下步骤创建接收位置：</span><span class="sxs-lookup"><span data-stu-id="5861f-126">Follow these steps to create the receive location:</span></span>  
  
1. <span data-ttu-id="5861f-127">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中双击默认数据库**\<** <em>m a c h</em>**\>。BizTalkMgmtDb.dbo**，其中*m a c h*是您的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="5861f-127">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console double-click the default database **\<**<em>machine_name</em>**\>.BizTalkMgmtDb.dbo**, where *machine_name* is the name of your computer.</span></span> <span data-ttu-id="5861f-128">单击**应用程序**，然后单击**BizTalk.Application.1**。</span><span class="sxs-lookup"><span data-stu-id="5861f-128">Click **Applications**, then click **BizTalk.Application.1**.</span></span>  
  
2. <span data-ttu-id="5861f-129">右键单击**接收端口**，单击**新建**，单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="5861f-129">Right-click **Receive Ports**, click **New**, click **One-way receive port**.</span></span>  
  
3. <span data-ttu-id="5861f-130">在中**接收端口属性**对话框中**名称**框中，键入**POP3Receive**。</span><span class="sxs-lookup"><span data-stu-id="5861f-130">In the **Receive Port Properties** dialog box, in the **Name** box, type **POP3Receive**.</span></span>  
  
4. <span data-ttu-id="5861f-131">单击**接收位置**，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="5861f-131">Click **Receive Locations**, and then click **New**.</span></span>  <span data-ttu-id="5861f-132">在中**接收位置属性**对话框中**名称**框中，键入**POP3Receive**。</span><span class="sxs-lookup"><span data-stu-id="5861f-132">In the **Receive Location Properties** dialog box, in the **Name** box, type **POP3Receive**.</span></span>  
  
5. <span data-ttu-id="5861f-133">在中**传输类型**框中，选择**POP3**。</span><span class="sxs-lookup"><span data-stu-id="5861f-133">In the **Transport Type** box, select **POP3**.</span></span>  
  
6. <span data-ttu-id="5861f-134">在中**接收处理程序**框中，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="5861f-134">In the **Receive Handler** box, select **BizTalkServerApplication**.</span></span>  
  
7. <span data-ttu-id="5861f-135">在中**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruReceive**。</span><span class="sxs-lookup"><span data-stu-id="5861f-135">In the **Receive Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruReceive**.</span></span>  
  
8. <span data-ttu-id="5861f-136">在中**传输**框中，单击**配置**按钮。</span><span class="sxs-lookup"><span data-stu-id="5861f-136">In the **Transport** box, click the **Configure** button.</span></span>  
  
9. <span data-ttu-id="5861f-137">在中**POP3 传输属性**对话框中**应用 MIME 解码**框中，选择**False**。</span><span class="sxs-lookup"><span data-stu-id="5861f-137">In the **POP3 Transport Properties** dialog box, in the **Apply MIME Decoding** box, select **False**.</span></span>  
  
10. <span data-ttu-id="5861f-138">在中**邮件服务器**框中，键入创建邮箱的基于 Windows Server 的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5861f-138">In the **Mail Server** box, type the name of the Windows Server-based server where you created a mailbox.</span></span>  
  
11. <span data-ttu-id="5861f-139">在中**身份验证方案**框中，选择**基本**。</span><span class="sxs-lookup"><span data-stu-id="5861f-139">In the **Authentication Scheme** box, select **Basic**.</span></span>  
  
12. <span data-ttu-id="5861f-140">在中**密码**框中，单击下拉箭头，然后键入该邮箱的密码。</span><span class="sxs-lookup"><span data-stu-id="5861f-140">In the **Password** box, click the drop-down arrow and type the password for the mailbox.</span></span>  
  
13. <span data-ttu-id="5861f-141">在中**用户名**框中，键入该邮箱的完全限定的用户名，例如 <em>username@host.domain.toplevel_domain。</em></span><span class="sxs-lookup"><span data-stu-id="5861f-141">In the **User Name** box, type the fully qualified user name for the mailbox, for example <em>username@host.domain.toplevel_domain.</em></span></span>  
  
14. <span data-ttu-id="5861f-142">在中**轮询间隔**框中，键入**1**，单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="5861f-142">In the **Polling Interval** box, type **1**, click **OK**, and then click **OK** again.</span></span>  
  
## <a name="create-the-send-port-and-destination-folder-on-the-biztalk-server"></a><span data-ttu-id="5861f-143">在 BizTalk server 上创建发送端口和目标文件夹</span><span class="sxs-lookup"><span data-stu-id="5861f-143">Create the send port and destination folder on the BizTalk server</span></span>  
 <span data-ttu-id="5861f-144">请按照以下步骤创建发送端口和目标文件夹上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5861f-144">Follow these steps to create the send port and destination folder on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span></span>  
  
1. <span data-ttu-id="5861f-145">上创建一个文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文件系统。</span><span class="sxs-lookup"><span data-stu-id="5861f-145">Create a folder on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] file system.</span></span> <span data-ttu-id="5861f-146">这将是发送端口的目标。</span><span class="sxs-lookup"><span data-stu-id="5861f-146">This will be the destination for the send port.</span></span>  
  
2. <span data-ttu-id="5861f-147">右键单击**发送端口**，单击**新建，** 然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="5861f-147">Right-click **Send Ports**, click **New,** then click **Static one-way Send Port.**</span></span>  
  
3. <span data-ttu-id="5861f-148">在中**发送端口属性**对话框中**传输类型**框中，选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="5861f-148">In the **Send Port Properties** dialog box, in the **Transport Type** box, select **FILE**.</span></span>  
  
4. <span data-ttu-id="5861f-149">在中**名称**框中，键入**SendToFile**。</span><span class="sxs-lookup"><span data-stu-id="5861f-149">In the **Name** box, type **SendToFile**.</span></span>  
  
5. <span data-ttu-id="5861f-150">在中**传输**框中，单击**配置**按钮。</span><span class="sxs-lookup"><span data-stu-id="5861f-150">In the **Transport** box, click the **Configure** button.</span></span>  
  
6. <span data-ttu-id="5861f-151">下一步**目标文件夹**框中，单击**浏览**，选择创建的文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5861f-151">Next to the **Destination folder** box, click **Browse**, select the folder that you created on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then click **OK**.</span></span>  
  
7. <span data-ttu-id="5861f-152">在中**文件名**框中，键入 **%MessageID%.txt**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5861f-152">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="5861f-153">在中**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="5861f-153">In the **Send Pipeline** box, select **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**.</span></span>  
  
9. <span data-ttu-id="5861f-154">单击 **“筛选器”**。</span><span class="sxs-lookup"><span data-stu-id="5861f-154">Click **Filters**.</span></span>  
  
10. <span data-ttu-id="5861f-155">在中**属性**框中，选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="5861f-155">In the **Property** box, select **BTS.ReceivePortName**.</span></span>  
  
11. <span data-ttu-id="5861f-156">在中**值**框中，键入**POP3Receive**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5861f-156">In the **Value** box, type **POP3Receive**, and then click **OK**.</span></span>  
  
## <a name="enable-the-receive-location-and-start-the-send-port"></a><span data-ttu-id="5861f-157">启用接收位置并启动发送端口</span><span class="sxs-lookup"><span data-stu-id="5861f-157">Enable the receive location and start the send port</span></span>  
 <span data-ttu-id="5861f-158">请按照下列步骤以启用接收位置并启动发送端口：</span><span class="sxs-lookup"><span data-stu-id="5861f-158">Follow these steps to enable the receive location and start the send port:</span></span>  
  
1. <span data-ttu-id="5861f-159">右键单击**POP3Receive**接收位置，然后依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="5861f-159">Right-click the **POP3Receive** receive location, and then click **Enable**.</span></span>  
  
2. <span data-ttu-id="5861f-160">右键单击**SendToFile**发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="5861f-160">Right-click the **SendToFile** send port, and then click **Start**.</span></span>  
  
   <span data-ttu-id="5861f-161">下一步是通过向接收位置监视的邮箱发送测试消息来测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="5861f-161">The next step is to test the application by sending a test message to the mailbox monitored by the receive location.</span></span>  
  
## <a name="configure-outlook-express-to-send-an-e-mail-message-to-the-mailbox"></a><span data-ttu-id="5861f-162">配置 Outlook Express 向邮箱发送一封电子邮件</span><span class="sxs-lookup"><span data-stu-id="5861f-162">Configure Outlook Express to send an e-mail message to the mailbox</span></span>  
 <span data-ttu-id="5861f-163">请按照下列步骤来配置 Outlook Express 向邮箱发送一封电子邮件：</span><span class="sxs-lookup"><span data-stu-id="5861f-163">Follow these steps to configure Outlook Express to send an e-mail message to the mailbox:</span></span>  
  
1.  <span data-ttu-id="5861f-164">单击**启动**，依次指向**程序**，然后单击**Outlook Express**。</span><span class="sxs-lookup"><span data-stu-id="5861f-164">Click **Start**, point to **Programs**, and then click **Outlook Express**.</span></span>  
  
2.  <span data-ttu-id="5861f-165">在 Outlook Express 中，在**工具**菜单上，单击**帐户**。</span><span class="sxs-lookup"><span data-stu-id="5861f-165">In Outlook Express, on the **Tools** menu, click **Accounts**.</span></span>  
  
3.  <span data-ttu-id="5861f-166">单击**外**，然后单击**邮件**。</span><span class="sxs-lookup"><span data-stu-id="5861f-166">Click **Add** and then click **Mail**.</span></span>  
  
4.  <span data-ttu-id="5861f-167">在中**显示名称**框中，键入显示名称，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5861f-167">In the **Display name** box, type a display name, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="5861f-168">在中**Internet 电子邮件地址**对话框中**电子邮件地址**框中，键入**EmailTest @< 域名 >**，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="5861f-168">In the **Internet E-mail address** dialog box, in the **E-mail address** box, type **EmailTest@<domain_name>**, and then click **Next**.</span></span>  
  
     <span data-ttu-id="5861f-169">请务必输入适当的值 *< 域名 >*。</span><span class="sxs-lookup"><span data-stu-id="5861f-169">Make sure to enter the appropriate value for *<domain_name>*.</span></span> <span data-ttu-id="5861f-170">此值应与在 Windows 服务器上的 POP3 服务管理接口中以其名义创建此邮箱的域的名称匹配。</span><span class="sxs-lookup"><span data-stu-id="5861f-170">This value should match the name of the domain under which this mailbox was created in the POP3 Service Administration interface on the Windows server.</span></span>  
  
6.  <span data-ttu-id="5861f-171">在中**电子邮件服务器名称**对话框中**传入邮件**并**传出邮件**框中，键入服务器名称或 IP 地址的 Windows 服务器，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5861f-171">In the **E-mail Server names** dialog box, in the **Incoming mail** and **Outgoing mail** boxes, type the server name or IP address of the Windows server, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="5861f-172">在中**Internet 邮件登录**对话框中**帐户名称**框中，键入**EmailTest**。</span><span class="sxs-lookup"><span data-stu-id="5861f-172">In the **Internet Mail Logon** dialog box, in the **Account name** box, type **EmailTest**.</span></span>  
  
8.  <span data-ttu-id="5861f-173">在中**密码**框中，键入 EmailTest 帐户，请选择的密码**记住密码**选项，单击**下一步**，然后单击**完成**.</span><span class="sxs-lookup"><span data-stu-id="5861f-173">In the **Password** box, type the password for the EmailTest account, select the **Remember password** option, click **Next**, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="5861f-174">单击以选择刚创建的帐户，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="5861f-174">Click to select the account that you just created, and then click **Properties**.</span></span>  
  
10. <span data-ttu-id="5861f-175">在**属性**对话框中，单击**高级**选项卡中，单击以选择选项**保留消息的副本服务器上**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="5861f-175">In the **Properties** dialog box, click the **Advanced** tab, click to select the option to **Leave a copy of messages on the server**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="5861f-176">在中**Internet 帐户**对话框中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="5861f-176">In the **Internet Accounts** dialog box, click **Close**.</span></span>  
  
12. <span data-ttu-id="5861f-177">使用 Outlook Express 撰写测试消息，类型**测试**成**主题**字段中，然后键入**EmailTest @< 域名 >** 到**到**字段。</span><span class="sxs-lookup"><span data-stu-id="5861f-177">Use Outlook Express to compose a test message, type **Test** into the **Subject** field, and type **EmailTest@<domain_name>** into the **To** field.</span></span>  
  
13. <span data-ttu-id="5861f-178">单击**发送**发送测试消息。</span><span class="sxs-lookup"><span data-stu-id="5861f-178">Click **Send** to send the test message.</span></span> <span data-ttu-id="5861f-179">若要确保，Outlook Express 立即发送测试消息，请单击**发送/接收**Outlook Express 工具栏中的按钮。</span><span class="sxs-lookup"><span data-stu-id="5861f-179">To ensure that Outlook Express sends the test message immediately, click the **Send/Recv** button in the Outlook Express toolbar.</span></span>  
  
## <a name="view-the-message"></a><span data-ttu-id="5861f-180">查看消息</span><span class="sxs-lookup"><span data-stu-id="5861f-180">View the message</span></span>  
 <span data-ttu-id="5861f-181">请按照下列步骤以查看该消息：</span><span class="sxs-lookup"><span data-stu-id="5861f-181">Follow these steps to view the message:</span></span>  
  
1.  <span data-ttu-id="5861f-182">使用 Windows 资源管理器中打开指定为的文件夹**目标文件夹**发送端口。</span><span class="sxs-lookup"><span data-stu-id="5861f-182">Use Windows Explorer to open the folder that you specified as the **Destination Folder** for the send port.</span></span>  
  
2.  <span data-ttu-id="5861f-183">双击要在记事本中查看文档的内容的文件夹中的文档。</span><span class="sxs-lookup"><span data-stu-id="5861f-183">Double click the document in the folder to view the contents of the document in Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5861f-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="5861f-184">See Also</span></span>  
 [<span data-ttu-id="5861f-185">POP3 适配器概述</span><span class="sxs-lookup"><span data-stu-id="5861f-185">What Is the POP3 Adapter?</span></span>](../core/what-is-the-pop3-adapter.md)