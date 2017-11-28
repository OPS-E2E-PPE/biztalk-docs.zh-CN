---
title: "FIN 响应对帐提升属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- promoted properties, FIN Response Reconciliation
- FIN Response Reconciliation, promoted properties
ms.assetid: 1a638e9e-61eb-482c-8856-b1aea36c449c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14a3e3a004dcb9e58abde08345352c02f0914801
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-reconciliation-promoted-properties"></a><span data-ttu-id="dcabe-102">FIN 响应对帐升级的属性</span><span class="sxs-lookup"><span data-stu-id="dcabe-102">FIN Response Reconciliation Promoted Properties</span></span>
<span data-ttu-id="dcabe-103">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN 响应对帐功能包括以下提升的属性。</span><span class="sxs-lookup"><span data-stu-id="dcabe-103">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN Response Reconciliation feature includes the following promoted properties.</span></span>  
  
|<span data-ttu-id="dcabe-104">提升的名称</span><span class="sxs-lookup"><span data-stu-id="dcabe-104">Promoted name</span></span>|<span data-ttu-id="dcabe-105">Description</span><span class="sxs-lookup"><span data-stu-id="dcabe-105">Description</span></span>|<span data-ttu-id="dcabe-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="dcabe-106">Data type</span></span>|<span data-ttu-id="dcabe-107">值范围</span><span class="sxs-lookup"><span data-stu-id="dcabe-107">Value range</span></span>|<span data-ttu-id="dcabe-108">用法示例</span><span class="sxs-lookup"><span data-stu-id="dcabe-108">Usage example</span></span>|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|<span data-ttu-id="dcabe-109">**A4SWIFT_FRRFailed**</span><span class="sxs-lookup"><span data-stu-id="dcabe-109">**A4SWIFT_FRRFailed**</span></span>|<span data-ttu-id="dcabe-110">发送出主消息时，此属性提升负方案中。</span><span class="sxs-lookup"><span data-stu-id="dcabe-110">This property is promoted in a negative scenario when sending out the main message.</span></span>|<span data-ttu-id="dcabe-111">Boolean</span><span class="sxs-lookup"><span data-stu-id="dcabe-111">Boolean</span></span>|<span data-ttu-id="dcabe-112">True</span><span class="sxs-lookup"><span data-stu-id="dcabe-112">True</span></span><br /><br /> <span data-ttu-id="dcabe-113">False</span><span class="sxs-lookup"><span data-stu-id="dcabe-113">False</span></span>|<span data-ttu-id="dcabe-114">FRR 发送端口的筛选器表达式中用于将失败的消息发送到自定义处理程序。</span><span class="sxs-lookup"><span data-stu-id="dcabe-114">Used in the filter expression of an FRR send port to send a failed message to a custom handler.</span></span>|  
|<span data-ttu-id="dcabe-115">**A4SWIFT_FrrFailedReason**</span><span class="sxs-lookup"><span data-stu-id="dcabe-115">**A4SWIFT_FrrFailedReason**</span></span>|<span data-ttu-id="dcabe-116">指示原始消息已不成功的方式处理 SAA/SWIFT。</span><span class="sxs-lookup"><span data-stu-id="dcabe-116">Indicates that the original message was not successfully processed by SAA/SWIFT.</span></span>|<span data-ttu-id="dcabe-117">字符串</span><span class="sxs-lookup"><span data-stu-id="dcabe-117">String</span></span>|<span data-ttu-id="dcabe-118">-   \<NAKErrorCode ></span><span class="sxs-lookup"><span data-stu-id="dcabe-118">-   \<NAKErrorCode></span></span><br /><span data-ttu-id="dcabe-119">-超时</span><span class="sxs-lookup"><span data-stu-id="dcabe-119">-   TimedOut</span></span><br /><span data-ttu-id="dcabe-120">-TransportError</span><span class="sxs-lookup"><span data-stu-id="dcabe-120">-   TransportError</span></span><br /><span data-ttu-id="dcabe-121">-Delayed_NAK</span><span class="sxs-lookup"><span data-stu-id="dcabe-121">-   Delayed_NAK</span></span><br /><span data-ttu-id="dcabe-122">-AbortReceived</span><span class="sxs-lookup"><span data-stu-id="dcabe-122">-   AbortReceived</span></span>|<span data-ttu-id="dcabe-123">FRR 发送端口的筛选器表达式中用于将失败的消息发送到自定义处理程序。</span><span class="sxs-lookup"><span data-stu-id="dcabe-123">Used in the filter expression of an FRR send port to send a failed message to a custom handler.</span></span>|  
|<span data-ttu-id="dcabe-124">**A4SWIFT_FRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="dcabe-124">**A4SWIFT_FRRCorrelationToken**</span></span>|<span data-ttu-id="dcabe-125">指示唯一相关标记的出站 MT*xxx*消息。</span><span class="sxs-lookup"><span data-stu-id="dcabe-125">Indicates the unique correlation token of the outbound MT*xxx* message.</span></span>|<span data-ttu-id="dcabe-126">字符串</span><span class="sxs-lookup"><span data-stu-id="dcabe-126">String</span></span>|-|<span data-ttu-id="dcabe-127">FRR 比较到此属性**MQMD_CorrelID** FIN 响应上下文属性。</span><span class="sxs-lookup"><span data-stu-id="dcabe-127">FRR compares this property to the **MQMD_CorrelID** context property of the FIN response.</span></span>|  
|<span data-ttu-id="dcabe-128">**A4SWIFT_SendingServiceType**</span><span class="sxs-lookup"><span data-stu-id="dcabe-128">**A4SWIFT_SendingServiceType**</span></span>|<span data-ttu-id="dcabe-129">指示 FRR 服务发送消息。</span><span class="sxs-lookup"><span data-stu-id="dcabe-129">Indicates the FRR service that sends the message.</span></span>|<span data-ttu-id="dcabe-130">字符串</span><span class="sxs-lookup"><span data-stu-id="dcabe-130">String</span></span>|<span data-ttu-id="dcabe-131">A4SWIFT_FrrService</span><span class="sxs-lookup"><span data-stu-id="dcabe-131">A4SWIFT_FrrService</span></span>|<span data-ttu-id="dcabe-132">提升时**A4SWIFT_FRRFailed**设置为 True。</span><span class="sxs-lookup"><span data-stu-id="dcabe-132">Promoted when **A4SWIFT_FRRFailed** is set to True.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dcabe-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcabe-133">See Also</span></span>  
 <span data-ttu-id="dcabe-134">[A4SWIFT_ * 提升属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md) </span><span class="sxs-lookup"><span data-stu-id="dcabe-134">[A4SWIFT_* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md) </span></span>  
 [<span data-ttu-id="dcabe-135">消息修复和新提交提升属性</span><span class="sxs-lookup"><span data-stu-id="dcabe-135">Message Repair and New Submission Promoted Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-promoted-properties.md)