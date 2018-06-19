---
title: 消息修复和新提交故障排除 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, Message Repair and New Submission
- Message Repair and New Submission, troubleshooting
ms.assetid: bb07a286-6f02-4639-b5fa-a3647e356ac8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d341a7f03c70e1ddcd242d7804b162338798e94
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25965411"
---
# <a name="message-repair-and-new-submission-troubleshooting"></a><span data-ttu-id="32286-102">消息修复和新提交疑难解答</span><span class="sxs-lookup"><span data-stu-id="32286-102">Message Repair and New Submission Troubleshooting</span></span>
## <a name="a-repaired-message-cannot-be-submitted-if-the-envelope-schema-is-not-deployed"></a><span data-ttu-id="32286-103">无法提交修复后的消息，如果未部署信封架构</span><span class="sxs-lookup"><span data-stu-id="32286-103">A repaired message cannot be submitted if the envelope schema is not deployed</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-104">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-104">Symptom</span></span>  
 <span data-ttu-id="32286-105">如果尝试以提交一条消息，您已修复，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]文章以下消息：</span><span class="sxs-lookup"><span data-stu-id="32286-105">When you attempt to submit a message that you have repaired, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] posts the following message:</span></span>  
  
 <span data-ttu-id="32286-106">"适配器出现故障，以传输消息将发送端口"http://mrsrtest:80/StsWebReceive/default.aspx?PartnerId=Unparsed 和 FolderType = MessagesInbox"。</span><span class="sxs-lookup"><span data-stu-id="32286-106">"The adapter failed to transmit message going to send port "http://mrsrtest:80/StsWebReceive/default.aspx?PartnerId=Unparsed&FolderType=MessagesInbox".</span></span> <span data-ttu-id="32286-107">它将为此发送端口指定的重试时间间隔过后重新传输。</span><span class="sxs-lookup"><span data-stu-id="32286-107">It will be retransmitted after the retry interval specified for this Send Port.</span></span> <span data-ttu-id="32286-108">详细信息:"80131600"。</span><span class="sxs-lookup"><span data-stu-id="32286-108">Details:"80131600".</span></span> <span data-ttu-id="32286-109">有关详细信息，请参阅帮助和支持中心[http://go.microsoft.com/fwlink/?LinkId=142493](http://go.microsoft.com/fwlink/?LinkId=142493)。</span><span class="sxs-lookup"><span data-stu-id="32286-109">For more information, see Help and Support Center at [http://go.microsoft.com/fwlink/?LinkId=142493](http://go.microsoft.com/fwlink/?LinkId=142493).</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="32286-110">可能的原因</span><span class="sxs-lookup"><span data-stu-id="32286-110">Possible Cause</span></span>  
 <span data-ttu-id="32286-111">未部署信封架构。</span><span class="sxs-lookup"><span data-stu-id="32286-111">The envelope schema is not deployed.</span></span> <span data-ttu-id="32286-112">这适用于任何 MT*xxx*消息或分析失败的任何消息。</span><span class="sxs-lookup"><span data-stu-id="32286-112">This is true for any MT*xxx* message or any message that has failed parsing.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-113">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-113">Solution</span></span>  
 <span data-ttu-id="32286-114">部署使用每个消息架构信封架构 (\<驱动器\>: files\microsoft BizTalk Accelerator for SWIFT\<版本\>消息包 \SWIFT Messages\ A4SWIFT SRG\<版本\>\Category n\MTxxx.xsd) 和未分析的信封架构 (\<驱动器\>: files\microsoft BizTalk Accelerator for SWIFT\<版本\>消息包 \SWIFT Messages\ A4SWIFT SRG\<版本\>\ 未分析 Message\EnvelopeUnparsedMessage.xsd)。</span><span class="sxs-lookup"><span data-stu-id="32286-114">Deploy an envelope schema for each message schema that you are using (\<drive\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack \SWIFT Messages\ A4SWIFT-SRG\<version\>\Category n\MTxxx.xsd) and for unparsed envelope schema (\<drive\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack \SWIFT Messages\ A4SWIFT-SRG\<version\>\ Unparsed Message\EnvelopeUnparsedMessage.xsd).</span></span> <span data-ttu-id="32286-115">有关详细信息，请参阅[部署 A4SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="32286-115">For more information, see [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span></span>  
  
## <a name="you-cannot-submit-a-fixed-unparsed-message-from-a-mrsr-site-library-named-other-than-unparsed"></a><span data-ttu-id="32286-116">无法提交一个名为"Unparsed"以外的 MRSR 站点库中的固定未分析的消息</span><span class="sxs-lookup"><span data-stu-id="32286-116">You cannot submit a fixed unparsed message from a MRSR site library named other than "Unparsed"</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-117">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-117">Symptom</span></span>  
 <span data-ttu-id="32286-118">当你尝试提交已从 MRSR 站点文档库中未命名为"Unparsed"修复未分析的消息时，则操作将失败。</span><span class="sxs-lookup"><span data-stu-id="32286-118">When you try to submit an unparsed message that you have fixed from a MRSR site document library that is not named "Unparsed", the operation fails.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="32286-119">可能的原因</span><span class="sxs-lookup"><span data-stu-id="32286-119">Possible Cause</span></span>  
 <span data-ttu-id="32286-120">A4SWIFT 无法成功提交未命名为"Unparsed"库中的消息。</span><span class="sxs-lookup"><span data-stu-id="32286-120">A4SWIFT cannot successfully submit a message from a library that is not named "Unparsed".</span></span> <span data-ttu-id="32286-121">如果你有现有的"Unparsed"文档库 MRSR 站点中安装 MRSR （消息修复） 功能之前，A4SWIFT 安装程序将创建一个后缀对名为"Unparsed"的未分析消息的库。</span><span class="sxs-lookup"><span data-stu-id="32286-121">If you have an existing "Unparsed" document library in MRSR site before you install the MRSR (message repair) feature, A4SWIFT setup will create a library for unparsed messages entitled "Unparsed" with a suffix.</span></span> <span data-ttu-id="32286-122">当它收到一条消息，A4SWIFT 无法分析时，它将将消息路由到它创建该库。</span><span class="sxs-lookup"><span data-stu-id="32286-122">When it receives a message that A4SWIFT could not parse, it will route the message to that library that it created.</span></span> <span data-ttu-id="32286-123">但是，当你尝试提交该库中的消息，该操作将失败。</span><span class="sxs-lookup"><span data-stu-id="32286-123">However, when you try to submit a message from that library, the operation will fail.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-124">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-124">Solution</span></span>  
 <span data-ttu-id="32286-125">删除 MRSR 功能，删除未分析的库，然后重新安装 MRSR 功能。</span><span class="sxs-lookup"><span data-stu-id="32286-125">Remove the MRSR feature, delete the Unparsed library, and then reinstall the MRSR feature.</span></span>  
  
## <a name="cannot-loop-back-a-message-in-a-two-stage-workflow"></a><span data-ttu-id="32286-126">不能环回两阶段工作流中的消息</span><span class="sxs-lookup"><span data-stu-id="32286-126">Cannot loop back a message in a two-stage workflow</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-127">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-127">Symptom</span></span>  
 <span data-ttu-id="32286-128">如果您具有仅创建阶段和修复阶段的工作流的修复阶段中拒绝了一条消息，提交失败。</span><span class="sxs-lookup"><span data-stu-id="32286-128">If you reject a message in the Repair stage of a workflow that has only a Create stage and a Repair stage, the submission fails.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="32286-129">将消息路由到 MessageBox 并发布以下的错误消息：</span><span class="sxs-lookup"><span data-stu-id="32286-129"> routes the message back to the MessageBox and posts the following error message:</span></span>  
  
 <span data-ttu-id="32286-130">"无法重置到工作流中的第一个阶段。"</span><span class="sxs-lookup"><span data-stu-id="32286-130">"Could not reset to the first stage in the workflow."</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="32286-131">可能的原因</span><span class="sxs-lookup"><span data-stu-id="32286-131">Possible Cause</span></span>  
 <span data-ttu-id="32286-132">具有仅创建阶段和修复阶段的工作流不支持消息环回。</span><span class="sxs-lookup"><span data-stu-id="32286-132">Message loopback is not supported for a workflow that has only a Create stage and a Repair stage.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-133">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-133">Solution</span></span>  
 <span data-ttu-id="32286-134">将另一个阶段添加到两个阶段工作流，或取消提交。</span><span class="sxs-lookup"><span data-stu-id="32286-134">Add another stage to the two-stage workflow, or cancel the submission.</span></span>  
  
## <a name="cannot-open-a-message-in-the-repair-inbox-in-mrsr"></a><span data-ttu-id="32286-135">无法打开在 MRSR 内的修复收件箱中的一条消息</span><span class="sxs-lookup"><span data-stu-id="32286-135">Cannot open a message in the repair inbox in MRSR</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-136">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-136">Symptom</span></span>  
 <span data-ttu-id="32286-137">当你尝试在 MRSR 内的修复收件箱中打开一条消息时，你会收到一个弹出窗口中的以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="32286-137">When you try to open a message in the repair inbox in MRSR, you receive the following error message in a popup:</span></span>  
  
 <span data-ttu-id="32286-138">"无法打开登录 A4SWIFT 中所请求的数据库。</span><span class="sxs-lookup"><span data-stu-id="32286-138">"Cannot open database requested in login 'A4SWIFT'.</span></span> <span data-ttu-id="32286-139">登录失败。</span><span class="sxs-lookup"><span data-stu-id="32286-139">Login fails.</span></span> <span data-ttu-id="32286-140">用户 NT AUTHORITY\NETWORK SERVICE 登录失败。</span><span class="sxs-lookup"><span data-stu-id="32286-140">Login failed for user 'NT AUTHORITY\NETWORK SERVICE'.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="32286-141">可能的原因</span><span class="sxs-lookup"><span data-stu-id="32286-141">Possible Cause</span></span>  
 <span data-ttu-id="32286-142">登录帐户有关的 web 应用程序下运行 A4SWIFT_MRSR web 服务帐户是 Network Service，不是本地或域帐户为 A4SWIFT 用户组中。</span><span class="sxs-lookup"><span data-stu-id="32286-142">The login account for the web application that the A4SWIFT_MRSR web service runs under is Network Service, not a local or domain account that is in the A4SWIFT Users group.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-143">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-143">Solution</span></span>  
 <span data-ttu-id="32286-144">更改 web 应用程序运行 A4SWIFT_MRSR web 服务的登录帐户。</span><span class="sxs-lookup"><span data-stu-id="32286-144">Change the login account for the web application that the A4SWIFT_MRSR web service runs under.</span></span>  
  
##### <a name="to-change-the-login-account-for-the-web-application-that-the-a4swiftmrsr-web-service-runs-under"></a><span data-ttu-id="32286-145">若要更改的 web 应用程序下运行 A4SWIFT_MRSR web 服务的登录帐户</span><span class="sxs-lookup"><span data-stu-id="32286-145">To change the login account for the web application that the A4SWIFT_MRSR web service runs under</span></span>  
  
1.  <span data-ttu-id="32286-146">单击 **启动**, ，指向 **所有程序**, ，指向 **管理工具**, ，然后单击 **Internet Information Services (IIS) Manager**。</span><span class="sxs-lookup"><span data-stu-id="32286-146">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="32286-147">在 IIS 管理器中，展开 ***\<服务器名称\>* （本地计算机）** 节点，**应用程序池**节点和**Web站点**节点。</span><span class="sxs-lookup"><span data-stu-id="32286-147">In IIS Manager, expand the ***\<server name\>* (local computer)** node, the **Application Pools** node and the **Web Sites** node.</span></span> <span data-ttu-id="32286-148">在网站节点下展开**Default Web Site**节点。</span><span class="sxs-lookup"><span data-stu-id="32286-148">Under the Web Sites node, expand the **Default Web Site** node.</span></span>  
  
3.  <span data-ttu-id="32286-149">在 Default Web Site 节点中，右键单击**A4SWIFT_MRSR**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="32286-149">Under the Default Web Site node, right-click **A4SWIFT_MRSR**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="32286-150">在 A4SWIFT_MRSR 属性对话框中，请注意应用程序池。</span><span class="sxs-lookup"><span data-stu-id="32286-150">In the A4SWIFT_MRSR Properties dialog box, note the Application pool.</span></span>  
  
5.  <span data-ttu-id="32286-151">在 IIS 管理器对话框中的下的应用程序池节点中，右键单击 A4SWIFT_MRSR，应用程序池，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="32286-151">In the IIS Manager dialog box, under the Application Pools node, right-click the application pool for A4SWIFT_MRSR, and then click **Properties**.</span></span>  
  
6.  <span data-ttu-id="32286-152">在\<应用程序池名称\>属性对话框中，单击**标识**注意。</span><span class="sxs-lookup"><span data-stu-id="32286-152">In the \<application pool name\> Properties dialog box, click the **Identity** note.</span></span> <span data-ttu-id="32286-153">如果**预定义**单击和**网络服务**是处于选中状态，单击**可配置**，输入你的本地或域帐户，然后输入你的密码。</span><span class="sxs-lookup"><span data-stu-id="32286-153">If **Predefined** is clicked and **Network Service** is selected, click **Configurable**, enter your local or domain account, and then enter your password.</span></span> <span data-ttu-id="32286-154">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="32286-154">Click **OK**.</span></span>  
  
## <a name="a-message-created-in-mrsr-site-on-a-localized-computer-is-not-processed"></a><span data-ttu-id="32286-155">在本地化的计算机上的 MRSR 站点中创建的消息不处理</span><span class="sxs-lookup"><span data-stu-id="32286-155">A message created in MRSR site on a localized computer is not processed</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-156">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-156">Symptom</span></span>  
 <span data-ttu-id="32286-157">当用户使用的本地化的平台运行的 A4SWIFT 英语版本创建中的消息[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]MRSR 中的窗体和将消息提交成功，将显示该消息将使用的消息修复和新的提交业务流程，但未成功处理。</span><span class="sxs-lookup"><span data-stu-id="32286-157">When a user working on an English version of A4SWIFT that is running on a localized platform creates a message in an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form in MRSR, and submits the message successfully, the message appears to be consumed by the Message Repair and New Submission orchestration, but is not successfully processed.</span></span> <span data-ttu-id="32286-158">消息提交到发件箱，但不是由 BizTalk 适配器选取。</span><span class="sxs-lookup"><span data-stu-id="32286-158">The message is submitted to the outbox, but is not picked up by the BizTalk adapter.</span></span> <span data-ttu-id="32286-159">没有错误或警告发布在事件查看器中，并且不没有正在运行的业务流程实例 HAT 中的任何记录。</span><span class="sxs-lookup"><span data-stu-id="32286-159">No error or warning is posted in the Event Viewer, and there is no record of a running orchestration instance in HAT.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="32286-160">可能的原因</span><span class="sxs-lookup"><span data-stu-id="32286-160">Possible Cause</span></span>  
 <span data-ttu-id="32286-161">为 STS 输入的 uri 的路径。发件箱接收位置包含的英语名称，而不是本地化名称。</span><span class="sxs-lookup"><span data-stu-id="32286-161">The path entered as the URI for the STS.Outbox receive location contains the English name, not the localized name.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-162">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-162">Solution</span></span>  
 <span data-ttu-id="32286-163">更改 STS 的 URI 地址。发件箱接收位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="32286-163">Change the URI address for the STS.Outbox receive location as follows:</span></span>  
  
1.  <span data-ttu-id="32286-164">在 BizTalk Server 2009 的管理控制台中，展开**BizTalk 组**，**应用程序**，和**BizTalk 应用程序 1 节点**。</span><span class="sxs-lookup"><span data-stu-id="32286-164">In the BizTalk Server 2009 Administration Console, expand the **BizTalk Group**, **Applications**, and **BizTalk Application 1 nodes**.</span></span>  
  
2.  <span data-ttu-id="32286-165">单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="32286-165">Click **Receive Locations**.</span></span>  
  
3.  <span data-ttu-id="32286-166">双击**Sts.Outbox.Location**。</span><span class="sxs-lookup"><span data-stu-id="32286-166">Double-click **Sts.Outbox.Location**.</span></span>  
  
4.  <span data-ttu-id="32286-167">在接收位置属性对话框中，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="32286-167">In the Receive Location Properties dialog box, click **Configure**.</span></span>  
  
5.  <span data-ttu-id="32286-168">在传输属性对话框中中的值替换为**SharePointSite URL**与本地化的等效项。</span><span class="sxs-lookup"><span data-stu-id="32286-168">In the Transport Properties dialog box, replace the value for **SharePointSite URL** with the localized equivalent.</span></span>  
  
6.  <span data-ttu-id="32286-169">单击**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="32286-169">Click **OK**, and then click **OK**.</span></span>  
  
## <a name="removing-a-role-while-it-is-processing-a-message-results-in-incomplete-removal-of-documents-and-artifacts"></a><span data-ttu-id="32286-170">删除角色时它正在处理的文档和项目中完全删除的消息结果</span><span class="sxs-lookup"><span data-stu-id="32286-170">Removing a role while it is processing a message results in incomplete removal of documents and artifacts</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-171">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-171">Symptom</span></span>  
 <span data-ttu-id="32286-172">当你在配置文件的 Web 客户端中删除角色时，发布对话框中，该值指示将删除所有文档和与角色关联的项目。</span><span class="sxs-lookup"><span data-stu-id="32286-172">When you remove a role in the Profile Web Client, a dialog box is posted indicating that all documents and artifacts associated with the role will be removed.</span></span> <span data-ttu-id="32286-173">但是，从在 A4SWIFT 管理控制台中，部门不删除角色和角色的文档文件夹 （收件箱和发送的项目） 不会从 MRSR 中删除。</span><span class="sxs-lookup"><span data-stu-id="32286-173">However, the role is not removed from the department in the A4SWIFT Management Console, and the role's document folders (Inbox and Sent Items) are not removed from MRSR.</span></span> <span data-ttu-id="32286-174">删除方、 发送端口和协议与角色关联，并且未部署角色的配置文件。</span><span class="sxs-lookup"><span data-stu-id="32286-174">The party, send port, and agreement associated with the role are removed, and the profile of the role is undeployed.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="32286-175">可能的原因</span><span class="sxs-lookup"><span data-stu-id="32286-175">Possible Cause</span></span>  
 <span data-ttu-id="32286-176">一条消息仍然在角色的收件箱中 MRSR，并且消息是在中打开其[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。</span><span class="sxs-lookup"><span data-stu-id="32286-176">A message is still in the role's inbox in MRSR, and the message is open in its [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-177">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-177">Solution</span></span>  
 <span data-ttu-id="32286-178">将消息从 MRSR 站点收件箱，手动删除然后再删除与已删除的角色相关联的文档库。</span><span class="sxs-lookup"><span data-stu-id="32286-178">Manually delete the message from the MRSR site inbox, and then delete the document library that is associated with the role that you were removing.</span></span> <span data-ttu-id="32286-179">关闭表单并再次删除角色。</span><span class="sxs-lookup"><span data-stu-id="32286-179">Close the form and remove the role again.</span></span>  
  
## <a name="message-processing-fails-as-a-result-of-an-error-in-the-bic-master-policy"></a><span data-ttu-id="32286-180">由于 BIC Master 策略中的错误的消息处理失败</span><span class="sxs-lookup"><span data-stu-id="32286-180">Message processing fails as a result of an error in the BIC Master Policy</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-181">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-181">Symptom</span></span>  
 <span data-ttu-id="32286-182">当提交邮件以进行处理时，你将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="32286-182">When you submit a message for processing, you receive the following error:</span></span>  
  
 <span data-ttu-id="32286-183">"执行 BicMasterPolicy 时发生错误。</span><span class="sxs-lookup"><span data-stu-id="32286-183">"An error occurred while executing the BicMasterPolicy.</span></span> <span data-ttu-id="32286-184">检查有效值的策略。"</span><span class="sxs-lookup"><span data-stu-id="32286-184">Check the policy for valid values."</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="32286-185">可能的原因</span><span class="sxs-lookup"><span data-stu-id="32286-185">Possible Cause</span></span>  
 <span data-ttu-id="32286-186">SQL Server 名称、 BIC 数据库名称和 BIC_Master_Policy.xml 文件中的集成的安全性值*\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Base 策略包含用双引号括起来。</span><span class="sxs-lookup"><span data-stu-id="32286-186">The SQL Server name, BIC database name, and integrated security value in the BIC_Master_Policy.xml file in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies are contained in double quotes.</span></span> <span data-ttu-id="32286-187">若要启用 BIC 验证，则输入这些字符串默认 BIC_Master_Policy.xml 文件中所述[启用验证 Bank 标识符代码的](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="32286-187">To enable BIC validation, you enter these strings in the default BIC_Master_Policy.xml file as described in [Enabling Validation of Bank Identifier Codes](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md).</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-188">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-188">Solution</span></span>  
 <span data-ttu-id="32286-189">若要修复 BIC 主策略，请继续执行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="32286-189">To repair the BIC master policy, proceed as follows:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32286-190">有关部署 BIC 主策略的详细信息，请参阅[部署 BRE 规则](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="32286-190">For more information about deploying the BIC master policy, see [Deploying BRE Rules](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md).</span></span>  
  
1.  <span data-ttu-id="32286-191">业务规则编辑器，在取消部署的 BIC_Master_Policy，版本 1.0，然后再删除 BIC_Master_Policy。</span><span class="sxs-lookup"><span data-stu-id="32286-191">In Business Rule Composer, undeploy Version 1.0 of the BIC_Master_Policy, and then delete the BIC_Master_Policy.</span></span>  
  
2.  <span data-ttu-id="32286-192">在文本编辑器中，（如记事本） 打开中的 BIC_Master_Policy.xml *\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT\<版本\>消息 Pack\SWIFTMessages\A4SWIFT SRG\<版本\>\Base 策略。</span><span class="sxs-lookup"><span data-stu-id="32286-192">In a text editor, such as Notepad, open BIC_Master_Policy.xml in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies.</span></span> <span data-ttu-id="32286-193">删除 SQL Server 名称两边添加双引号，BIC 数据库名称，并集成安全值。</span><span class="sxs-lookup"><span data-stu-id="32286-193">Remove the double quotes around the SQL Server name, BIC database name, and integrated security value.</span></span>  
  
3.  <span data-ttu-id="32286-194">在业务规则引擎的部署向导中，导入 BIC_Master_Policy.xml，，然后部署 BIC_Master_Policy.xml。</span><span class="sxs-lookup"><span data-stu-id="32286-194">In the Business Rules Engine Deployment Wizard, import BIC_Master_Policy.xml, and then deploy BIC_Master_Policy.xml.</span></span>  
  
4.  <span data-ttu-id="32286-195">在服务 MMC 中，重新启动规则引擎更新服务和 BizTalk 接收主机服务。</span><span class="sxs-lookup"><span data-stu-id="32286-195">In the Services MMC, restart the Rule Engine Update Service and the BizTalk Receive Host Service.</span></span>  
  
## <a name="a4swift-will-not-be-able-to-process-an-unparsed-message-without-proper-database-permissions"></a><span data-ttu-id="32286-196">A4SWIFT 将无法处理不正确的数据库权限的情况下一条未分析的消息</span><span class="sxs-lookup"><span data-stu-id="32286-196">A4SWIFT will not be able to process an unparsed message without proper database permissions</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-197">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-197">Symptom</span></span>  
 <span data-ttu-id="32286-198">当您删除一条消息，无法分析 A4SWIFT 时，A4SWIFT 将无法处理消息，但失败并且具有未捕获的异常。</span><span class="sxs-lookup"><span data-stu-id="32286-198">When you drop a message that A4SWIFT cannot parse, A4SWIFT is unable to process the message, but fails with an uncaught exception.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="32286-199">可能的原因</span><span class="sxs-lookup"><span data-stu-id="32286-199">Possible Cause</span></span>  
 <span data-ttu-id="32286-200">没有数据库权限问题。</span><span class="sxs-lookup"><span data-stu-id="32286-200">There is a database permission issue.</span></span> <span data-ttu-id="32286-201">A4SWIFT 管理员和 A4SWIFT 用户组中不包括 BizTalk 服务，它们的默认值是 HostSvc 的登录帐户。</span><span class="sxs-lookup"><span data-stu-id="32286-201">The Log On account for the BizTalk service, which by default is HostSvc, is not included in the A4SWIFT Administrators and A4SWIFT Users groups.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-202">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-202">Solution</span></span>  
 <span data-ttu-id="32286-203">将 BizTalk 服务的登录帐户添加到 A4SWIFT 管理员和 A4SWIFT 用户组。</span><span class="sxs-lookup"><span data-stu-id="32286-203">Add the Log On account for the BizTalk service to the A4SWIFT Administrators and A4SWIFT Users groups.</span></span>  
  
## <a name="a-timeout-of-the-infopath-repair-form-can-result-in-two-copies-of-a-message-in-different-stages-of-the-repair-workflow"></a><span data-ttu-id="32286-204">InfoPath 修复窗体的超时可能在修复工作流的不同阶段导致一条消息的两个副本</span><span class="sxs-lookup"><span data-stu-id="32286-204">A timeout of the InfoPath repair form can result in two copies of a message in different stages of the repair workflow</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-205">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-205">Symptom</span></span>  
 <span data-ttu-id="32286-206">当你提交的 InfoPath 窗体中的消息 （任何工作流阶段），如果在提交表单中没有错误时，该错误可能导致在消息的两个副本。</span><span class="sxs-lookup"><span data-stu-id="32286-206">When you submit a message from an InfoPath form (for any workflow stage), if there is an error in submission of the form, the error could result in two copies of message.</span></span> <span data-ttu-id="32286-207">一条消息仍在收件箱进行的当前阶段，并在工作流中的下一步角色的收件箱中的其他邮件是。</span><span class="sxs-lookup"><span data-stu-id="32286-207">One message is still in the inbox for the current stages, and the other message is in the inbox for the next role in the workflow.</span></span> <span data-ttu-id="32286-208">尝试处理这些消息将导致以下：</span><span class="sxs-lookup"><span data-stu-id="32286-208">Attempting to process these messages will result in the following:</span></span>  
  
-   <span data-ttu-id="32286-209">如果提交来自工作流的下一步角色的收件箱的消息，消息将继续在工作流。</span><span class="sxs-lookup"><span data-stu-id="32286-209">If you submit the message from the inbox for the next role of the workflow, the message will continue through the workflow.</span></span>  
  
-   <span data-ttu-id="32286-210">如果你提交来自收件箱的消息的当前阶段已完成的处理消息的下一阶段的收件箱从中提交后，从当前的收件箱提交的邮件将被挂起用路由的失败。</span><span class="sxs-lookup"><span data-stu-id="32286-210">If you submit the message from the inbox for the current stage after the message submitted from the inbox of the next stage has completed processing, the message submitted from the current inbox will be suspended with a routing failure.</span></span>  
  
-   <span data-ttu-id="32286-211">如果你提交收件箱中的消息的当前阶段完成下一阶段的收件箱从提交的邮件之前处理消息的当前阶段提交从收件箱的收件箱返回适用于该阶段中，和中，你将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="32286-211">If you submit the message in the inbox for the current stage before the message submitted from the inbox of the next stage has completed processing, the message submitted from the inbox for the current stage will be returned to the inbox for that stage, and you will receive the following error:</span></span>  
    <span data-ttu-id="32286-212">"重置由于工作流： 消息已被篡改或对于这一阶段用户无效。"</span><span class="sxs-lookup"><span data-stu-id="32286-212">"Resetting workflow due to: either the message was tampered with or the user is invalid for this stage."</span></span>  
    <span data-ttu-id="32286-213">此后，如果下一个阶段，提交来自收件箱的消息的工作流将还重置。</span><span class="sxs-lookup"><span data-stu-id="32286-213">After this, if you submit the message from the inbox for the next stage, the workflow for it will also be reset.</span></span> <span data-ttu-id="32286-214">它将为返回的收件箱对于当前阶段，你将收到以上错误。</span><span class="sxs-lookup"><span data-stu-id="32286-214">It will be returned to the inbox for the current stage and you will receive the above error.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="32286-215">可能的原因</span><span class="sxs-lookup"><span data-stu-id="32286-215">Possible Cause</span></span>  
 <span data-ttu-id="32286-216">InfoPath 表单提交之后发送给 BizTalk Server 通过 Microsoft Windows Sharepoint Services 和会执行验证的自定义 Web 服务的消息。</span><span class="sxs-lookup"><span data-stu-id="32286-216">The InfoPath form has submitted the message to BizTalk Server via Microsoft Windows Sharepoint Services and a custom Web service that performs validations.</span></span> <span data-ttu-id="32286-217">提交一条消息中多个步骤完成，因为 Windows Sharepoint Services 不是事务性的可能不是事务性的这些步骤。</span><span class="sxs-lookup"><span data-stu-id="32286-217">Submitting a message is accomplished in multiple steps and these steps are not transactional, because Windows Sharepoint Services is not transactional.</span></span> <span data-ttu-id="32286-218">为了满足此限制，MRSR 业务流程具有内置的恢复逻辑来检测，并从因消息提交的错误中恢复。</span><span class="sxs-lookup"><span data-stu-id="32286-218">To accommodate this limitation, the MRSR orchestrations have built in recovery logic to detect and recover from errors arising from the message submission.</span></span> <span data-ttu-id="32286-219">MRSR 业务流程始终能够阻止发送到 SWIFT 重复消息。</span><span class="sxs-lookup"><span data-stu-id="32286-219">The MRSR orchestrations always prevent duplicate messages being sent to SWIFT.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-220">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-220">Solution</span></span>  
 <span data-ttu-id="32286-221">如果发生这种情况，应选择进一步沿工作流中的消息，并尝试处理处于早期阶段，工作流的其他消息之前完成其工作流。</span><span class="sxs-lookup"><span data-stu-id="32286-221">If this occurs, you should pick the message that is further along in the workflow and complete its workflow before attempting to process the other messages that are in the earlier stages of the workflow.</span></span> <span data-ttu-id="32286-222">沿工作流中的消息完成处理之后，您可以根据你的释放的第二个消息 （这与路由失败，已挂起）。</span><span class="sxs-lookup"><span data-stu-id="32286-222">After the message that is further along in the workflow has completed processing, you can dispose of the second message (which was suspended with a routing failure) as you see fit.</span></span>  
  
 <span data-ttu-id="32286-223">如果的消息进一步沿工作流中未完成处理处理第二条消息之前，您应再次修复进一步沿修复 InfoPath 窗体中工作流中的消息，然后将其提交。</span><span class="sxs-lookup"><span data-stu-id="32286-223">If the message that is further along in the workflow did not complete processing before you processed the second message, you should once again repair the message that is further along in the workflow in the repair InfoPath form, and then submit it.</span></span> <span data-ttu-id="32286-224">允许其完成处理，然后提交第二条消息。</span><span class="sxs-lookup"><span data-stu-id="32286-224">Allow it to complete processing, and then submit the second message.</span></span> <span data-ttu-id="32286-225">第二条消息已被挂起后，释放类型。</span><span class="sxs-lookup"><span data-stu-id="32286-225">After the second message has been suspended, dispose of it.</span></span>  
  
## <a name="a-new-submission-with-no-verify-stage-will-result-in-a-suspended-message"></a><span data-ttu-id="32286-226">没有验证阶段新提交将导致将挂起的消息</span><span class="sxs-lookup"><span data-stu-id="32286-226">A new submission with no verify stage will result in a suspended message</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-227">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-227">Symptom</span></span>  
 <span data-ttu-id="32286-228">当提交具有不验证阶段的工作流中的新消息时，会挂起消息。</span><span class="sxs-lookup"><span data-stu-id="32286-228">When you submit a new message in a workflow that has no verify stage, the message is suspended.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="32286-229">可能的原因</span><span class="sxs-lookup"><span data-stu-id="32286-229">Possible Cause</span></span>  
 <span data-ttu-id="32286-230">请验证阶段缺乏会导致将挂起的消息如果 A4SWIFT_MRSRLastStage 未设置为创建。</span><span class="sxs-lookup"><span data-stu-id="32286-230">The lack of a verify stage results in a suspended message if A4SWIFT_MRSRLastStage is not set to Create.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-231">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-231">Solution</span></span>  
 <span data-ttu-id="32286-232">使用订阅 A4SWIFT_MRSRLastStage = = 创建，以确保正确路由消息。</span><span class="sxs-lookup"><span data-stu-id="32286-232">Use a subscription of A4SWIFT_MRSRLastStage == Create to ensure that the message is routed properly.</span></span>  
  
## <a name="validation-of-message-results-a-parse-error-in-the-infopath-form-task-pane"></a><span data-ttu-id="32286-233">消息验证结果"分析错误"中的 InfoPath 窗体任务窗格</span><span class="sxs-lookup"><span data-stu-id="32286-233">Validation of message results a "parse error" in the InfoPath form task pane</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-234">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-234">Symptom</span></span>  
 <span data-ttu-id="32286-235">验证窗体任务窗格将显示"分析错误"没有任何说明 InfoPath 中的消息按钮。</span><span class="sxs-lookup"><span data-stu-id="32286-235">Validate Message button in the InfoPath form task pane shows “parse error” without any description.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-236">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-236">Solution</span></span>  
 <span data-ttu-id="32286-237">重新启动 MRSR web 服务或者执行 iisreset。</span><span class="sxs-lookup"><span data-stu-id="32286-237">Restart the MRSR web service or do iisreset.</span></span>  
  
## <a name="publishing-an-infopath-form-results-an-authorization-error"></a><span data-ttu-id="32286-238">InfoPath 窗体发布结果授权错误</span><span class="sxs-lookup"><span data-stu-id="32286-238">Publishing an InfoPath form results an authorization error</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-239">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-239">Symptom</span></span>  
 <span data-ttu-id="32286-240">InfoPath 窗体发布给出授权错误。</span><span class="sxs-lookup"><span data-stu-id="32286-240">Publishing an InfoPath form gives authorization error.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-241">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-241">Solution</span></span>  
 <span data-ttu-id="32286-242">用 MRSR 站点 URL 中的 localhost 替换计算机名称。</span><span class="sxs-lookup"><span data-stu-id="32286-242">Replace machine name by localhost in the MRSR site URL.</span></span>  
  
## <a name="infopath-form-task-pane-shows-html-source-code"></a><span data-ttu-id="32286-243">InfoPath 窗体任务窗格中显示的 HTML 源代码</span><span class="sxs-lookup"><span data-stu-id="32286-243">InfoPath form task pane shows HTML source code</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-244">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-244">Symptom</span></span>  
 <span data-ttu-id="32286-245">InfoPath 窗体任务窗格将显示而不是 Web 控件的 HTML 源代码。</span><span class="sxs-lookup"><span data-stu-id="32286-245">InfoPath form task pane shows HTML source code instead of Web controls.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-246">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-246">Solution</span></span>  
 <span data-ttu-id="32286-247">转到**工具**-> **安全选项卡** -> **Internet 区域**，并启用**根据内容而打开的文件不能对扩展**在杂项下。</span><span class="sxs-lookup"><span data-stu-id="32286-247">Go to **Tools**-> **Security Tab** -> **Internet Zone**, and enable **Open file based on content not on extension** under Miscellaneous.</span></span>  
  
## <a name="profile-web-client-website-results-an-authentication-error"></a><span data-ttu-id="32286-248">配置文件 Web 客户端网站结果身份验证错误</span><span class="sxs-lookup"><span data-stu-id="32286-248">Profile Web Client website results an Authentication error</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="32286-249">故障现象</span><span class="sxs-lookup"><span data-stu-id="32286-249">Symptom</span></span>  
 <span data-ttu-id="32286-250">配置文件 Web 客户端网站显示身份验证错误。</span><span class="sxs-lookup"><span data-stu-id="32286-250">Profile Web Client website displays Authentication error.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="32286-251">解决方案</span><span class="sxs-lookup"><span data-stu-id="32286-251">Solution</span></span>  
 <span data-ttu-id="32286-252">运行**BTSharePointAdapterWSAppPool**和**DefaultAppPoolApplication** -> 和在 Internet 信息 Services(IIS) 池 administrator 帐户下。</span><span class="sxs-lookup"><span data-stu-id="32286-252">Run the **BTSharePointAdapterWSAppPool** and **DefaultAppPoolApplication** -> and pool in Internet Information Services(IIS) under the administrator account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32286-253">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32286-253">See Also</span></span>  
 [<span data-ttu-id="32286-254">疑难解答：问题和解决方法</span><span class="sxs-lookup"><span data-stu-id="32286-254">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)