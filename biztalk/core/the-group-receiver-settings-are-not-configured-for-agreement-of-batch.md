---
title: 未批处理的协议配置组接收器设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57b205e9-aaab-43d1-b373-17d206957814
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 534d426d192e27bbe7c6c7e866399b42360a8e3a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990638"
---
# <a name="the-group-receiver-settings-are-not-configured-for-agreement-of-batch"></a><span data-ttu-id="0b3bf-102">未针对批协议配置组接收器设置</span><span class="sxs-lookup"><span data-stu-id="0b3bf-102">The group receiver settings are not configured for agreement of batch</span></span>
## <a name="details"></a><span data-ttu-id="0b3bf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0b3bf-103">Details</span></span>  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0b3bf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0b3bf-104">Product Name</span></span>   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| <span data-ttu-id="0b3bf-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0b3bf-105">Product Version</span></span> |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    <span data-ttu-id="0b3bf-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0b3bf-106">Event ID</span></span>     |                                                                  -                                                                  |
|  <span data-ttu-id="0b3bf-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0b3bf-107">Event Source</span></span>   |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0b3bf-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0b3bf-108"> EDI</span></span>                        |
|    <span data-ttu-id="0b3bf-109">组件</span><span class="sxs-lookup"><span data-stu-id="0b3bf-109">Component</span></span>    |                                                           <span data-ttu-id="0b3bf-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="0b3bf-110">Batching Engine</span></span>                                                           |
|  <span data-ttu-id="0b3bf-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0b3bf-111">Symbolic Name</span></span>  |                                                      <span data-ttu-id="0b3bf-112">GroupReceiverNotSelected</span><span class="sxs-lookup"><span data-stu-id="0b3bf-112">GroupReceiverNotSelected</span></span>                                                       |
|  <span data-ttu-id="0b3bf-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0b3bf-113">Message Text</span></span>   | <span data-ttu-id="0b3bf-114">未批处理的协议配置组接收器设置{0}。</span><span class="sxs-lookup"><span data-stu-id="0b3bf-114">The group receiver settings are not configured for agreement of batch {0}.</span></span> <span data-ttu-id="0b3bf-115">需要先完成此设置才能进行批处理。</span><span class="sxs-lookup"><span data-stu-id="0b3bf-115">This needs to be configured before batching can proceed.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0b3bf-116">解释</span><span class="sxs-lookup"><span data-stu-id="0b3bf-116">Explanation</span></span>  
 <span data-ttu-id="0b3bf-117">此错误/警告/信息事件表明发生了以下两种情况之一：</span><span class="sxs-lookup"><span data-stu-id="0b3bf-117">This Error/Warning/Information event indicates that one of two conditions has occurred:</span></span>  
  
-   <span data-ttu-id="0b3bf-118">批处理业务流程无法验证其已接收的批处理元素，因为没有设置包含编码语法的 UNB1.1 字段（对于 EDIFACT 编码的交换）。</span><span class="sxs-lookup"><span data-stu-id="0b3bf-118">The batching orchestration could not validate a batch element that it has received because the UNB1.1 field (for an EDIFACT-encoded interchange) that contains the encoding syntax was not set.</span></span>  
  
-   <span data-ttu-id="0b3bf-119">批处理业务流程无法为批处理元素创建信封设置，因为标头属性不完整（X12 交换的 ISA、GS 和 ST 属性，EDIFACT 交换的 UNA、UNB、UNG 和 UNH 属性）。</span><span class="sxs-lookup"><span data-stu-id="0b3bf-119">The batching orchestration could not create the envelope settings for the batch element because the header properties were not complete (ISA, GS, and ST properties for an X12 interchange or UNA, UNB, UNG, and UNH properties for an EDIFACT interchange).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b3bf-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="0b3bf-120">User Action</span></span>  
 <span data-ttu-id="0b3bf-121">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="0b3bf-121">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="0b3bf-122">如果批处理业务流程由于未设置编码语法而无法验证其已接收的批处理元素，请在“EDI 属性”对话框的“UNB 段定义”页中为 UNB1.1 字段设置编码语法。</span><span class="sxs-lookup"><span data-stu-id="0b3bf-122">If the batching orchestration could not validate a batch element that it has received because the encoding syntax was not set, set the encoding syntax for the UNB1.1 field in the UNB Segment Definition page of the EDI Properties dialog box.</span></span>  
  
-   <span data-ttu-id="0b3bf-123">如果批处理业务流程由于标头属性不完整而无法为批处理元素创建信封设置，请确保设置 X12 交换的 ISA、GS 和 ST 属性，或者设置 EDIFACT 交换的 UNA、UNB、UNG 和 UNH 属性。</span><span class="sxs-lookup"><span data-stu-id="0b3bf-123">If the batching orchestration could not create the envelope settings for the batch element because the header properties were not complete, ensure that the ISA, GS, and ST properties for an X12 interchange are set or that the UNA, UNB, UNG, and UNH properties for an EDIFACT interchange are set.</span></span>