---
title: 批处理的已知的问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, known issues
- known issues, batching
ms.assetid: 25c645eb-845d-483a-8f77-398e7dfe0c8f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae2c9fb3abf43d7eb62c0c78d03c30a33b45995c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251797"
---
# <a name="batching-known-issues"></a><span data-ttu-id="22e65-102">批处理的已知的问题</span><span class="sxs-lookup"><span data-stu-id="22e65-102">Batching Known Issues</span></span>
<span data-ttu-id="22e65-103">本部分包含可帮助你避免批处理错误的有用信息。</span><span class="sxs-lookup"><span data-stu-id="22e65-103">This section contains useful information that may help you avoid batching errors.</span></span>  
  
## <a name="batch-trailer-segment-fts-and-bts-fields-are-accepted-even-if-they-are-strings"></a><span data-ttu-id="22e65-104">即使它们是字符串接受批处理尾部段 （FTS 和 BTS） 字段</span><span class="sxs-lookup"><span data-stu-id="22e65-104">Batch trailer segment (FTS and BTS) fields are accepted even if they are strings</span></span>  
 <span data-ttu-id="22e65-105">HL7 中以不同的方式在各种版本的 HL7 FTS 和 BTS 段指定的字段。</span><span class="sxs-lookup"><span data-stu-id="22e65-105">HL7 specifies the fields in FTS and BTS segments differently in the various versions of HL7.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="22e65-106">所有字段定义为字符串数据类型，以避免出现不一致。</span><span class="sxs-lookup"><span data-stu-id="22e65-106">defines all of the fields as String data type to avoid inconsistency.</span></span>  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a><span data-ttu-id="22e65-107">数据类型的批处理消息的确认</span><span class="sxs-lookup"><span data-stu-id="22e65-107">Data type of an ACK to a batch message</span></span>  
 <span data-ttu-id="22e65-108">在为批处理消息，如果碎片源参与方已关闭，则 MSH10 响应中生成的确认 (ACK) 消息字段 (消息控件 ID) 将是一个 GUID，而不是任何其他数据类型的批处理消息中的 MSH10 字段。</span><span class="sxs-lookup"><span data-stu-id="22e65-108">In an acknowledgment (ACK) message generated in response to a batch message, if fragmentation for source party is turned off, then the MSH10 field (message control ID) will be a GUID, rather than any other data type of the MSH10 field in the batch message.</span></span>  
  
## <a name="btahl7-configuration-explorer-and-create-batch-orchestrations-are-not-two-way-synchronized"></a><span data-ttu-id="22e65-109">BTAHL7 配置资源管理器和创建批处理业务流程不是双向同步</span><span class="sxs-lookup"><span data-stu-id="22e65-109">BTAHL7 Configuration Explorer and Create Batch orchestrations are not two-way synchronized</span></span>  
 <span data-ttu-id="22e65-110">您可能无法查看批处理控制计划的当前状态，即使您按 F5 在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，并可能需要检查[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]当前的配置资源管理器和运行状况与活动跟踪 (HAT) 工具批处理控制计划的状态。</span><span class="sxs-lookup"><span data-stu-id="22e65-110">You may not able to view the current status of the batch control schedule even if you press F5 in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, and may have to check both [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and the Health and Activity Tracking (HAT) tool for the current status of the batch control schedule.</span></span>  
  
## <a name="two-parsing-errors-logged-when-messages-in-batch-inbatch-out-scenario-contain-validation-errors"></a><span data-ttu-id="22e65-111">两个分析错误记录时中的消息中批处理 / 出批处理方案包含验证错误</span><span class="sxs-lookup"><span data-stu-id="22e65-111">Two parsing errors logged when messages in Batch In/Batch Out scenario contain validation errors</span></span>  
 <span data-ttu-id="22e65-112">第一个批处理中的消息时在 / 批处理出方案 （多个消息批处理没有批处理标头） 包含验证错误，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]事件日志中记录两个错误。</span><span class="sxs-lookup"><span data-stu-id="22e65-112">When the first message in the Batch In/Batch Out scenario (multiple messages batched without batch headers) contains validation errors, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logs two errors in the Event Log.</span></span> <span data-ttu-id="22e65-113">第二个错误相关的消息的其余部分和与批处理中的第一个消息相关的第一个错误。</span><span class="sxs-lookup"><span data-stu-id="22e65-113">The first error pertains to the first message in the batch, and the second error pertains to the remainder of the messages.</span></span>  
  
## <a name="subscription-using-the-btsmessagetype-property-for-the-batch-inbatch-out-scenario-with-fragmentation-disabled-is-not-supported"></a><span data-ttu-id="22e65-114">使用 BTS 的订阅。MessageType 属性批处理中不支持批处理出方案具有禁用的碎片</span><span class="sxs-lookup"><span data-stu-id="22e65-114">Subscription using the BTS.MessageType property for the Batch In/Batch Out scenario with fragmentation disabled is not supported</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="22e65-115">不支持订阅使用**BTS。MessageType**属性批处理中 / 出站批处理方案与碎片可能包含多个消息类型的交换中禁用。</span><span class="sxs-lookup"><span data-stu-id="22e65-115">does not support subscription using the **BTS.MessageType** property for the Batch In/Batch Out scenario with fragmentation disabled as an interchange that may consist of multiple message types.</span></span>  
  
## <a name="entire-batch-suspended-after-erroneous-message-in-the-batch-inbatch-out-scenario"></a><span data-ttu-id="22e65-116">在批处理中的错误消息后挂起整个批次中 / 出站批处理方案</span><span class="sxs-lookup"><span data-stu-id="22e65-116">Entire batch suspended after erroneous message in the Batch In/Batch Out scenario</span></span>  
 <span data-ttu-id="22e65-117">如果具有致命分析器错误的消息 (例如， [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] MSH 9 或加载失败的消息的 MSH 12 或正文架构未分析) 时遇到的零碎的批处理中 / Batch 扩展方案中，甚至是挂起的错误消息后的任何数据如果已启用可恢复的交换的支持。</span><span class="sxs-lookup"><span data-stu-id="22e65-117">If a message with fatal parser errors (for example, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not parse MSH 9 or MSH 12 or body schema for the message failed to load) is encountered in a fragmented Batch In/Batch Out scenario, any data after the erroneous message is suspended even if the recoverable interchange support has been enabled.</span></span>  
  
## <a name="batch-of-acks-get-routed-to-the-source-party-of-the-first-message-in-batch-inbatch-out-scenario"></a><span data-ttu-id="22e65-118">批处理确认路由到批处理中的第一个消息的源参与方中 / 出站批处理方案</span><span class="sxs-lookup"><span data-stu-id="22e65-118">Batch of Acks get routed to the source party of the first message in Batch In/Batch Out Scenario</span></span>  
 <span data-ttu-id="22e65-119">在批处理中 / 方案批处理确认的批处理出获取根据路由源参与方信息的第一条消息，因为此功能假定为入站中的所有消息进行都批处理的源和目标参与方都相同。</span><span class="sxs-lookup"><span data-stu-id="22e65-119">In Batch In/ Batch Out scenario batch of Acks get routed based on the source party information of the first message, because this functionality assume that for all the messages in inbound batch the source and destination parties are same.</span></span>  
  
## <a name="batch-of-acks-does-not-get-routed-to-the-source-party-when-two-way-receive-port-is-used-in-batch-in-batch-out-scenario"></a><span data-ttu-id="22e65-120">确认的批处理不会不会路由至源参与方时双向接收端口可在批处理中 / 出站批处理方案</span><span class="sxs-lookup"><span data-stu-id="22e65-120">Batch of Acks does not get routed to the source party when two-way receive port is used in Batch In/ Batch Out scenario</span></span>  
 <span data-ttu-id="22e65-121">对于请求-响应接收的端口 ACK/NACK 批处理不会不会路由至 BIBO 方案的源参与方。</span><span class="sxs-lookup"><span data-stu-id="22e65-121">In case of request-response receive port the ACK/NACK batch does not get routed to the source party for BIBO scenario.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e65-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="22e65-122">See Also</span></span>  
 [<span data-ttu-id="22e65-123">已知问题</span><span class="sxs-lookup"><span data-stu-id="22e65-123">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)