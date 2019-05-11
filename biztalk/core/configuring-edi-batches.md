---
title: 配置 EDI 批 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8be06e5c-603a-4f93-b018-105314666157
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d4ce3d926526b7b7fe17011d30d555566de7cb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355919"
---
# <a name="configuring-edi-batches"></a><span data-ttu-id="b4378-102">配置 EDI 批</span><span class="sxs-lookup"><span data-stu-id="b4378-102">Configuring EDI Batches</span></span>
<span data-ttu-id="b4378-103">在本部分中的主题介绍如何接收拆分或保留批的交换、 如何通过 XML 管道发送保留的交换以及如何实现外部批处理发布机制。</span><span class="sxs-lookup"><span data-stu-id="b4378-103">The topics in this section describe how to receive a split or preserved batched interchange, how to send a preserved interchange over an XML pipeline, and how to implement an external batch release mechanism.</span></span>  
  
 <span data-ttu-id="b4378-104">在本部分中的主题不包含有关如何成批发送交换的信息。</span><span class="sxs-lookup"><span data-stu-id="b4378-104">The topics in this section do not contain information on how to send interchanges in batches.</span></span> <span data-ttu-id="b4378-105">有关如何进行批处理传出交换的详细信息，请参阅[配置批处理 (X12)](../core/configuring-batching-x12.md) （对于 X12 编码的消息） 或[配置批处理 (EDIFACT)](../core/configuring-batching-edifact.md) （对于 EDIFACT 编码的消息）。</span><span class="sxs-lookup"><span data-stu-id="b4378-105">For more information on how to batch outgoing interchanges, see [Configuring Batching (X12)](../core/configuring-batching-x12.md) (for X12 encoded messages) or [Configuring Batching (EDIFACT)](../core/configuring-batching-edifact.md) (for EDIFACT encoded messages).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b4378-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="b4378-106">In This Section</span></span>  
  
-   [<span data-ttu-id="b4378-107">拆分批处理的交换</span><span class="sxs-lookup"><span data-stu-id="b4378-107">Splitting a Batched Interchange</span></span>](../core/splitting-a-batched-interchange.md)  
  
-   [<span data-ttu-id="b4378-108">保留批处理的交换</span><span class="sxs-lookup"><span data-stu-id="b4378-108">Preserving a Batched Interchange</span></span>](../core/preserving-a-batched-interchange.md)  
  
-   [<span data-ttu-id="b4378-109">使用 XML 发送管道发送保留批</span><span class="sxs-lookup"><span data-stu-id="b4378-109">Sending a Preserved Batch with an XML Send Pipeline</span></span>](../core/sending-a-preserved-batch-with-an-xml-send-pipeline.md)  
  
-   [<span data-ttu-id="b4378-110">实现外部批发布机制</span><span class="sxs-lookup"><span data-stu-id="b4378-110">Implementing an External Batch Release Mechanism</span></span>](../core/implementing-an-external-batch-release-mechanism.md)  
  
-   [<span data-ttu-id="b4378-111">将传入事务集与传出批相关联</span><span class="sxs-lookup"><span data-stu-id="b4378-111">Correlating an Incoming Transaction Set with an Outgoing Batch</span></span>](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)  
  
## <a name="see-also"></a><span data-ttu-id="b4378-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4378-112">See Also</span></span>  
 [<span data-ttu-id="b4378-113">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="b4378-113">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)