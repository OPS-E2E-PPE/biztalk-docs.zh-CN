---
title: 已知 Issues5 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, known issues
- BizTalk Accelerator for SWIFT, known issues
- known issues
ms.assetid: 0f1ec7dd-9e74-479a-bdc8-ab9c4397c992
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f20477988a3a4f60522a7c05270e72ac525dead
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377310"
---
# <a name="known-issues"></a><span data-ttu-id="84a1d-102">已知问题</span><span class="sxs-lookup"><span data-stu-id="84a1d-102">Known Issues</span></span>
<span data-ttu-id="84a1d-103">本部分包含可帮助你避免与 Microsoft 的错误的有用信息[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="84a1d-103">This section contains useful information that may help you avoid errors with Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="84a1d-104">已知的问题分为以下几个方面：</span><span class="sxs-lookup"><span data-stu-id="84a1d-104">The known issues are grouped into the following areas:</span></span>  
  
## <a name="message-repair-and-new-submission"></a><span data-ttu-id="84a1d-105">消息修复和新提交</span><span class="sxs-lookup"><span data-stu-id="84a1d-105">Message Repair and New Submission</span></span>

#### <a name="printing-of-a-repair-document-is-recorded-in-the-history-log-even-if-canceled"></a><span data-ttu-id="84a1d-106">即使已取消，历史记录日志中记录的修复文档打印</span><span class="sxs-lookup"><span data-stu-id="84a1d-106">Printing of a repair document is recorded in the history log even if canceled</span></span>  
 <span data-ttu-id="84a1d-107">如果你运行修复收件箱中的文档打印命令，然后取消打印打印仍然被进入历史记录日志。</span><span class="sxs-lookup"><span data-stu-id="84a1d-107">If you run the Print command for a document in the Repair Inbox, and then cancel the printing, the printing is still entered into the history log.</span></span> <span data-ttu-id="84a1d-108">发生这种情况是当您打开要在中修复的文档时其[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，单击文件菜单中，打印命令，然后单击打印对话框中的取消。</span><span class="sxs-lookup"><span data-stu-id="84a1d-108">This occurs when you open the document to be repaired in its [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, click the Print command on the File menu, and then click Cancel in the Print dialog box.</span></span> <span data-ttu-id="84a1d-109">历史记录日志中的条目，则应将其忽略。</span><span class="sxs-lookup"><span data-stu-id="84a1d-109">You should ignore the entry in the history log.</span></span>  
  
#### <a name="a-duplicate-signature-can-cause-an-xlangs-error-message"></a><span data-ttu-id="84a1d-110">重复的签名可能会导致 XLANG/s 错误消息</span><span class="sxs-lookup"><span data-stu-id="84a1d-110">A duplicate signature can cause an XLANG/s error message</span></span>  
 <span data-ttu-id="84a1d-111">当一个验证程序使用相同的证书作为 repairer[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]挂起消息，并指示不允许重复的签名对错误消息中。</span><span class="sxs-lookup"><span data-stu-id="84a1d-111">When a verifier uses the same certificate as a repairer, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] suspends the message and indicates in an error message that duplicate signatures are not allowed.</span></span> <span data-ttu-id="84a1d-112">但是，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]还会生成的事件源为 XLANG/s，该值指示已挂起的 XLANG/s 服务的另一个错误消息。</span><span class="sxs-lookup"><span data-stu-id="84a1d-112">However, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] also generates another error message with an event source of XLANG/s, indicating that the XLANG/s service has been suspended.</span></span> <span data-ttu-id="84a1d-113">可以忽略此消息。</span><span class="sxs-lookup"><span data-stu-id="84a1d-113">You can ignore this message.</span></span>  
  
#### <a name="message-size-can-affect-repair-performance"></a><span data-ttu-id="84a1d-114">消息大小可能会影响修复性能</span><span class="sxs-lookup"><span data-stu-id="84a1d-114">Message size can affect repair performance</span></span>  
 <span data-ttu-id="84a1d-115">如果你尝试修复非常大的 XML 文件，打开中的 XML 文件时，系统性能会大大降低[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]消息类型的窗体。</span><span class="sxs-lookup"><span data-stu-id="84a1d-115">If you attempt to repair an unusually large XML file, system performance can significantly degrade when you open the XML file in the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form for the message type.</span></span> <span data-ttu-id="84a1d-116">内存消耗可能会增加，可能会降低 CPU 占用率，进程可能会因出现错误，指示没有足够的存储可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="84a1d-116">Memory consumption may increase, CPU consumption may decrease, and the process may fail with an error indicating that not enough storage was available to complete the operation.</span></span>  
  
#### <a name="the-last-signature-used-to-sign-a-message-successfully-will-be-authenticated-by-authenticate-signatures"></a><span data-ttu-id="84a1d-117">最后一个用于成功对消息进行签名的签名将通过身份验证的签名进行身份验证</span><span class="sxs-lookup"><span data-stu-id="84a1d-117">The last signature used to sign a message successfully will be authenticated by Authenticate Signatures</span></span>  
 <span data-ttu-id="84a1d-118">单击进行身份验证签名按钮[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中只是如果你已登录窗体的阶段验证的签名。</span><span class="sxs-lookup"><span data-stu-id="84a1d-118">Clicking the Authenticate Signatures button on an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form validates the signature for the stage that you are in only if you have already signed the form.</span></span> <span data-ttu-id="84a1d-119">否则，它验证的签名为上一阶段，如果有的话，并将发布以下错误：</span><span class="sxs-lookup"><span data-stu-id="84a1d-119">Otherwise, it validates the signature for the previous stage, if there was one, and posts the following error:</span></span>  
  
 <span data-ttu-id="84a1d-120">签名用户未正确配置为部门 < department_name > 中 < stage_name > 角色。</span><span class="sxs-lookup"><span data-stu-id="84a1d-120">The signing user is not correctly configured for the <stage_name> role in department <department_name>.</span></span>  
  
 <span data-ttu-id="84a1d-121">例如，假设您验证阶段后立即处于批准阶段。</span><span class="sxs-lookup"><span data-stu-id="84a1d-121">For example, suppose that you are in an approve stage immediately after a verify stage.</span></span> <span data-ttu-id="84a1d-122">如果尚未登录窗体作为审批者，并单击进行身份验证签名[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]验证人使用，不是审批者的签名的签名进行身份验证并发布之前的错误。</span><span class="sxs-lookup"><span data-stu-id="84a1d-122">If you have not yet signed the form as the approver, and you click Authenticate Signatures, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] authenticates the signature that the verifier used, not your approver's signature, and posts the preceding error.</span></span>  

#### <a name="a4swift-cleanup-tool-doesnt-delete-templates"></a><span data-ttu-id="84a1d-123">A4SWIFT 清理工具不会删除模板</span><span class="sxs-lookup"><span data-stu-id="84a1d-123">A4SWIFT cleanup tool doesn’t delete templates</span></span>  
 <span data-ttu-id="84a1d-124">A4SWIFT 清理工具不会执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="84a1d-124">The A4SWIFT cleanup tool doesn’t performs the following operations:</span></span>  
  
-   <span data-ttu-id="84a1d-125">从 MRSR 站点中删除所有 MT 模板</span><span class="sxs-lookup"><span data-stu-id="84a1d-125">Removes all MT templates from MRSR site</span></span>  
  
-   <span data-ttu-id="84a1d-126">从 MRSR 站点中删除所有协议和合作伙伴配置文件</span><span class="sxs-lookup"><span data-stu-id="84a1d-126">Removes all agreements and partner profiles from MRSR site</span></span>  
  
-   <span data-ttu-id="84a1d-127">删除所有用户、 角色和部门</span><span class="sxs-lookup"><span data-stu-id="84a1d-127">Removes all users, roles, and departments</span></span>  
  
-   <span data-ttu-id="84a1d-128">注销 A4SWIFT BizTalk Server 从 MRSR 站点</span><span class="sxs-lookup"><span data-stu-id="84a1d-128">Unregisters the A4SWIFT BizTalk Server from the MRSR site</span></span>  
  
#### <a name="the-a4swiftmrsrdepartment-property-is-set-to-an-empty-string-for-a-message-that-did-not-parse"></a><span data-ttu-id="84a1d-129">A4SWIFT_MRSRDepartment 属性设置为空字符串作为一条消息，未进行分析。</span><span class="sxs-lookup"><span data-stu-id="84a1d-129">The A4SWIFT_MRSRDepartment property is set to an empty string for a message that did not parse</span></span>  
 <span data-ttu-id="84a1d-130">如果消息修复业务流程将路由到 MessageBox 已修复未分析的消息，它会设置[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_MRSRDepartment 属性为空字符串，并将其升级。</span><span class="sxs-lookup"><span data-stu-id="84a1d-130">When the message-repair orchestration routes to the MessageBox an unparsed message that has been fixed, it will set the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_MRSRDepartment property to an empty string and promote it.</span></span> <span data-ttu-id="84a1d-131">发送端口不能订阅此属性。</span><span class="sxs-lookup"><span data-stu-id="84a1d-131">A send port will not be able to subscribe on this property.</span></span>  
  
#### <a name="cannot-save-a-department-if-the-sso-service-has-been-stopped"></a><span data-ttu-id="84a1d-132">如果 SSO 服务已停止，无法保存部门</span><span class="sxs-lookup"><span data-stu-id="84a1d-132">Cannot save a department if the SSO service has been stopped</span></span>  
 <span data-ttu-id="84a1d-133">主 SSO 服务器如果尝试添加系，SSO 服务停止时，你都将收到错误，指示\<machinename\>失败。</span><span class="sxs-lookup"><span data-stu-id="84a1d-133">If you try to add a department when the SSO service is stopped, you will receive an error indicating that the Primary SSO server \<machinename\> failed.</span></span> <span data-ttu-id="84a1d-134">检查配置了 SSO 以及 SSO 服务正在该服务器上。</span><span class="sxs-lookup"><span data-stu-id="84a1d-134">Check that SSO is configured and that the SSO service is running on that server.</span></span>  
  
#### <a name="a-department-name-must-not-contain-the-character-"></a><span data-ttu-id="84a1d-135">部门名称不得包含字符"~"</span><span class="sxs-lookup"><span data-stu-id="84a1d-135">A department name must not contain the character "~"</span></span>  
 <span data-ttu-id="84a1d-136">部门名称包含字符"~"将导致 A4SWIFT 数据库出现问题。</span><span class="sxs-lookup"><span data-stu-id="84a1d-136">A department name that contains the character "~" will cause issues with the A4SWIFT database.</span></span>  
  
#### <a name="signing-infopath-forms"></a><span data-ttu-id="84a1d-137">签名 Infopath 窗体</span><span class="sxs-lookup"><span data-stu-id="84a1d-137">Signing Infopath forms</span></span>  
 <span data-ttu-id="84a1d-138">对签名的 InfoPath 窗体需要手动完成。</span><span class="sxs-lookup"><span data-stu-id="84a1d-138">The signing of InfoPath forms needs to be done manually.</span></span>  
  
## <a name="security"></a><span data-ttu-id="84a1d-139">安全性</span><span class="sxs-lookup"><span data-stu-id="84a1d-139">Security</span></span>

#### <a name="mixing-trusted-and-untrusted-hosts-can-enable-spoofing"></a><span data-ttu-id="84a1d-140">混合使用受信任和不受信任主机可以启用欺骗</span><span class="sxs-lookup"><span data-stu-id="84a1d-140">Mixing trusted and untrusted hosts can enable spoofing</span></span>  

 <span data-ttu-id="84a1d-141">可能从其他不受信任的 SWIFT 绑定消息欺骗[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="84a1d-141">It may be possible to spoof SWIFT-bound messages from other non-trusted [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host applications.</span></span> <span data-ttu-id="84a1d-142">这是仅一个问题，在混合信任模式下运行时 (受信任的主机和不受信任的主机中运行时，应用程序相同[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]组)。</span><span class="sxs-lookup"><span data-stu-id="84a1d-142">This is only a problem when running in mixed-trust mode (when trusted hosts and untrusted hosts run applications in the same [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] group).</span></span> <span data-ttu-id="84a1d-143">通过使用参与方解析管道组件来标识 SWIFT 绑定消息的源，可以降低此风险。</span><span class="sxs-lookup"><span data-stu-id="84a1d-143">You can mitigate this risk by using party-resolution pipeline components to identify the source of the SWIFT-bound message.</span></span> <span data-ttu-id="84a1d-144">运行在完全受信任环境中或对于大多数使用方案时，这是不必要的。</span><span class="sxs-lookup"><span data-stu-id="84a1d-144">This is not necessary when running in a fully trusted environment or for the majority of usage scenarios.</span></span> <span data-ttu-id="84a1d-145">应遵循[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]混合时构建安全的应用程序的指导原则受信任和不受信任的主机。</span><span class="sxs-lookup"><span data-stu-id="84a1d-145">You should follow the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] guidelines for building secure applications when mixing trusted and untrusted hosts.</span></span> 
 
## <a name="miscellaneous"></a><span data-ttu-id="84a1d-146">杂项</span><span class="sxs-lookup"><span data-stu-id="84a1d-146">Miscellaneous</span></span>

#### <a name="the-cacheentries-setting-may-be-reset-by-a-setup-program-affecting-performance"></a><span data-ttu-id="84a1d-147">CacheEntries 设置可能会重置被安装程序，会影响性能</span><span class="sxs-lookup"><span data-stu-id="84a1d-147">The CacheEntries setting may be reset by a Setup program, affecting performance</span></span>  
 <span data-ttu-id="84a1d-148">CacheEntries 注册表项确定缓存的业务规则引擎更新服务的规则集的最大数目。</span><span class="sxs-lookup"><span data-stu-id="84a1d-148">The CacheEntries registry key determines the maximum number of rulesets cached by the Business Rule Engine Update service.</span></span> <span data-ttu-id="84a1d-149">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装程序将 CacheEntries 设为 32，默认情况下。</span><span class="sxs-lookup"><span data-stu-id="84a1d-149">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Setup program sets CacheEntries to 32 by default.</span></span> <span data-ttu-id="84a1d-150">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序更改 HKEY_LOCAL_MACHINE\SOFTWARE\\Microsoft \BusinessRules\3.0\CacheEntries 为 512 以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="84a1d-150">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Setup program changes HKEY_LOCAL_MACHINE\SOFTWARE\\Microsoft \BusinessRules\3.0\CacheEntries to 512 for optimum performance.</span></span> <span data-ttu-id="84a1d-151">但是，在某些情况下，CacheEntries 可能会自动重置。</span><span class="sxs-lookup"><span data-stu-id="84a1d-151">However, in certain circumstances, CacheEntries may be reset automatically.</span></span> <span data-ttu-id="84a1d-152">这可能会影响系统性能。</span><span class="sxs-lookup"><span data-stu-id="84a1d-152">This may affect system performance.</span></span>  
  
 <span data-ttu-id="84a1d-153">规则引擎更新可能会更改 CacheEntries 从 512 到 32 个。</span><span class="sxs-lookup"><span data-stu-id="84a1d-153">Rule Engine updates may change CacheEntries from 512 to 32.</span></span> <span data-ttu-id="84a1d-154">安装规则引擎更新后，手动重置 CacheEntries 为 512，如有必要。</span><span class="sxs-lookup"><span data-stu-id="84a1d-154">After installing a Rule Engine update, manually reset CacheEntries to 512, if necessary.</span></span>  
  
 <span data-ttu-id="84a1d-155">即使[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序将 CacheEntries 32 从设置为 512，卸载[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不重置 CacheEntries 从 512 到 32 个。</span><span class="sxs-lookup"><span data-stu-id="84a1d-155">Even though the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Setup program sets CacheEntries from 32 to 512, uninstalling [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] does not reset CacheEntries from 512 to 32.</span></span>  
  
 <span data-ttu-id="84a1d-156">有关详细信息，请参阅 BizTalk Server 帮助中的"规则引擎配置和优化参数"主题。</span><span class="sxs-lookup"><span data-stu-id="84a1d-156">For more information, see the "Rule Engine Configuration and Tuning Parameters" topic in BizTalk Server Help.</span></span>  
  
#### <a name="building-a-pipeline-project-may-result-in-a-large-number-of-warnings"></a><span data-ttu-id="84a1d-157">生成管道项目可能会导致大量警告</span><span class="sxs-lookup"><span data-stu-id="84a1d-157">Building a pipeline project may result in a large number of warnings</span></span>  
 <span data-ttu-id="84a1d-158">如果您将 SWIFT 汇编程序添加到发送管道或接收管道，到 SWIFT 反汇编程序，然后生成包含这些管道的管道项目可能会收到一系列与管道组件相关的警告。</span><span class="sxs-lookup"><span data-stu-id="84a1d-158">When you add the SWIFT assembler to a send pipeline, or the SWIFT disassembler to a receive pipeline, and then build the pipeline project containing those pipelines, you may receive a series of warnings related to the pipeline components.</span></span> <span data-ttu-id="84a1d-159">这些警告指示 Visual Studio 找不到依赖项。</span><span class="sxs-lookup"><span data-stu-id="84a1d-159">These warnings indicate that Visual Studio could not find dependencies.</span></span> <span data-ttu-id="84a1d-160">您可以更正导致这些警告，如下所示更改 SWIFTAsm 或 SWIFTDasm 程序集引用文件夹中的复制本地属性的条件：</span><span class="sxs-lookup"><span data-stu-id="84a1d-160">You can correct the condition leading to these warnings by changing the Copy Local property of the SWIFTAsm or SWIFTDasm assembly in the reference folder, as follows:</span></span>  
  
1.  <span data-ttu-id="84a1d-161">在解决方案资源管理器的 Visual Studio 中，展开你的管道项目，然后展开**引用**节点。</span><span class="sxs-lookup"><span data-stu-id="84a1d-161">In Solution Explorer of Visual Studio, expand your pipeline project, and then expand the **References** node.</span></span>  
  
2.  <span data-ttu-id="84a1d-162">在引用节点下选择**SWIFTAsm**程序集和/或**SWIFTDasm**程序集。</span><span class="sxs-lookup"><span data-stu-id="84a1d-162">Under the References node, select the **SWIFTAsm** assembly and/or the **SWIFTDasm** assembly.</span></span>  
  
3.  <span data-ttu-id="84a1d-163">在属性窗格中的值更改**Copy Local**属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="84a1d-163">In the Properties pane, change the value for the **Copy Local** property to **False**.</span></span>  
  
4.  <span data-ttu-id="84a1d-164">右键单击管道项目，然后依次**生成**。</span><span class="sxs-lookup"><span data-stu-id="84a1d-164">Right-click your pipeline project, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84a1d-165">不应看到有关依赖关系找不到任何警告。</span><span class="sxs-lookup"><span data-stu-id="84a1d-165">You should not see any warnings about dependencies not being found.</span></span>   