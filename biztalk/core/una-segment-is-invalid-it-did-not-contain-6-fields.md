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
ms.openlocfilehash: 7aaa5714a3063ba5039c042fb24c5c6a9a28f7d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258660"
---
# <a name="una-segment-is-invalid-it-did-not-contain-6-fields"></a><span data-ttu-id="448d5-103">UNA 段无效。</span><span class="sxs-lookup"><span data-stu-id="448d5-103">UNA segment is invalid.</span></span> <span data-ttu-id="448d5-104">它不包含 6 个字段</span><span class="sxs-lookup"><span data-stu-id="448d5-104">It did not contain 6 fields</span></span>
## <a name="details"></a><span data-ttu-id="448d5-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="448d5-105">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="448d5-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="448d5-106">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="448d5-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="448d5-107">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="448d5-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="448d5-108">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="448d5-109">事件源</span><span class="sxs-lookup"><span data-stu-id="448d5-109">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="448d5-110">EDI</span><span class="sxs-lookup"><span data-stu-id="448d5-110">EDI</span></span> |
|    <span data-ttu-id="448d5-111">组件</span><span class="sxs-lookup"><span data-stu-id="448d5-111">Component</span></span>    |                                       <span data-ttu-id="448d5-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="448d5-112">EDI Engine</span></span>                                       |
|  <span data-ttu-id="448d5-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="448d5-113">Symbolic Name</span></span>  |                             <span data-ttu-id="448d5-114">UnaDidNotContainSixDelimiters</span><span class="sxs-lookup"><span data-stu-id="448d5-114">UnaDidNotContainSixDelimiters</span></span>                              |
|  <span data-ttu-id="448d5-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="448d5-115">Message Text</span></span>   |                  <span data-ttu-id="448d5-116">UNA 段无效。</span><span class="sxs-lookup"><span data-stu-id="448d5-116">UNA segment is invalid.</span></span> <span data-ttu-id="448d5-117">它不包含 6 个字段</span><span class="sxs-lookup"><span data-stu-id="448d5-117">It did not contain 6 fields</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="448d5-118">解释</span><span class="sxs-lookup"><span data-stu-id="448d5-118">Explanation</span></span>  
 <span data-ttu-id="448d5-119">此错误/警告/信息事件表明接收管道无法处理传入的 EDIFACT 交换，因为 UNA 段包含的数据元素少于 6 个。</span><span class="sxs-lookup"><span data-stu-id="448d5-119">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming EDIFACT interchange because the UNA segment contained fewer than six data elements.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="448d5-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="448d5-120">User Action</span></span>  
 <span data-ttu-id="448d5-121">若要解决此错误，请让交换的发送方确保 UNA 段包含 6 个数据元素，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="448d5-121">To resolve this error, have the sender of the interchange make sure that the UNA segment contains six data elements, and then resend the interchange.</span></span>