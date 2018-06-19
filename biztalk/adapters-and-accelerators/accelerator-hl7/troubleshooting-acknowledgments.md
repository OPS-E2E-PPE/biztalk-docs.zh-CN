---
title: 故障排除确认 |Microsoft 文档
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
ms.openlocfilehash: ecbbb22498cfd3d451c0b8c75c8e6f4502c2364d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207029"
---
# <a name="troubleshooting-acknowledgments"></a><span data-ttu-id="8efea-102">故障排除的确认</span><span class="sxs-lookup"><span data-stu-id="8efea-102">Troubleshooting Acknowledgments</span></span>
<span data-ttu-id="8efea-103">解决与相关的问题，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]确认。</span><span class="sxs-lookup"><span data-stu-id="8efea-103">Addresses issues related to [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] acknowledgments.</span></span>  
  
## <a name="acknowledgments-are-not-generated"></a><span data-ttu-id="8efea-104">确认不会生成</span><span class="sxs-lookup"><span data-stu-id="8efea-104">Acknowledgments are not generated</span></span>  
 <span data-ttu-id="8efea-105">有几个确认 (Ack) 不生成或接收的潜在原因。</span><span class="sxs-lookup"><span data-stu-id="8efea-105">There are several potential causes for acknowledgments (ACKs) not being generated or received.</span></span> <span data-ttu-id="8efea-106">查看以下列表的潜在问题。</span><span class="sxs-lookup"><span data-stu-id="8efea-106">Review the following list of potential problems.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="8efea-107">故障现象</span><span class="sxs-lookup"><span data-stu-id="8efea-107">Symptom</span></span>  
 <span data-ttu-id="8efea-108">当你更新方中的信息时，不会生成确认[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器以生成确认。</span><span class="sxs-lookup"><span data-stu-id="8efea-108">Acknowledgments are not generated when you update party information in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer to generate acknowledgments.</span></span>  
  
<span data-ttu-id="8efea-109">**可能的原因**:[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]缓存并方配置信息每隔 15 分钟刷新一次。</span><span class="sxs-lookup"><span data-stu-id="8efea-109">**Possible cause** : [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] caches and refreshes party configuration information every 15 minutes.</span></span>  
  
<span data-ttu-id="8efea-110">**解析**： 等待至少 15 分钟缓存刷新或重新启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]的更改立即生效。</span><span class="sxs-lookup"><span data-stu-id="8efea-110">**Resolution** : Wait for at least 15 minutes for the cache to refresh, or restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] for changes to take effect immediately.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="8efea-111">故障现象</span><span class="sxs-lookup"><span data-stu-id="8efea-111">Symptom</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="8efea-112">不生成 Ack 且事件错误出现在事件日志。</span><span class="sxs-lookup"><span data-stu-id="8efea-112"> does not generate ACKs and event errors appear in the event log.</span></span>  
  
<span data-ttu-id="8efea-113">**可能的原因**： 时中的批，无法生成 ACK / 出消息的批处理包含空 FHS11 字段。</span><span class="sxs-lookup"><span data-stu-id="8efea-113">**Possible cause** : An ACK cannot be generated when a batch in/batch out message contains an empty FHS11 field.</span></span>  
  
<span data-ttu-id="8efea-114">**解析**： 确保你的消息具有正确格式化和填充 FHS11 字段。</span><span class="sxs-lookup"><span data-stu-id="8efea-114">**Resolution** : Ensure that your messages have a correctly formatted and populated FHS11 field.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="8efea-115">故障现象</span><span class="sxs-lookup"><span data-stu-id="8efea-115">Symptom</span></span>  
 <span data-ttu-id="8efea-116">你的应用程序无法生成或接收确认</span><span class="sxs-lookup"><span data-stu-id="8efea-116">Your application cannot generate or receive an ACK.</span></span>  
  
<span data-ttu-id="8efea-117">**可能的原因**: MSH3 字段中的消息的不正确信息会阻止[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]从发送消息确认。</span><span class="sxs-lookup"><span data-stu-id="8efea-117">**Possible cause** : Incorrect information in the MSH3 field of your message prevents [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] from sending the message ACKs.</span></span>  
  
<span data-ttu-id="8efea-118">**解析**： 确保你的消息具有正确格式化和填充 MSH3 字段。</span><span class="sxs-lookup"><span data-stu-id="8efea-118">**Resolution** : Ensure that your messages have a correctly formatted and populated MSH3 field.</span></span>  
  
## <a name="acknowledgments-are-suspended-or-not-routed-to-the-send-party"></a><span data-ttu-id="8efea-119">挂起或未路由到发送方确认</span><span class="sxs-lookup"><span data-stu-id="8efea-119">Acknowledgments are suspended or not routed to the send party</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="8efea-120">故障现象</span><span class="sxs-lookup"><span data-stu-id="8efea-120">Symptom</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="8efea-121">将消息发送到双向适配器，而不生成确认。</span><span class="sxs-lookup"><span data-stu-id="8efea-121"> sends messages to a two-way adapter without generating acknowledgments.</span></span>  
  
<span data-ttu-id="8efea-122">**可能的原因**： 消息订阅配置不正确。</span><span class="sxs-lookup"><span data-stu-id="8efea-122">**Possible cause** : The message subscription is not configured correctly.</span></span>  
  
<span data-ttu-id="8efea-123">**解析**： 确保消息的订阅已存在并且配置正确。</span><span class="sxs-lookup"><span data-stu-id="8efea-123">**Resolution** : Ensure that message subscriptions are present and configured correctly.</span></span>  
  
## <a name="suspended-acknowledgments"></a><span data-ttu-id="8efea-124">挂起的确认</span><span class="sxs-lookup"><span data-stu-id="8efea-124">Suspended acknowledgments</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="8efea-125">故障现象</span><span class="sxs-lookup"><span data-stu-id="8efea-125">Symptom</span></span>  
 <span data-ttu-id="8efea-126">确认挂起并显示错误消息"字段中找到的分隔符"配置该参与方将具有如包含分隔符的字符进行编码时@-！ $。</span><span class="sxs-lookup"><span data-stu-id="8efea-126">Acknowledgments are suspended with the error message "Delimiter found in the field" when you have configured the party to have encoding characters containing delimiter characters such as @-!$.</span></span>  
  
<span data-ttu-id="8efea-127">**可能的原因**： 消息包含如句点 （.） 或连字符 （-） 字符。</span><span class="sxs-lookup"><span data-stu-id="8efea-127">**Possible cause** : The message contains characters such as a period (.) or a hyphen (-).</span></span> <span data-ttu-id="8efea-128">当生成 Ack，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]包括"。"和"-"时间戳值。</span><span class="sxs-lookup"><span data-stu-id="8efea-128">When generating the ACKs, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] includes "." and "-" for the timestamp value.</span></span>  
  
<span data-ttu-id="8efea-129">**解析**： 在发送管道，以避免这些错误中禁用验证。</span><span class="sxs-lookup"><span data-stu-id="8efea-129">**Resolution** : Disable validation in the send pipeline to avoid these errors.</span></span>  
  
## <a name="biztalk-server-generates-an-error-about-missing-ack-when-using-2-way-mllp-adapter"></a><span data-ttu-id="8efea-130">BizTalk Server 生成有关缺少 ACK，使用双向 MLLP 适配器时出错</span><span class="sxs-lookup"><span data-stu-id="8efea-130">BizTalk Server generates an error about missing ACK when using 2-way MLLP adapter</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="8efea-131">故障现象</span><span class="sxs-lookup"><span data-stu-id="8efea-131">Symptom</span></span>  
 <span data-ttu-id="8efea-132">事件日志中获取以下或类似错误：</span><span class="sxs-lookup"><span data-stu-id="8efea-132">You get the following or similar error in the Event Log:</span></span>  
  
 <span data-ttu-id="8efea-133">"无法从网络由于错误接收 ACK"异常来自 HRESULT: 0xC0C01662""</span><span class="sxs-lookup"><span data-stu-id="8efea-133">"Unable to receive ACK from network due to error "Exception from HRESULT: 0xC0C01662""</span></span>  
  
<span data-ttu-id="8efea-134">**可能的原因**： 使用单向接收和双向发送端口，因此 BizTalk 没有相应的接收端口，以返回从双向发送端口收到的消息。</span><span class="sxs-lookup"><span data-stu-id="8efea-134">**Possible cause** : You are using 1-way receive and 2-way send port, so BizTalk does not have a corresponding Receive port to return the message received from the 2-way Send port.</span></span>  
  
<span data-ttu-id="8efea-135">**解析**： 这是设计使然，并且你可以忽略该错误消息。</span><span class="sxs-lookup"><span data-stu-id="8efea-135">**Resolution** : This is by design, and you can ignore the error message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8efea-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8efea-136">See Also</span></span>  
[<span data-ttu-id="8efea-137">在 HL7 疑难解答和已知问题</span><span class="sxs-lookup"><span data-stu-id="8efea-137">Troubleshooting and known issues in HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)