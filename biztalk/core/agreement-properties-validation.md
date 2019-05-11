---
title: 协议属性验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d565c26-37ef-4aee-aebb-3152880242a1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38f03d5d504210d270e8892965bffa238ee49496
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359381"
---
# <a name="agreement-properties-validation"></a><span data-ttu-id="b9886-102">协议属性验证</span><span class="sxs-lookup"><span data-stu-id="b9886-102">Agreement Properties Validation</span></span>
<span data-ttu-id="b9886-103">协议属性包括对交换、组或事务集的重复控制编号的检查。</span><span class="sxs-lookup"><span data-stu-id="b9886-103">Agreement properties include checks for duplicate control numbers for interchanges, groups, or transaction sets.</span></span> <span data-ttu-id="b9886-104">只有在协议属性中启用这些验证，EDI 接收管道才会执行这些验证。</span><span class="sxs-lookup"><span data-stu-id="b9886-104">The EDI receive pipeline will perform these validations only if they are enabled in agreement properties.</span></span> <span data-ttu-id="b9886-105">这些验证包括：</span><span class="sxs-lookup"><span data-stu-id="b9886-105">These validations include:</span></span>  
  
-   <span data-ttu-id="b9886-106">检查重复的交换控制编号（X12 中的 ISA13 或 EDIFACT 中的 UNB5）。</span><span class="sxs-lookup"><span data-stu-id="b9886-106">Checking for a duplicate interchange control number (ISA13 in X12 or UNB5 in EDIFACT).</span></span> <span data-ttu-id="b9886-107">可以输入一个时间值（单位：天）来为此检查设置有效的时间范围。</span><span class="sxs-lookup"><span data-stu-id="b9886-107">You enter a time value (in days) to establish the valid time range for this check.</span></span>  
  
-   <span data-ttu-id="b9886-108">检查交换中的重复组控制编号（X12 中的 GS6 或 EDIFACT 中的 UNG5）</span><span class="sxs-lookup"><span data-stu-id="b9886-108">Checking for a duplicate group control number in an interchange (GS6 in X12 or UNG5 in EDIFACT)</span></span>  
  
-   <span data-ttu-id="b9886-109">检查功能组中的重复事务集控制编号（X12 中的 ST2 或 EDIFACT 中的 UNH1）</span><span class="sxs-lookup"><span data-stu-id="b9886-109">Checking for a duplicate transaction set control number in a functional group (ST2 in X12 or UNH1 in EDIFACT)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9886-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9886-110">See Also</span></span>  
 [<span data-ttu-id="b9886-111">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="b9886-111">EDI Message Validation</span></span>](../core/edi-message-validation.md)