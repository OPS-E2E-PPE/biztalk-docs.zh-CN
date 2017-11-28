---
title: "处理传入的批次 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98f47903-933a-4bde-b320-f7689c3d8366
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca3781d9b7c1ed2190a8334f272c04d304669ace
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-incoming-batches"></a><span data-ttu-id="7f3d1-102">处理传入批</span><span class="sxs-lookup"><span data-stu-id="7f3d1-102">Processing Incoming Batches</span></span>
<span data-ttu-id="7f3d1-103">当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到批处理 EDI 交换时，它可以将交换拆分为事务集，然后对每一个事务集分别加以处理，也可以保留交换，将所有事务集作为一个组进行处理。</span><span class="sxs-lookup"><span data-stu-id="7f3d1-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a batched EDI interchange, it can either split the interchange into its transaction sets, processing each one separately, or it can preserve the interchange, processing all transaction sets as a group.</span></span>  
  
 <span data-ttu-id="7f3d1-104">确定在批处理**本地主机设置**页中的单向协议选项卡**协议属性**X12 和 EDIFACT 协议的对话框。</span><span class="sxs-lookup"><span data-stu-id="7f3d1-104">You determine batch processing in the **Local Host Settings** page of the one-way agreement tabs in the **Agreement Properties** dialog box for both X12 and EDIFACT agreements.</span></span> <span data-ttu-id="7f3d1-105">当保留交换时，如果出现错误，则可以选择挂起相应的交换或事务集。</span><span class="sxs-lookup"><span data-stu-id="7f3d1-105">When you preserve the interchange, you have the choice to suspend either the interchange or the transaction sets if an error occurs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f3d1-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="7f3d1-106">In This Section</span></span>  
  
-   [<span data-ttu-id="7f3d1-107">拆分批处理的 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="7f3d1-107">Splitting a Batched EDI Interchange</span></span>](../core/splitting-a-batched-edi-interchange.md)  
  
-   [<span data-ttu-id="7f3d1-108">拆分 HIPAA 子文档</span><span class="sxs-lookup"><span data-stu-id="7f3d1-108">Splitting HIPAA Subdocuments</span></span>](../core/splitting-hipaa-subdocuments.md)  
  
-   [<span data-ttu-id="7f3d1-109">保留已收到批处理的 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="7f3d1-109">Preserving a Received Batched EDI Interchange</span></span>](../core/preserving-a-received-batched-edi-interchange.md)