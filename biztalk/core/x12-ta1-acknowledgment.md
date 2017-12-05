---
title: "X12 TA1 确认 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68568a1a-3669-46f4-8edc-8d057b012544
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6a3de45744b40335999c1471165ff851ec60664
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="x12-ta1-acknowledgment"></a><span data-ttu-id="2b862-102">X12 TA1 确认</span><span class="sxs-lookup"><span data-stu-id="2b862-102">X12 TA1 Acknowledgment</span></span>
<span data-ttu-id="2b862-103">X12 TA1 技术确认通过地址接收方报告交换标头和尾部的处理状态。</span><span class="sxs-lookup"><span data-stu-id="2b862-103">The X12 TA1 technical acknowledgment reports the status of the processing of an interchange header and trailer by the address receiver.</span></span> <span data-ttu-id="2b862-104">无论其他内容的状态如何，当 X12 编码消息的 ISA 和 IEA 有效时，将会发送肯定的 TA1 确认。</span><span class="sxs-lookup"><span data-stu-id="2b862-104">When the ISA and IEA of the X12-encoded message are valid, a positive TA1 ACK is sent, whatever the status of the other content is.</span></span> <span data-ttu-id="2b862-105">否则，将发送带有错误代码的 TA1 确认。</span><span class="sxs-lookup"><span data-stu-id="2b862-105">If not, TA1 ACK with an error code is sent.</span></span>  
  
 <span data-ttu-id="2b862-106">X12 TA1 确认符合 X12_\<版本号\>_TA1.xsd 架构。</span><span class="sxs-lookup"><span data-stu-id="2b862-106">The X12 TA1 acknowledgment conforms to the X12_\<version number\>_TA1.xsd schema.</span></span> <span data-ttu-id="2b862-107">TA1 确认是在 ISA/IEA 信封内部发送的。</span><span class="sxs-lookup"><span data-stu-id="2b862-107">The TA1 ACK is sent inside an ISA/IEA envelope.</span></span> <span data-ttu-id="2b862-108">ISA 和 IEA 与其他任何交换没有任何区别。</span><span class="sxs-lookup"><span data-stu-id="2b862-108">The ISA and IEA are no different than any other interchange.</span></span>  
  
 <span data-ttu-id="2b862-109">下表显示了 TA1 确认交换内部的分段。</span><span class="sxs-lookup"><span data-stu-id="2b862-109">The segments within the interchange of a TA1 ACK are shown in the following table.</span></span>  
  
|<span data-ttu-id="2b862-110">TA1 中的字段</span><span class="sxs-lookup"><span data-stu-id="2b862-110">Field in TA1</span></span>|<span data-ttu-id="2b862-111">字段的名称</span><span class="sxs-lookup"><span data-stu-id="2b862-111">Name of Field</span></span>|<span data-ttu-id="2b862-112">映射到传入交换</span><span class="sxs-lookup"><span data-stu-id="2b862-112">Mapped to Incoming Interchange</span></span>|<span data-ttu-id="2b862-113">值</span><span class="sxs-lookup"><span data-stu-id="2b862-113">Value</span></span>|  
|------------------|-------------------|------------------------------------|-----------|  
|<span data-ttu-id="2b862-114">TA101</span><span class="sxs-lookup"><span data-stu-id="2b862-114">TA101</span></span>|<span data-ttu-id="2b862-115">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="2b862-115">Interchange control number</span></span>|<span data-ttu-id="2b862-116">ISA13 - 交换控制编号</span><span class="sxs-lookup"><span data-stu-id="2b862-116">ISA13 - Interchange control number</span></span>|-|  
|<span data-ttu-id="2b862-117">TA102</span><span class="sxs-lookup"><span data-stu-id="2b862-117">TA102</span></span>|<span data-ttu-id="2b862-118">交换日期</span><span class="sxs-lookup"><span data-stu-id="2b862-118">Interchange Date</span></span>|<span data-ttu-id="2b862-119">ISA09 交换日期</span><span class="sxs-lookup"><span data-stu-id="2b862-119">ISA09 Interchange Date</span></span>|-|  
|<span data-ttu-id="2b862-120">TA103</span><span class="sxs-lookup"><span data-stu-id="2b862-120">TA103</span></span>|<span data-ttu-id="2b862-121">交换时间</span><span class="sxs-lookup"><span data-stu-id="2b862-121">Interchange Time</span></span>|<span data-ttu-id="2b862-122">ISA10 – 交换时间</span><span class="sxs-lookup"><span data-stu-id="2b862-122">ISA10 – Interchange Time</span></span>|-|  
|<span data-ttu-id="2b862-123">TA104</span><span class="sxs-lookup"><span data-stu-id="2b862-123">TA104</span></span>|<span data-ttu-id="2b862-124">交换确认代码*</span><span class="sxs-lookup"><span data-stu-id="2b862-124">Interchange ACK Code*</span></span>|<span data-ttu-id="2b862-125">N/A</span><span class="sxs-lookup"><span data-stu-id="2b862-125">N/A</span></span>|<span data-ttu-id="2b862-126">引擎行为： A、 E 或 R</span><span class="sxs-lookup"><span data-stu-id="2b862-126">Engine behavior: A, E, or R</span></span><br /><br /> <span data-ttu-id="2b862-127">A = 接受</span><span class="sxs-lookup"><span data-stu-id="2b862-127">A = Accept</span></span><br /><br /> <span data-ttu-id="2b862-128">E = 已接受但存在错误的交换</span><span class="sxs-lookup"><span data-stu-id="2b862-128">E = Interchange accepted with errors</span></span><br /><br /> <span data-ttu-id="2b862-129">R = 已拒绝/已挂起的交换</span><span class="sxs-lookup"><span data-stu-id="2b862-129">R = Interchange rejected/suspended</span></span>|  
|<span data-ttu-id="2b862-130">TA105</span><span class="sxs-lookup"><span data-stu-id="2b862-130">TA105</span></span>|<span data-ttu-id="2b862-131">交换注释代码</span><span class="sxs-lookup"><span data-stu-id="2b862-131">Interchange Note Code</span></span>|<span data-ttu-id="2b862-132">N/A</span><span class="sxs-lookup"><span data-stu-id="2b862-132">N/A</span></span>|<span data-ttu-id="2b862-133">处理结果错误代码。</span><span class="sxs-lookup"><span data-stu-id="2b862-133">Processing result error code.</span></span> <span data-ttu-id="2b862-134">**注意：**中的，请参阅表[X12 TA1 确认错误代码](../core/x12-ta1-acknowledgment-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="2b862-134">**Note:**  See table in [X12 TA1 Acknowledgment Error Codes](../core/x12-ta1-acknowledgment-error-codes.md).</span></span>|  
  
 <span data-ttu-id="2b862-135">\*引擎行为基于数据元素验证;除了安全和身份验证信息，将关闭中配置信息的字符串比较基于其。</span><span class="sxs-lookup"><span data-stu-id="2b862-135">\* Engine behavior is based off data element validation; except for security and authentication information, which will be based off string comparisons in configuration information.</span></span>