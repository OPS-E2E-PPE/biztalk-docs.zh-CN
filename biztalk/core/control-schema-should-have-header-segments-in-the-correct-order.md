---
title: "控制架构应具有正确的顺序中的标头段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88f38e8f-243a-467f-84bd-a232ef148b4b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3362bce20e1e7d31fa870a5376128d2d721c11f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="control-schema-should-have-header-segments-in-the-correct-order"></a><span data-ttu-id="90188-102">控制架构标头段的顺序应正确</span><span class="sxs-lookup"><span data-stu-id="90188-102">Control schema should have header segments in the correct order</span></span>
## <a name="details"></a><span data-ttu-id="90188-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="90188-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="90188-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="90188-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="90188-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="90188-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="90188-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="90188-106">Event ID</span></span>|-|  
|<span data-ttu-id="90188-107">事件源</span><span class="sxs-lookup"><span data-stu-id="90188-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="90188-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="90188-108"> EDI</span></span>|  
|<span data-ttu-id="90188-109">组件</span><span class="sxs-lookup"><span data-stu-id="90188-109">Component</span></span>|<span data-ttu-id="90188-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="90188-110">EDI Engine</span></span>|  
|<span data-ttu-id="90188-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="90188-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="90188-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="90188-112">Message Text</span></span>|<span data-ttu-id="90188-113">控制架构应按以下顺序具有段： ISA GS ST...SE GE IEA</span><span class="sxs-lookup"><span data-stu-id="90188-113">Control schema should have segments in the following order: ISA GS ST .... SE GE IEA</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="90188-114">解释</span><span class="sxs-lookup"><span data-stu-id="90188-114">Explanation</span></span>  
 <span data-ttu-id="90188-115">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的交换，因为交换的标头和尾部、组和事务集在交换中的顺序不正确。</span><span class="sxs-lookup"><span data-stu-id="90188-115">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming interchange because the headers and trailers for the interchange, groups, and transaction sets were not in the correct order in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="90188-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="90188-116">User Action</span></span>  
 <span data-ttu-id="90188-117">若要解决此错误，请确保 ISA、GS 和 ST 标头以及 SE、GE 和 IEA 尾部在交换中的顺序正确，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="90188-117">To resolve this error, ensure that the ISA, GS, and ST headers, and the SE, GE, and IEA trailers, are in the correct order in the interchange, and then resend the interchange.</span></span>