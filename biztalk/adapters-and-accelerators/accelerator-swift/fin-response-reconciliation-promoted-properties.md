---
title: FIN 响应对帐的已提升属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- promoted properties, FIN Response Reconciliation
- FIN Response Reconciliation, promoted properties
ms.assetid: 1a638e9e-61eb-482c-8856-b1aea36c449c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23d1460163b67618c3f7e15f1c8bd14ecdd97556
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377878"
---
# <a name="fin-response-reconciliation-promoted-properties"></a><span data-ttu-id="8f7f3-102">FIN 响应对帐的已提升属性</span><span class="sxs-lookup"><span data-stu-id="8f7f3-102">FIN Response Reconciliation Promoted Properties</span></span>
<span data-ttu-id="8f7f3-103">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN 响应对帐功能包括以下升级的属性。</span><span class="sxs-lookup"><span data-stu-id="8f7f3-103">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN Response Reconciliation feature includes the following promoted properties.</span></span>  
  
|<span data-ttu-id="8f7f3-104">升级的名称</span><span class="sxs-lookup"><span data-stu-id="8f7f3-104">Promoted name</span></span>|<span data-ttu-id="8f7f3-105">Description</span><span class="sxs-lookup"><span data-stu-id="8f7f3-105">Description</span></span>|<span data-ttu-id="8f7f3-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="8f7f3-106">Data type</span></span>|<span data-ttu-id="8f7f3-107">值范围</span><span class="sxs-lookup"><span data-stu-id="8f7f3-107">Value range</span></span>|<span data-ttu-id="8f7f3-108">用法示例</span><span class="sxs-lookup"><span data-stu-id="8f7f3-108">Usage example</span></span>|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|<span data-ttu-id="8f7f3-109">**A4SWIFT_FRRFailed**</span><span class="sxs-lookup"><span data-stu-id="8f7f3-109">**A4SWIFT_FRRFailed**</span></span>|<span data-ttu-id="8f7f3-110">主要消息发送时，在负方案中升级此属性。</span><span class="sxs-lookup"><span data-stu-id="8f7f3-110">This property is promoted in a negative scenario when sending out the main message.</span></span>|<span data-ttu-id="8f7f3-111">Boolean</span><span class="sxs-lookup"><span data-stu-id="8f7f3-111">Boolean</span></span>|<span data-ttu-id="8f7f3-112">True</span><span class="sxs-lookup"><span data-stu-id="8f7f3-112">True</span></span><br /><br /> <span data-ttu-id="8f7f3-113">False</span><span class="sxs-lookup"><span data-stu-id="8f7f3-113">False</span></span>|<span data-ttu-id="8f7f3-114">FRR 发送端口的筛选器表达式中用于将失败的消息发送到自定义处理程序。</span><span class="sxs-lookup"><span data-stu-id="8f7f3-114">Used in the filter expression of an FRR send port to send a failed message to a custom handler.</span></span>|  
|<span data-ttu-id="8f7f3-115">**A4SWIFT_FrrFailedReason**</span><span class="sxs-lookup"><span data-stu-id="8f7f3-115">**A4SWIFT_FrrFailedReason**</span></span>|<span data-ttu-id="8f7f3-116">指示未成功处理原始消息，通过 SAA/SWIFT。</span><span class="sxs-lookup"><span data-stu-id="8f7f3-116">Indicates that the original message was not successfully processed by SAA/SWIFT.</span></span>|<span data-ttu-id="8f7f3-117">String</span><span class="sxs-lookup"><span data-stu-id="8f7f3-117">String</span></span>|<span data-ttu-id="8f7f3-118">-   \<NAKErrorCode\></span><span class="sxs-lookup"><span data-stu-id="8f7f3-118">-   \<NAKErrorCode\></span></span><br /><span data-ttu-id="8f7f3-119">-   TimedOut</span><span class="sxs-lookup"><span data-stu-id="8f7f3-119">-   TimedOut</span></span><br /><span data-ttu-id="8f7f3-120">-TransportError</span><span class="sxs-lookup"><span data-stu-id="8f7f3-120">-   TransportError</span></span><br /><span data-ttu-id="8f7f3-121">-   Delayed_NAK</span><span class="sxs-lookup"><span data-stu-id="8f7f3-121">-   Delayed_NAK</span></span><br /><span data-ttu-id="8f7f3-122">-   AbortReceived</span><span class="sxs-lookup"><span data-stu-id="8f7f3-122">-   AbortReceived</span></span>|<span data-ttu-id="8f7f3-123">FRR 发送端口的筛选器表达式中用于将失败的消息发送到自定义处理程序。</span><span class="sxs-lookup"><span data-stu-id="8f7f3-123">Used in the filter expression of an FRR send port to send a failed message to a custom handler.</span></span>|  
|<span data-ttu-id="8f7f3-124">**A4SWIFT_FRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="8f7f3-124">**A4SWIFT_FRRCorrelationToken**</span></span>|<span data-ttu-id="8f7f3-125">指示唯一相关标记的出站 MT*xxx*消息。</span><span class="sxs-lookup"><span data-stu-id="8f7f3-125">Indicates the unique correlation token of the outbound MT*xxx* message.</span></span>|<span data-ttu-id="8f7f3-126">String</span><span class="sxs-lookup"><span data-stu-id="8f7f3-126">String</span></span>|-|<span data-ttu-id="8f7f3-127">FRR 将此属性设置为进行比较**MQMD_CorrelID** FIN 响应上下文属性。</span><span class="sxs-lookup"><span data-stu-id="8f7f3-127">FRR compares this property to the **MQMD_CorrelID** context property of the FIN response.</span></span>|  
|<span data-ttu-id="8f7f3-128">**A4SWIFT_SendingServiceType**</span><span class="sxs-lookup"><span data-stu-id="8f7f3-128">**A4SWIFT_SendingServiceType**</span></span>|<span data-ttu-id="8f7f3-129">指示发送该消息的 FRR 服务。</span><span class="sxs-lookup"><span data-stu-id="8f7f3-129">Indicates the FRR service that sends the message.</span></span>|<span data-ttu-id="8f7f3-130">String</span><span class="sxs-lookup"><span data-stu-id="8f7f3-130">String</span></span>|<span data-ttu-id="8f7f3-131">A4SWIFT_FrrService</span><span class="sxs-lookup"><span data-stu-id="8f7f3-131">A4SWIFT_FrrService</span></span>|<span data-ttu-id="8f7f3-132">升级时**A4SWIFT_FRRFailed**设置为 True。</span><span class="sxs-lookup"><span data-stu-id="8f7f3-132">Promoted when **A4SWIFT_FRRFailed** is set to True.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f7f3-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f7f3-133">See Also</span></span>  
 <span data-ttu-id="8f7f3-134">[A4SWIFT_ \* 的已提升属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md) </span><span class="sxs-lookup"><span data-stu-id="8f7f3-134">[A4SWIFT_\* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md) </span></span>  
 [<span data-ttu-id="8f7f3-135">消息回复和新提交的已提升属性</span><span class="sxs-lookup"><span data-stu-id="8f7f3-135">Message Repair and New Submission Promoted Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-promoted-properties.md)