---
title: Edifact 交换应具有包含 UNA 或作为第一条线段的 UNB |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43fd17-31d0-48df-93cd-524b40034764
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e673df728dea00852e9713aed12f8ced902a4fdc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240029"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a><span data-ttu-id="65277-102">EDIFACT 交换应该包含 UNA 或 UNB 作为第一个段</span><span class="sxs-lookup"><span data-stu-id="65277-102">Edifact interchange should have contained UNA or UNB as the first segment</span></span>
## <a name="details"></a><span data-ttu-id="65277-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="65277-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="65277-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="65277-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="65277-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="65277-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="65277-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="65277-106">Event ID</span></span>|-|  
|<span data-ttu-id="65277-107">事件源</span><span class="sxs-lookup"><span data-stu-id="65277-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="65277-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="65277-108"> EDI</span></span>|  
|<span data-ttu-id="65277-109">组件</span><span class="sxs-lookup"><span data-stu-id="65277-109">Component</span></span>|<span data-ttu-id="65277-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="65277-110">EDI Engine</span></span>|  
|<span data-ttu-id="65277-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="65277-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="65277-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="65277-112">Message Text</span></span>|<span data-ttu-id="65277-113">Edifact 交换应该包含 UNA 或 UNB 作为第一个段。</span><span class="sxs-lookup"><span data-stu-id="65277-113">Edifact interchange should have contained UNA or UNB as the first segment.</span></span> <span data-ttu-id="65277-114">实际找到的是 {0}</span><span class="sxs-lookup"><span data-stu-id="65277-114">Instead {0} was found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="65277-115">解释</span><span class="sxs-lookup"><span data-stu-id="65277-115">Explanation</span></span>  
 <span data-ttu-id="65277-116">此错误/警告/信息事件指示 EDI 接收管道无法处理传入的 EDIFACT 交换，因为第一条线段 UNA 和 UNB 段都不。</span><span class="sxs-lookup"><span data-stu-id="65277-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the first segment was neither a UNA nor a UNB segment.</span></span> <span data-ttu-id="65277-117">UNA 段是可选的；UNB 段是必需的。</span><span class="sxs-lookup"><span data-stu-id="65277-117">The UNA segment is optional; the UNB segment is mandatory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="65277-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="65277-118">User Action</span></span>  
 <span data-ttu-id="65277-119">若要解决此错误，请确保交换的发送方包含 UNA 或 UNB 段作为交换的第一个段，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="65277-119">To resolve this error, ensure that the sender of the interchange includes the UNA or UNB segment as the first segment of the interchange, and then resends the interchange.</span></span>