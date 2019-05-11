---
title: 处理传入批 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 98f47903-933a-4bde-b320-f7689c3d8366
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6a7b40401623a867d706d82c50eb150a84a9eff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299813"
---
# <a name="processing-incoming-batches"></a><span data-ttu-id="e8409-102">处理传入批</span><span class="sxs-lookup"><span data-stu-id="e8409-102">Processing Incoming Batches</span></span>
<span data-ttu-id="e8409-103">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收批处理的 EDI 交换，它可以将交换拆分为单独处理每个其事务集，也可以保留交换，处理所有事务集作为一个组。</span><span class="sxs-lookup"><span data-stu-id="e8409-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a batched EDI interchange, it can either split the interchange into its transaction sets, processing each one separately, or it can preserve the interchange, processing all transaction sets as a group.</span></span>  
  
 <span data-ttu-id="e8409-104">确定批处理**本地主机设置**页中的单向协议选项卡**协议属性**针对 X12 和 EDIFACT 协议的对话框。</span><span class="sxs-lookup"><span data-stu-id="e8409-104">You determine batch processing in the **Local Host Settings** page of the one-way agreement tabs in the **Agreement Properties** dialog box for both X12 and EDIFACT agreements.</span></span> <span data-ttu-id="e8409-105">保留交换时，必须选择出错时挂起交换或事务集。</span><span class="sxs-lookup"><span data-stu-id="e8409-105">When you preserve the interchange, you have the choice to suspend either the interchange or the transaction sets if an error occurs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8409-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="e8409-106">In This Section</span></span>  
  
-   [<span data-ttu-id="e8409-107">拆分成批 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="e8409-107">Splitting a Batched EDI Interchange</span></span>](../core/splitting-a-batched-edi-interchange.md)  
  
-   [<span data-ttu-id="e8409-108">拆分 HIPAA 子文档</span><span class="sxs-lookup"><span data-stu-id="e8409-108">Splitting HIPAA Subdocuments</span></span>](../core/splitting-hipaa-subdocuments.md)  
  
-   [<span data-ttu-id="e8409-109">保留收到的批处理 EDI 交换</span><span class="sxs-lookup"><span data-stu-id="e8409-109">Preserving a Received Batched EDI Interchange</span></span>](../core/preserving-a-received-batched-edi-interchange.md)