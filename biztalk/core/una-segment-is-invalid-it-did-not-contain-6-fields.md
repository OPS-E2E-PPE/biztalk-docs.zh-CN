---
title: UNA 段无效。 它不包含 6 个字段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c939d8d3-e6fb-4505-836d-31559fc5f1a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 469ce2e3d8b82b876053df93bb66fbea0ec1354f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001686"
---
# <a name="una-segment-is-invalid-it-did-not-contain-6-fields"></a><span data-ttu-id="e06e8-103">UNA 段无效。</span><span class="sxs-lookup"><span data-stu-id="e06e8-103">UNA segment is invalid.</span></span> <span data-ttu-id="e06e8-104">它不包含 6 个字段</span><span class="sxs-lookup"><span data-stu-id="e06e8-104">It did not contain 6 fields</span></span>
## <a name="details"></a><span data-ttu-id="e06e8-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="e06e8-105">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e06e8-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="e06e8-106">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e06e8-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="e06e8-107">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e06e8-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e06e8-108">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e06e8-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e06e8-109">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e06e8-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="e06e8-110"> EDI</span></span> |
|    <span data-ttu-id="e06e8-111">组件</span><span class="sxs-lookup"><span data-stu-id="e06e8-111">Component</span></span>    |                                       <span data-ttu-id="e06e8-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e06e8-112">EDI Engine</span></span>                                       |
|  <span data-ttu-id="e06e8-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e06e8-113">Symbolic Name</span></span>  |                             <span data-ttu-id="e06e8-114">UnaDidNotContainSixDelimiters</span><span class="sxs-lookup"><span data-stu-id="e06e8-114">UnaDidNotContainSixDelimiters</span></span>                              |
|  <span data-ttu-id="e06e8-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e06e8-115">Message Text</span></span>   |                  <span data-ttu-id="e06e8-116">UNA 段无效。</span><span class="sxs-lookup"><span data-stu-id="e06e8-116">UNA segment is invalid.</span></span> <span data-ttu-id="e06e8-117">它不包含 6 个字段</span><span class="sxs-lookup"><span data-stu-id="e06e8-117">It did not contain 6 fields</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="e06e8-118">解释</span><span class="sxs-lookup"><span data-stu-id="e06e8-118">Explanation</span></span>  
 <span data-ttu-id="e06e8-119">此错误/警告/信息事件表明接收管道无法处理传入的 EDIFACT 交换，因为 UNA 段包含的数据元素少于 6 个。</span><span class="sxs-lookup"><span data-stu-id="e06e8-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange because the UNA segment contained fewer than six data elements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e06e8-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="e06e8-120">User Action</span></span>  
 <span data-ttu-id="e06e8-121">若要解决此错误，请让交换的发送方确保 UNA 段包含 6 个数据元素，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="e06e8-121">To resolve this error, have the sender of the interchange make sure that the UNA segment contains six data elements, and then resend the interchange.</span></span>