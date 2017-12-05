---
title: "已知 Issues5 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, known issues
- BizTalk Accelerator for SWIFT, known issues
- known issues
ms.assetid: 0f1ec7dd-9e74-479a-bdc8-ab9c4397c992
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1356209f700fc7ceff220f4b0f8fcd3dd67db07
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="known-issues"></a><span data-ttu-id="a0db5-102">已知问题</span><span class="sxs-lookup"><span data-stu-id="a0db5-102">Known Issues</span></span>
<span data-ttu-id="a0db5-103">本部分包含有用信息来帮助你避免与错误[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a0db5-103">This section contains useful information that may help you avoid errors with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="a0db5-104">已知问题归为以下几个方面：</span><span class="sxs-lookup"><span data-stu-id="a0db5-104">The known issues are grouped into the following areas:</span></span>  
  
## <a name="message-repair-and-new-submission"></a><span data-ttu-id="a0db5-105">消息修复和新的提交</span><span class="sxs-lookup"><span data-stu-id="a0db5-105">Message Repair and New Submission</span></span>

#### <a name="printing-of-a-repair-document-is-recorded-in-the-history-log-even-if-canceled"></a><span data-ttu-id="a0db5-106">在历史记录日志中记录的修复文档的打印，即使取消</span><span class="sxs-lookup"><span data-stu-id="a0db5-106">Printing of a repair document is recorded in the history log even if canceled</span></span>  
 <span data-ttu-id="a0db5-107">如果运行修复收件箱中的文档打印命令，然后取消打印打印仍将输入到历史记录日志。</span><span class="sxs-lookup"><span data-stu-id="a0db5-107">If you run the Print command for a document in the Repair Inbox, and then cancel the printing, the printing is still entered into the history log.</span></span> <span data-ttu-id="a0db5-108">发生这种情况是当你打开文档后，在要修复其[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，单击文件菜单上的打印命令，然后单击打印对话框中的取消。</span><span class="sxs-lookup"><span data-stu-id="a0db5-108">This occurs when you open the document to be repaired in its [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, click the Print command on the File menu, and then click Cancel in the Print dialog box.</span></span> <span data-ttu-id="a0db5-109">历史记录日志中的条目，则应将其忽略。</span><span class="sxs-lookup"><span data-stu-id="a0db5-109">You should ignore the entry in the history log.</span></span>  
  
#### <a name="a-duplicate-signature-can-cause-an-xlangs-error-message"></a><span data-ttu-id="a0db5-110">重复的签名可能会导致 XLANG/s 错误消息</span><span class="sxs-lookup"><span data-stu-id="a0db5-110">A duplicate signature can cause an XLANG/s error message</span></span>  
 <span data-ttu-id="a0db5-111">当一个验证程序使用相同的证书作为 repairer[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]挂起消息，并指示不允许重复的签名对错误消息中。</span><span class="sxs-lookup"><span data-stu-id="a0db5-111">When a verifier uses the same certificate as a repairer, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] suspends the message and indicates in an error message that duplicate signatures are not allowed.</span></span> <span data-ttu-id="a0db5-112">但是，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]还会生成与 XLANG/s，XLANG/s 服务已被挂起，该值指示事件源的另一个错误消息。</span><span class="sxs-lookup"><span data-stu-id="a0db5-112">However, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] also generates another error message with an event source of XLANG/s, indicating that the XLANG/s service has been suspended.</span></span> <span data-ttu-id="a0db5-113">可以忽略此消息。</span><span class="sxs-lookup"><span data-stu-id="a0db5-113">You can ignore this message.</span></span>  
  
#### <a name="message-size-can-affect-repair-performance"></a><span data-ttu-id="a0db5-114">消息大小可能会影响修复性能</span><span class="sxs-lookup"><span data-stu-id="a0db5-114">Message size can affect repair performance</span></span>  
 <span data-ttu-id="a0db5-115">如果你尝试修复非常大的 XML 文件，当你打开中的 XML 文件时，系统性能会大大降低[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]消息类型窗体。</span><span class="sxs-lookup"><span data-stu-id="a0db5-115">If you attempt to repair an unusually large XML file, system performance can significantly degrade when you open the XML file in the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form for the message type.</span></span> <span data-ttu-id="a0db5-116">内存消耗可能会增加，可能会降低 CPU 占用率，进程可能会失败并出现错误，指示没有足够的存储已可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="a0db5-116">Memory consumption may increase, CPU consumption may decrease, and the process may fail with an error indicating that not enough storage was available to complete the operation.</span></span>  
  
#### <a name="the-last-signature-used-to-sign-a-message-successfully-will-be-authenticated-by-authenticate-signatures"></a><span data-ttu-id="a0db5-117">用于已成功对消息进行签名的最后一个签名将通过身份验证的签名进行身份验证</span><span class="sxs-lookup"><span data-stu-id="a0db5-117">The last signature used to sign a message successfully will be authenticated by Authenticate Signatures</span></span>  
 <span data-ttu-id="a0db5-118">单击身份验证的签名按钮[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中只是如果您已经注册该窗体阶段验证的签名。</span><span class="sxs-lookup"><span data-stu-id="a0db5-118">Clicking the Authenticate Signatures button on an [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form validates the signature for the stage that you are in only if you have already signed the form.</span></span> <span data-ttu-id="a0db5-119">否则，它验证的签名为上一阶段，如果没有一个，并发布以下错误：</span><span class="sxs-lookup"><span data-stu-id="a0db5-119">Otherwise, it validates the signature for the previous stage, if there was one, and posts the following error:</span></span>  
  
 <span data-ttu-id="a0db5-120">签名用户未正确配置为部门 < department_name > 中 < stage_name > 角色。</span><span class="sxs-lookup"><span data-stu-id="a0db5-120">The signing user is not correctly configured for the <stage_name> role in department <department_name>.</span></span>  
  
 <span data-ttu-id="a0db5-121">例如，假设你在验证阶段之后立即处于批准阶段。</span><span class="sxs-lookup"><span data-stu-id="a0db5-121">For example, suppose that you are in an approve stage immediately after a verify stage.</span></span> <span data-ttu-id="a0db5-122">如果尚未登录窗体为审批者，然后单击进行身份验证签名，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]进行身份验证验证程序使用，不是审批者的签名的签名并将前面的错误。</span><span class="sxs-lookup"><span data-stu-id="a0db5-122">If you have not yet signed the form as the approver, and you click Authenticate Signatures, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] authenticates the signature that the verifier used, not your approver's signature, and posts the preceding error.</span></span>  

#### <a name="a4swift-cleanup-tool-doesnt-delete-templates"></a><span data-ttu-id="a0db5-123">A4SWIFT 清理工具不会删除模板</span><span class="sxs-lookup"><span data-stu-id="a0db5-123">A4SWIFT cleanup tool doesn’t delete templates</span></span>  
 <span data-ttu-id="a0db5-124">A4SWIFT 清理工具不会执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a0db5-124">The A4SWIFT cleanup tool doesn’t performs the following operations:</span></span>  
  
-   <span data-ttu-id="a0db5-125">从 MRSR 站点中删除所有 MT 模板</span><span class="sxs-lookup"><span data-stu-id="a0db5-125">Removes all MT templates from MRSR site</span></span>  
  
-   <span data-ttu-id="a0db5-126">从 MRSR 站点中删除所有协议和合作伙伴配置文件</span><span class="sxs-lookup"><span data-stu-id="a0db5-126">Removes all agreements and partner profiles from MRSR site</span></span>  
  
-   <span data-ttu-id="a0db5-127">删除所有用户、 角色和部门</span><span class="sxs-lookup"><span data-stu-id="a0db5-127">Removes all users, roles, and departments</span></span>  
  
-   <span data-ttu-id="a0db5-128">从 MRSR 站点 A4SWIFT BizTalk Server 中注销</span><span class="sxs-lookup"><span data-stu-id="a0db5-128">Unregisters the A4SWIFT BizTalk Server from the MRSR site</span></span>  
  
#### <a name="the-a4swiftmrsrdepartment-property-is-set-to-an-empty-string-for-a-message-that-did-not-parse"></a><span data-ttu-id="a0db5-129">A4SWIFT_MRSRDepartment 属性设置为空字符串作为一条消息，未进行分析</span><span class="sxs-lookup"><span data-stu-id="a0db5-129">The A4SWIFT_MRSRDepartment property is set to an empty string for a message that did not parse</span></span>  
 <span data-ttu-id="a0db5-130">在消息修复业务流程将路由到 MessageBox 未分析的消息已修复，它会将设置[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_MRSRDepartment 属性设置为一个空字符串并将其升级。</span><span class="sxs-lookup"><span data-stu-id="a0db5-130">When the message-repair orchestration routes to the MessageBox an unparsed message that has been fixed, it will set the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_MRSRDepartment property to an empty string and promote it.</span></span> <span data-ttu-id="a0db5-131">发送端口将不能订阅此属性上。</span><span class="sxs-lookup"><span data-stu-id="a0db5-131">A send port will not be able to subscribe on this property.</span></span>  
  
#### <a name="cannot-save-a-department-if-the-sso-service-has-been-stopped"></a><span data-ttu-id="a0db5-132">如果 SSO 服务已停止，无法保存部门</span><span class="sxs-lookup"><span data-stu-id="a0db5-132">Cannot save a department if the SSO service has been stopped</span></span>  
 <span data-ttu-id="a0db5-133">主 SSO 服务器如果你尝试添加一个部门，SSO 服务停止时，你都将收到错误，该值指示\<machinename\>失败。</span><span class="sxs-lookup"><span data-stu-id="a0db5-133">If you try to add a department when the SSO service is stopped, you will receive an error indicating that the Primary SSO server \<machinename\> failed.</span></span> <span data-ttu-id="a0db5-134">请检查是否正确配置了 SSO 以及 SSO 服务是否正在该服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="a0db5-134">Check that SSO is configured and that the SSO service is running on that server.</span></span>  
  
#### <a name="a-department-name-must-not-contain-the-character-"></a><span data-ttu-id="a0db5-135">部门名称不能包含字符"~"</span><span class="sxs-lookup"><span data-stu-id="a0db5-135">A department name must not contain the character "~"</span></span>  
 <span data-ttu-id="a0db5-136">包含字符的部门名称"~"将导致 A4SWIFT 数据库时出现的问题。</span><span class="sxs-lookup"><span data-stu-id="a0db5-136">A department name that contains the character "~" will cause issues with the A4SWIFT database.</span></span>  
  
#### <a name="signing-infopath-forms"></a><span data-ttu-id="a0db5-137">签名 Infopath 窗体</span><span class="sxs-lookup"><span data-stu-id="a0db5-137">Signing Infopath forms</span></span>  
 <span data-ttu-id="a0db5-138">对签名的 InfoPath 窗体需要手动完成。</span><span class="sxs-lookup"><span data-stu-id="a0db5-138">The signing of InfoPath forms needs to be done manually.</span></span>  
  
## <a name="security"></a><span data-ttu-id="a0db5-139">安全性</span><span class="sxs-lookup"><span data-stu-id="a0db5-139">Security</span></span>

#### <a name="mixing-trusted-and-untrusted-hosts-can-enable-spoofing"></a><span data-ttu-id="a0db5-140">混合使用受信任和不受信任主机可以启用欺骗</span><span class="sxs-lookup"><span data-stu-id="a0db5-140">Mixing trusted and untrusted hosts can enable spoofing</span></span>  

 <span data-ttu-id="a0db5-141">有可能为欺骗从其他不受信任的 SWIFT 绑定消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]托管应用程序。</span><span class="sxs-lookup"><span data-stu-id="a0db5-141">It may be possible to spoof SWIFT-bound messages from other non-trusted [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host applications.</span></span> <span data-ttu-id="a0db5-142">这是只是问题，在混合信任模式下运行时 (受信任的主机和不受信任的主机中运行时，应用程序相同[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]组)。</span><span class="sxs-lookup"><span data-stu-id="a0db5-142">This is only a problem when running in mixed-trust mode (when trusted hosts and untrusted hosts run applications in the same [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] group).</span></span> <span data-ttu-id="a0db5-143">通过使用参与方解析管道组件标识 SWIFT 绑定消息的源，可以缓解此风险。</span><span class="sxs-lookup"><span data-stu-id="a0db5-143">You can mitigate this risk by using party-resolution pipeline components to identify the source of the SWIFT-bound message.</span></span> <span data-ttu-id="a0db5-144">运行在完全受信任环境中或对于大多数使用情况方案时，这是不必要的。</span><span class="sxs-lookup"><span data-stu-id="a0db5-144">This is not necessary when running in a fully trusted environment or for the majority of usage scenarios.</span></span> <span data-ttu-id="a0db5-145">应遵循[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]混合时构建安全应用程序的指导原则受信任和不受信任的主机。</span><span class="sxs-lookup"><span data-stu-id="a0db5-145">You should follow the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] guidelines for building secure applications when mixing trusted and untrusted hosts.</span></span> 
 
## <a name="miscellaneous"></a><span data-ttu-id="a0db5-146">杂项</span><span class="sxs-lookup"><span data-stu-id="a0db5-146">Miscellaneous</span></span>

#### <a name="the-cacheentries-setting-may-be-reset-by-a-setup-program-affecting-performance"></a><span data-ttu-id="a0db5-147">CacheEntries 设置重置被安装程序，会对性能影响</span><span class="sxs-lookup"><span data-stu-id="a0db5-147">The CacheEntries setting may be reset by a Setup program, affecting performance</span></span>  
 <span data-ttu-id="a0db5-148">CacheEntries 注册表项确定的最大 ruleset 由业务规则引擎更新服务缓存数。</span><span class="sxs-lookup"><span data-stu-id="a0db5-148">The CacheEntries registry key determines the maximum number of rulesets cached by the Business Rule Engine Update service.</span></span> <span data-ttu-id="a0db5-149">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安装程序默认情况下将 CacheEntries 设为 32。</span><span class="sxs-lookup"><span data-stu-id="a0db5-149">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Setup program sets CacheEntries to 32 by default.</span></span> <span data-ttu-id="a0db5-150">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序更改 HKEY_LOCAL_MACHINE\SOFTWARE\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]\BusinessRules\3.0\CacheEntries 为 512 以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="a0db5-150">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Setup program changes HKEY_LOCAL_MACHINE\SOFTWARE\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]\BusinessRules\3.0\CacheEntries to 512 for optimum performance.</span></span> <span data-ttu-id="a0db5-151">但是，在某些情况下，CacheEntries 可能被自动重新设置。</span><span class="sxs-lookup"><span data-stu-id="a0db5-151">However, in certain circumstances, CacheEntries may be reset automatically.</span></span> <span data-ttu-id="a0db5-152">这可能会影响系统性能。</span><span class="sxs-lookup"><span data-stu-id="a0db5-152">This may affect system performance.</span></span>  
  
 <span data-ttu-id="a0db5-153">规则引擎更新可能会变为 CacheEntries 从 512 32。</span><span class="sxs-lookup"><span data-stu-id="a0db5-153">Rule Engine updates may change CacheEntries from 512 to 32.</span></span> <span data-ttu-id="a0db5-154">在安装的规则引擎更新后, 手动重置 CacheEntries 为 512，如有必要。</span><span class="sxs-lookup"><span data-stu-id="a0db5-154">After installing a Rule Engine update, manually reset CacheEntries to 512, if necessary.</span></span>  
  
 <span data-ttu-id="a0db5-155">即使[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序将从 32 CacheEntries 设置为 512，卸载[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]不重置 CacheEntries 从 512 为 32。</span><span class="sxs-lookup"><span data-stu-id="a0db5-155">Even though the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Setup program sets CacheEntries from 32 to 512, uninstalling [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] does not reset CacheEntries from 512 to 32.</span></span>  
  
 <span data-ttu-id="a0db5-156">有关详细信息，请参阅 BizTalk Server 帮助中的"规则引擎配置和优化参数"主题。</span><span class="sxs-lookup"><span data-stu-id="a0db5-156">For more information, see the "Rule Engine Configuration and Tuning Parameters" topic in BizTalk Server Help.</span></span>  
  
#### <a name="building-a-pipeline-project-may-result-in-a-large-number-of-warnings"></a><span data-ttu-id="a0db5-157">生成管道项目可能会导致大量的警告</span><span class="sxs-lookup"><span data-stu-id="a0db5-157">Building a pipeline project may result in a large number of warnings</span></span>  
 <span data-ttu-id="a0db5-158">当你将 SWIFT 汇编程序添加到发送管道或 SWIFT 拆装器接收管道，然后生成包含这些管道的管道项目，你可能会收到警告的管道组件相关的一系列。</span><span class="sxs-lookup"><span data-stu-id="a0db5-158">When you add the SWIFT assembler to a send pipeline, or the SWIFT disassembler to a receive pipeline, and then build the pipeline project containing those pipelines, you may receive a series of warnings related to the pipeline components.</span></span> <span data-ttu-id="a0db5-159">这些警告指示 Visual Studio 找不到依赖项。</span><span class="sxs-lookup"><span data-stu-id="a0db5-159">These warnings indicate that Visual Studio could not find dependencies.</span></span> <span data-ttu-id="a0db5-160">您可以更正导致通过更改中的引用文件夹中，SWIFTAsm 或 SWIFTDasm 程序集的复制本地属性，如下所示的这些警告的条件：</span><span class="sxs-lookup"><span data-stu-id="a0db5-160">You can correct the condition leading to these warnings by changing the Copy Local property of the SWIFTAsm or SWIFTDasm assembly in the reference folder, as follows:</span></span>  
  
1.  <span data-ttu-id="a0db5-161">在解决方案资源管理器的 Visual Studio 中，展开你的管道项目，然后展开**引用**节点。</span><span class="sxs-lookup"><span data-stu-id="a0db5-161">In Solution Explorer of Visual Studio, expand your pipeline project, and then expand the **References** node.</span></span>  
  
2.  <span data-ttu-id="a0db5-162">在引用节点下选择**SWIFTAsm**程序集和/或**SWIFTDasm**程序集。</span><span class="sxs-lookup"><span data-stu-id="a0db5-162">Under the References node, select the **SWIFTAsm** assembly and/or the **SWIFTDasm** assembly.</span></span>  
  
3.  <span data-ttu-id="a0db5-163">在属性窗格中的值更改**Copy Local**属性**False**。</span><span class="sxs-lookup"><span data-stu-id="a0db5-163">In the Properties pane, change the value for the **Copy Local** property to **False**.</span></span>  
  
4.  <span data-ttu-id="a0db5-164">右键单击你管道的项目，并依次**生成**。</span><span class="sxs-lookup"><span data-stu-id="a0db5-164">Right-click your pipeline project, and then click **Build**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0db5-165">不应看到有关依赖关系找不到任何警告。</span><span class="sxs-lookup"><span data-stu-id="a0db5-165">You should not see any warnings about dependencies not being found.</span></span>   