---
title: 其他问题疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 1f115f64-45ce-445d-ab18-092f4a6a232c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bab6578c6a9fcbc4a9b1349833604188d1d7884c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286424"
---
# <a name="troubleshooting-other-issues"></a><span data-ttu-id="ceda4-102">其他问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="ceda4-102">Troubleshooting Other Issues</span></span>
<span data-ttu-id="ceda4-103">解决了与 Microsoft 相关的其他问题[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ceda4-103">Addresses other issues related to Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  
  
## <a name="message-rejected-by-the-btahl7-engine"></a><span data-ttu-id="ceda4-104">BTAHL7 引擎被拒绝的消息</span><span class="sxs-lookup"><span data-stu-id="ceda4-104">Message rejected by the BTAHL7 engine</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="ceda4-105">故障现象</span><span class="sxs-lookup"><span data-stu-id="ceda4-105">Symptom</span></span>  
 <span data-ttu-id="ceda4-106">由消息引擎将随机拒绝邮件。</span><span class="sxs-lookup"><span data-stu-id="ceda4-106">Messages are randomly rejected by the message engine.</span></span>  
  
<span data-ttu-id="ceda4-107">**可能的原因**:根据 HL7 标准的枚举值的表 0338年包含"L & 我"的值。</span><span class="sxs-lookup"><span data-stu-id="ceda4-107">**Possible Cause** : According to the HL7 standard, enumeration values for table 0338 contains the "L&I" value.</span></span> <span data-ttu-id="ceda4-108">字段 6 PRA 段的可能包含此值。</span><span class="sxs-lookup"><span data-stu-id="ceda4-108">Field 6 of the PRA segment may contain this value.</span></span> <span data-ttu-id="ceda4-109">由于[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]会"&"字符作为分隔符，则消息被拒绝。</span><span class="sxs-lookup"><span data-stu-id="ceda4-109">Since [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] treats the "&" character as a delimiter, the message is rejected.</span></span>  
  
<span data-ttu-id="ceda4-110">**解析**:有三个可能针对此问题的解决方法：</span><span class="sxs-lookup"><span data-stu-id="ceda4-110">**Resolution** : There are three potential resolutions for this issue:</span></span>  
  
1.  <span data-ttu-id="ceda4-111">在消息实例中，处理通过转义序列，例如，使用字符组合 L\T\I"&"字符。</span><span class="sxs-lookup"><span data-stu-id="ceda4-111">In the message instance, handle the "&" character through an escape sequence, such as using the character combination L\T\I.</span></span>  
  
2.  <span data-ttu-id="ceda4-112">在架构中在 PRA 6 添加"LI"的枚举值，并在消息实例中改为使用此值。</span><span class="sxs-lookup"><span data-stu-id="ceda4-112">Add an enumeration value of "LI" at PRA 6 in the schema and use this value instead in the message instance.</span></span>  
  
3.  <span data-ttu-id="ceda4-113">在 MSH2; 中使用完全不同的子组件分隔符但是，这个特殊的解决方案可能不可行取决于你的环境。</span><span class="sxs-lookup"><span data-stu-id="ceda4-113">Use a completely different subcomponent separator in MSH2; however, this particular solution may not be practical depending upon your environment.</span></span>  
  
## <a name="cannot-edit-the-hl7-schema-using-visual-studio"></a><span data-ttu-id="ceda4-114">不能编辑使用 Visual Studio 的 HL7 架构</span><span class="sxs-lookup"><span data-stu-id="ceda4-114">Cannot edit the HL7 schema using Visual Studio</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="ceda4-115">故障现象</span><span class="sxs-lookup"><span data-stu-id="ceda4-115">Symptom</span></span>  
 <span data-ttu-id="ceda4-116">不能编辑使用 Microsoft 的 HL7 架构[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ceda4-116">Cannot edit the HL7 schema using Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
<span data-ttu-id="ceda4-117">**可能的原因**:[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]不支持某些 HL7 架构。</span><span class="sxs-lookup"><span data-stu-id="ceda4-117">**Possible Cause** : [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] does not support some HL7 schemas.</span></span>  
  
<span data-ttu-id="ceda4-118">**解析**:使用其他编辑器 （如 Microsoft 记事本） 编辑 HL7 架构。</span><span class="sxs-lookup"><span data-stu-id="ceda4-118">**Resolution** : Use other editors, such as Microsoft Notepad, to edit HL7 schemas.</span></span>  
  
## <a name="message-handling-fails-with-no-errors-logged"></a><span data-ttu-id="ceda4-119">消息处理失败，并记录任何错误</span><span class="sxs-lookup"><span data-stu-id="ceda4-119">Message handling fails with no errors logged</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="ceda4-120">故障现象</span><span class="sxs-lookup"><span data-stu-id="ceda4-120">Symptom</span></span>  
 <span data-ttu-id="ceda4-121">系统处理消息，而不记录错误消息或将消息放在挂起的消息队列中。</span><span class="sxs-lookup"><span data-stu-id="ceda4-121">The system processes messages without logging error messages or placing messages in the suspended message queue.</span></span>  
  
<span data-ttu-id="ceda4-122">**可能的原因**:**HeaderSpecType**并**DocumentSpecType**属性值不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="ceda4-122">**Possible Cause** : The **HeaderSpecType** and **DocumentSpecType** property values are case-sensitive.</span></span> <span data-ttu-id="ceda4-123">在部署管道时，这些名称中犯了输入错误可能会导致错误处理和删除，而不记录的错误的消息。</span><span class="sxs-lookup"><span data-stu-id="ceda4-123">When you deploy your pipelines, a typographical error in these names can cause messages to be mishandled and dropped with no errors logged.</span></span>  
  
<span data-ttu-id="ceda4-124">**解析**:使用时，应遵守区分大小写**HeaderSpecType**并**DocumentSpecType**属性值名称。</span><span class="sxs-lookup"><span data-stu-id="ceda4-124">**Resolution** : Observe case-sensitivity when using the **HeaderSpecType** and **DocumentSpecType** property value names.</span></span>  
  
## <a name="message-header-fields-are-not-validated-correctly"></a><span data-ttu-id="ceda4-125">尚未正确验证消息的标头字段</span><span class="sxs-lookup"><span data-stu-id="ceda4-125">Message header fields are not validated correctly</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="ceda4-126">故障现象</span><span class="sxs-lookup"><span data-stu-id="ceda4-126">Symptom</span></span>  
 <span data-ttu-id="ceda4-127">标头字段的验证失败。</span><span class="sxs-lookup"><span data-stu-id="ceda4-127">Validation of a header field failed.</span></span>  
  
 <span data-ttu-id="ceda4-128">原因:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序验证升级的属性，而不是实际标头字段上下文属性。</span><span class="sxs-lookup"><span data-stu-id="ceda4-128">Reason: The [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializer validated a promoted property, not the actual header-field context property.</span></span>  
  
<span data-ttu-id="ceda4-129">**可能的原因**:通过业务流程或映射的标头与对应的已提升属性发生变化。</span><span class="sxs-lookup"><span data-stu-id="ceda4-129">**Possible Cause** : A change occurred to the promoted property corresponding to the header through an orchestration or a map.</span></span>  
  
<span data-ttu-id="ceda4-130">**解析**:上下文属性的消息标头 MSH1、 MSH2 和 MSH5{1-3}需要进行更新，以便它们中的数据同步。</span><span class="sxs-lookup"><span data-stu-id="ceda4-130">**Resolution** : The context properties of message headers MSH1, MSH2, and MSH5{1-3} need to be updated so that they are in synchronization with the data.</span></span>  
  
## <a name="the-mllp-adapter-is-not-removed-during-uninstall"></a><span data-ttu-id="ceda4-131">在卸载过程不会删除 MLLP 适配器</span><span class="sxs-lookup"><span data-stu-id="ceda4-131">The MLLP adapter is not removed during uninstall</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="ceda4-132">故障现象</span><span class="sxs-lookup"><span data-stu-id="ceda4-132">Symptom</span></span>  
 <span data-ttu-id="ceda4-133">卸载 BTAHL7 的过程，则 BTAHL7 安装程序未删除 MLLP 适配器。</span><span class="sxs-lookup"><span data-stu-id="ceda4-133">The BTAHL7 setup program did not remove the MLLP adapter during uninstallation of BTAHL7.</span></span>  
  
<span data-ttu-id="ceda4-134">**可能的原因**:与传输类型为 MLLP 的接收位置或发送端口时出现。</span><span class="sxs-lookup"><span data-stu-id="ceda4-134">**Possible Cause** : There was a receive location or send port with a transport type of MLLP.</span></span> <span data-ttu-id="ceda4-135">如果在任何 BizTalk Server 项目中引用，则 BTAHL7 安装程序不能删除 MLLP 适配器。</span><span class="sxs-lookup"><span data-stu-id="ceda4-135">BTAHL7 setup cannot remove the MLLP adapter if it is being referenced in any of the BizTalk Server projects.</span></span>  
  
<span data-ttu-id="ceda4-136">**解析**:在卸载 BTAHL7 的已完成后，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ceda4-136">**Resolution** : After uninstallation of BTAHL7 has completed, do the following:</span></span>  
  
1.  <span data-ttu-id="ceda4-137">在 BizTalk Server 管理控制台中，删除所有接收位置和发送端口的传输类型为 MLLP，或更改接收位置的传输类型或发送端口与另一种类型的端口。</span><span class="sxs-lookup"><span data-stu-id="ceda4-137">In the BizTalk Server Administration Console, remove all receive locations and send ports that have a transport type of MLLP, or change the transport type of the receive locations or send ports to another type.</span></span>  
  
2.  <span data-ttu-id="ceda4-138">在管理控制台中，删除 MLLP 适配器。</span><span class="sxs-lookup"><span data-stu-id="ceda4-138">In the Administration Console, delete the MLLP adapter.</span></span>  
  
3.  <span data-ttu-id="ceda4-139">重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="ceda4-139">Restart the host instance.</span></span>  
  
## <a name="btahl7-cannot-be-uninstalled-if-biztalk-server-has-already-been-uninstalled"></a><span data-ttu-id="ceda4-140">如果已卸载 BizTalk Server 无法卸载 BTAHL7</span><span class="sxs-lookup"><span data-stu-id="ceda4-140">BTAHL7 cannot be uninstalled if BizTalk Server has already been uninstalled</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="ceda4-141">故障现象</span><span class="sxs-lookup"><span data-stu-id="ceda4-141">Symptom</span></span>  
 <span data-ttu-id="ceda4-142">卸载[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]会导致以下错误：</span><span class="sxs-lookup"><span data-stu-id="ceda4-142">Uninstalling [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] results in the following error:</span></span>  
  
`A network error while attempting to read from file C:\Windows\Installer\Microsoft BizTalk <version\> Accelerator for HL7.msi`
  
<span data-ttu-id="ceda4-143">**可能的原因**:[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]在卸载之前卸载[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]尝试。</span><span class="sxs-lookup"><span data-stu-id="ceda4-143">**Possible Cause** : [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] was uninstalled before uninstallation of [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] was attempted.</span></span> <span data-ttu-id="ceda4-144">必须先卸载[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]然后再卸载[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ceda4-144">You must uninstall [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] before uninstalling [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
<span data-ttu-id="ceda4-145">**解析**:重新安装[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]，然后卸载[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]，然后卸载[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ceda4-145">**Resolution** : Reinstall [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], then uninstall [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)], and then uninstall [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="messages-are-still-sent-after-the-applicable-mllp-send-port-has-been-stopped"></a><span data-ttu-id="ceda4-146">停止适用 MLLP 发送端口后，仍然发送消息</span><span class="sxs-lookup"><span data-stu-id="ceda4-146">Messages are still sent after the applicable MLLP send port has been stopped</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="ceda4-147">故障现象</span><span class="sxs-lookup"><span data-stu-id="ceda4-147">Symptom</span></span>  
 <span data-ttu-id="ceda4-148">您不停止的停止 MLLP 发送端口，通过发送该发送端口的消息，之后继续发送。</span><span class="sxs-lookup"><span data-stu-id="ceda4-148">After you stop an MLLP send port, the messages that are sent through that send port do not stop, but continue to be sent.</span></span>  
  
<span data-ttu-id="ceda4-149">**可能的原因**:停止发送端口时，连接将仍保持已建立，删除通过停止 BizTalk 主机之前。</span><span class="sxs-lookup"><span data-stu-id="ceda4-149">**Possible Cause** : When you stop a send port, the connection remains established until it is removed by stopping the BizTalk host.</span></span> <span data-ttu-id="ceda4-150">因此，停止发送端口后，仍会发送消息。</span><span class="sxs-lookup"><span data-stu-id="ceda4-150">As a result, messages are still sent after the send port has been stopped.</span></span> <span data-ttu-id="ceda4-151">这是因为 Biztalk Server 不会为处的 MLLP 适配器调用期间启动或停止的发送端口。</span><span class="sxs-lookup"><span data-stu-id="ceda4-151">This occurs because Biztalk Server does not call into the MLLP adapter during start or stop of the send port.</span></span> <span data-ttu-id="ceda4-152">BizTalk Server 调用到处的 MLLP 适配器仅在开始和停止主机服务。</span><span class="sxs-lookup"><span data-stu-id="ceda4-152">BizTalk Server calls into the MLLP adapter only during the start and stop of the host service.</span></span>  
  
<span data-ttu-id="ceda4-153">**解析**:可以删除该连接，并通过停止你已停止的发送端口的发送处理程序的主机实例停止的消息传输。</span><span class="sxs-lookup"><span data-stu-id="ceda4-153">**Resolution** : You can remove the connection and stop transmission of messages by stopping the host instance that is the send handler for the send port that you stopped.</span></span> <span data-ttu-id="ceda4-154">但是，停止该主机实例可能会影响你不想要停止其他消息。</span><span class="sxs-lookup"><span data-stu-id="ceda4-154">However, stopping that host instance might affect other messages that you do not want to stop.</span></span> <span data-ttu-id="ceda4-155">如果您知道这种情况，您应在创建时以不同的方式配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="ceda4-155">If you know that this is the case, you should configure the send port differently when you create it.</span></span> <span data-ttu-id="ceda4-156">应创建另一个主机实例，以用作仅此 MLLP 发送端口 （或发送端口的子集） 的发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="ceda4-156">You should create another host instance to serve as the send handler for only this MLLP send port (or a subset of your send ports).</span></span> <span data-ttu-id="ceda4-157">然后可以通过停止此主机实例停止此发送端口中的消息传输。</span><span class="sxs-lookup"><span data-stu-id="ceda4-157">You can then stop transmission of messages from this send port by stopping this host instance.</span></span> <span data-ttu-id="ceda4-158">这将不影响其他使用其他发送处理程序的发送端口上的其他消息的传输。</span><span class="sxs-lookup"><span data-stu-id="ceda4-158">This will then not affect transmission of other messages on other send ports that use other send handlers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceda4-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="ceda4-159">See Also</span></span>  
 [<span data-ttu-id="ceda4-160">HL7 的疑难解答和已知问题</span><span class="sxs-lookup"><span data-stu-id="ceda4-160">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)