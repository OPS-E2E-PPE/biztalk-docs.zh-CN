---
title: 确认疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, troubleshooting
- troubleshooting, acknowledgements
ms.assetid: faed356e-f5fc-4920-a9f9-82eca0ad7d67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a66eba1221b30ec142cc44400c60cff6f66e62e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286522"
---
# <a name="troubleshooting-acknowledgments"></a><span data-ttu-id="53222-102">确认疑难解答</span><span class="sxs-lookup"><span data-stu-id="53222-102">Troubleshooting Acknowledgments</span></span>
<span data-ttu-id="53222-103">解决了与相关的问题[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]确认。</span><span class="sxs-lookup"><span data-stu-id="53222-103">Addresses issues related to [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] acknowledgments.</span></span>  
  
## <a name="acknowledgments-are-not-generated"></a><span data-ttu-id="53222-104">不生成确认</span><span class="sxs-lookup"><span data-stu-id="53222-104">Acknowledgments are not generated</span></span>  
 <span data-ttu-id="53222-105">有多个确认 (Ack) 不生成或接收的潜在原因。</span><span class="sxs-lookup"><span data-stu-id="53222-105">There are several potential causes for acknowledgments (ACKs) not being generated or received.</span></span> <span data-ttu-id="53222-106">查看以下潜在问题的列表。</span><span class="sxs-lookup"><span data-stu-id="53222-106">Review the following list of potential problems.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="53222-107">故障现象</span><span class="sxs-lookup"><span data-stu-id="53222-107">Symptom</span></span>  
 <span data-ttu-id="53222-108">当更新中的参与方信息时，不会生成确认[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器生成确认。</span><span class="sxs-lookup"><span data-stu-id="53222-108">Acknowledgments are not generated when you update party information in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer to generate acknowledgments.</span></span>  
  
<span data-ttu-id="53222-109">**可能的原因**:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]缓存并刷新参与方配置信息每隔 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="53222-109">**Possible cause** : [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] caches and refreshes party configuration information every 15 minutes.</span></span>  
  
<span data-ttu-id="53222-110">**解析**:等待至少 15 分钟的缓存刷新，或重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]的更改立即生效。</span><span class="sxs-lookup"><span data-stu-id="53222-110">**Resolution** : Wait for at least 15 minutes for the cache to refresh, or restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for changes to take effect immediately.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="53222-111">故障现象</span><span class="sxs-lookup"><span data-stu-id="53222-111">Symptom</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="53222-112">does 不会生成用于确认和事件日志中出现事件错误。</span><span class="sxs-lookup"><span data-stu-id="53222-112">does not generate ACKs and event errors appear in the event log.</span></span>  
  
<span data-ttu-id="53222-113">**可能的原因**:无法生成确认时中的批处理, / 出消息的批包含空 FHS11 字段。</span><span class="sxs-lookup"><span data-stu-id="53222-113">**Possible cause** : An ACK cannot be generated when a batch in/batch out message contains an empty FHS11 field.</span></span>  
  
<span data-ttu-id="53222-114">**解析**:请确保消息具有正确格式化和填充 FHS11 字段。</span><span class="sxs-lookup"><span data-stu-id="53222-114">**Resolution** : Ensure that your messages have a correctly formatted and populated FHS11 field.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="53222-115">故障现象</span><span class="sxs-lookup"><span data-stu-id="53222-115">Symptom</span></span>  
 <span data-ttu-id="53222-116">你的应用程序将无法生成或接收确认。</span><span class="sxs-lookup"><span data-stu-id="53222-116">Your application cannot generate or receive an ACK.</span></span>  
  
<span data-ttu-id="53222-117">**可能的原因**:MSH3 字段中的消息的不正确信息可以防止[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]从发送消息的确认。</span><span class="sxs-lookup"><span data-stu-id="53222-117">**Possible cause** : Incorrect information in the MSH3 field of your message prevents [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] from sending the message ACKs.</span></span>  
  
<span data-ttu-id="53222-118">**解析**:请确保消息具有正确格式化和填充 MSH3 字段。</span><span class="sxs-lookup"><span data-stu-id="53222-118">**Resolution** : Ensure that your messages have a correctly formatted and populated MSH3 field.</span></span>  
  
## <a name="acknowledgments-are-suspended-or-not-routed-to-the-send-party"></a><span data-ttu-id="53222-119">挂起或不会路由至发送方确认</span><span class="sxs-lookup"><span data-stu-id="53222-119">Acknowledgments are suspended or not routed to the send party</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="53222-120">故障现象</span><span class="sxs-lookup"><span data-stu-id="53222-120">Symptom</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="53222-121">将消息发送到双向适配器，而不会生成确认。</span><span class="sxs-lookup"><span data-stu-id="53222-121">sends messages to a two-way adapter without generating acknowledgments.</span></span>  
  
<span data-ttu-id="53222-122">**可能的原因**:消息订阅的配置不正确。</span><span class="sxs-lookup"><span data-stu-id="53222-122">**Possible cause** : The message subscription is not configured correctly.</span></span>  
  
<span data-ttu-id="53222-123">**解析**:确保消息订阅已存在并且配置正确。</span><span class="sxs-lookup"><span data-stu-id="53222-123">**Resolution** : Ensure that message subscriptions are present and configured correctly.</span></span>  
  
## <a name="suspended-acknowledgments"></a><span data-ttu-id="53222-124">挂起的确认</span><span class="sxs-lookup"><span data-stu-id="53222-124">Suspended acknowledgments</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="53222-125">故障现象</span><span class="sxs-lookup"><span data-stu-id="53222-125">Symptom</span></span>  
 <span data-ttu-id="53222-126">确认挂起并显示错误消息"字段中找到的分隔符"配置该参与方如包含分隔符字符的字符进行编码时@-！ $。</span><span class="sxs-lookup"><span data-stu-id="53222-126">Acknowledgments are suspended with the error message "Delimiter found in the field" when you have configured the party to have encoding characters containing delimiter characters such as @-!$.</span></span>  
  
<span data-ttu-id="53222-127">**可能的原因**:该消息包含一个句点 （.） 或连字符 （-） 等字符。</span><span class="sxs-lookup"><span data-stu-id="53222-127">**Possible cause** : The message contains characters such as a period (.) or a hyphen (-).</span></span> <span data-ttu-id="53222-128">生成 Ack 时[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]包括"。"和"-"时间戳值。</span><span class="sxs-lookup"><span data-stu-id="53222-128">When generating the ACKs, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] includes "." and "-" for the timestamp value.</span></span>  
  
<span data-ttu-id="53222-129">**解析**:禁用在发送管道中要避免这些错误的验证。</span><span class="sxs-lookup"><span data-stu-id="53222-129">**Resolution** : Disable validation in the send pipeline to avoid these errors.</span></span>  
  
## <a name="biztalk-server-generates-an-error-about-missing-ack-when-using-2-way-mllp-adapter"></a><span data-ttu-id="53222-130">BizTalk Server 生成关于缺少确认使用双向处的 MLLP 适配器时的错误</span><span class="sxs-lookup"><span data-stu-id="53222-130">BizTalk Server generates an error about missing ACK when using 2-way MLLP adapter</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="53222-131">故障现象</span><span class="sxs-lookup"><span data-stu-id="53222-131">Symptom</span></span>  
 <span data-ttu-id="53222-132">事件日志中收到以下或类似错误：</span><span class="sxs-lookup"><span data-stu-id="53222-132">You get the following or similar error in the Event Log:</span></span>  
  
 <span data-ttu-id="53222-133">"无法从网络由于错误接收 ACK"异常来自 HRESULT:0xC0C01662""</span><span class="sxs-lookup"><span data-stu-id="53222-133">"Unable to receive ACK from network due to error "Exception from HRESULT: 0xC0C01662""</span></span>  
  
<span data-ttu-id="53222-134">**可能的原因**:使用单向接收和双向发送端口，因此，BizTalk 没有相应的接收端口以返回来自双向发送端口接收的消息。</span><span class="sxs-lookup"><span data-stu-id="53222-134">**Possible cause** : You are using 1-way receive and 2-way send port, so BizTalk does not have a corresponding Receive port to return the message received from the 2-way Send port.</span></span>  
  
<span data-ttu-id="53222-135">**解析**:这是设计使然，并且可以忽略的错误消息。</span><span class="sxs-lookup"><span data-stu-id="53222-135">**Resolution** : This is by design, and you can ignore the error message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53222-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="53222-136">See Also</span></span>  
[<span data-ttu-id="53222-137">HL7 的疑难解答和已知问题</span><span class="sxs-lookup"><span data-stu-id="53222-137">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)