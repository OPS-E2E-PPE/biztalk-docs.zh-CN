---
title: X12 TA1 确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68568a1a-3669-46f4-8edc-8d057b012544
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a168a4112e861ea6b33b232883d320be2aa1ba82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394754"
---
# <a name="x12-ta1-acknowledgment"></a><span data-ttu-id="74490-102">X12 TA1 确认</span><span class="sxs-lookup"><span data-stu-id="74490-102">X12 TA1 Acknowledgment</span></span>
<span data-ttu-id="74490-103">X12 TA1 技术确认报告的交换标头和尾部地址接收方处理的状态。</span><span class="sxs-lookup"><span data-stu-id="74490-103">The X12 TA1 technical acknowledgment reports the status of the processing of an interchange header and trailer by the address receiver.</span></span> <span data-ttu-id="74490-104">有效，发送肯定的 TA1 确认的 ISA 和 IEA 的 X12 编码消息时，任何其他内容的状态。</span><span class="sxs-lookup"><span data-stu-id="74490-104">When the ISA and IEA of the X12-encoded message are valid, a positive TA1 ACK is sent, whatever the status of the other content is.</span></span> <span data-ttu-id="74490-105">否则，发送并返回错误代码的 TA1 确认。</span><span class="sxs-lookup"><span data-stu-id="74490-105">If not, TA1 ACK with an error code is sent.</span></span>  
  
 <span data-ttu-id="74490-106">X12 TA1 确认遵循到 X12_\<版本号\>_TA1.xsd 架构。</span><span class="sxs-lookup"><span data-stu-id="74490-106">The X12 TA1 acknowledgment conforms to the X12_\<version number\>_TA1.xsd schema.</span></span> <span data-ttu-id="74490-107">在 ISA/IEA 信封内部发送 TA1 确认。</span><span class="sxs-lookup"><span data-stu-id="74490-107">The TA1 ACK is sent inside an ISA/IEA envelope.</span></span> <span data-ttu-id="74490-108">ISA 和 IEA 与其他任何交换没有什么不同。</span><span class="sxs-lookup"><span data-stu-id="74490-108">The ISA and IEA are no different than any other interchange.</span></span>  
  
 <span data-ttu-id="74490-109">下表中显示了 TA1 确认交换内部的分段。</span><span class="sxs-lookup"><span data-stu-id="74490-109">The segments within the interchange of a TA1 ACK are shown in the following table.</span></span>  
  
|<span data-ttu-id="74490-110">TA1 中的字段</span><span class="sxs-lookup"><span data-stu-id="74490-110">Field in TA1</span></span>|<span data-ttu-id="74490-111">字段的名称</span><span class="sxs-lookup"><span data-stu-id="74490-111">Name of Field</span></span>|<span data-ttu-id="74490-112">映射到传入的交换</span><span class="sxs-lookup"><span data-stu-id="74490-112">Mapped to Incoming Interchange</span></span>|<span data-ttu-id="74490-113">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="74490-113">Value</span></span>|  
|------------------|-------------------|------------------------------------|-----------|  
|<span data-ttu-id="74490-114">TA101</span><span class="sxs-lookup"><span data-stu-id="74490-114">TA101</span></span>|<span data-ttu-id="74490-115">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="74490-115">Interchange control number</span></span>|<span data-ttu-id="74490-116">ISA13-交换控制编号</span><span class="sxs-lookup"><span data-stu-id="74490-116">ISA13 - Interchange control number</span></span>|-|  
|<span data-ttu-id="74490-117">TA102</span><span class="sxs-lookup"><span data-stu-id="74490-117">TA102</span></span>|<span data-ttu-id="74490-118">交换日期</span><span class="sxs-lookup"><span data-stu-id="74490-118">Interchange Date</span></span>|<span data-ttu-id="74490-119">ISA09 Interchange Date</span><span class="sxs-lookup"><span data-stu-id="74490-119">ISA09 Interchange Date</span></span>|-|  
|<span data-ttu-id="74490-120">TA103</span><span class="sxs-lookup"><span data-stu-id="74490-120">TA103</span></span>|<span data-ttu-id="74490-121">交换时间</span><span class="sxs-lookup"><span data-stu-id="74490-121">Interchange Time</span></span>|<span data-ttu-id="74490-122">ISA10 – 交换时间</span><span class="sxs-lookup"><span data-stu-id="74490-122">ISA10 – Interchange Time</span></span>|-|  
|<span data-ttu-id="74490-123">TA104</span><span class="sxs-lookup"><span data-stu-id="74490-123">TA104</span></span>|<span data-ttu-id="74490-124">交换确认代码 \*</span><span class="sxs-lookup"><span data-stu-id="74490-124">Interchange ACK Code\*</span></span>|<span data-ttu-id="74490-125">不可用</span><span class="sxs-lookup"><span data-stu-id="74490-125">N/A</span></span>|<span data-ttu-id="74490-126">引擎行为：A、 E 或 R</span><span class="sxs-lookup"><span data-stu-id="74490-126">Engine behavior: A, E, or R</span></span><br /><br /> <span data-ttu-id="74490-127">A = 接受</span><span class="sxs-lookup"><span data-stu-id="74490-127">A = Accept</span></span><br /><br /> <span data-ttu-id="74490-128">E = 接受存在错误的交换</span><span class="sxs-lookup"><span data-stu-id="74490-128">E = Interchange accepted with errors</span></span><br /><br /> <span data-ttu-id="74490-129">R = 交换被拒绝/已挂起</span><span class="sxs-lookup"><span data-stu-id="74490-129">R = Interchange rejected/suspended</span></span>|  
|<span data-ttu-id="74490-130">TA105</span><span class="sxs-lookup"><span data-stu-id="74490-130">TA105</span></span>|<span data-ttu-id="74490-131">交换注释代码</span><span class="sxs-lookup"><span data-stu-id="74490-131">Interchange Note Code</span></span>|<span data-ttu-id="74490-132">不可用</span><span class="sxs-lookup"><span data-stu-id="74490-132">N/A</span></span>|<span data-ttu-id="74490-133">处理结果错误代码。</span><span class="sxs-lookup"><span data-stu-id="74490-133">Processing result error code.</span></span> <span data-ttu-id="74490-134">**注意：** 请参阅中的表[X12 TA1 确认错误代码](../core/x12-ta1-acknowledgment-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="74490-134">**Note:**  See table in [X12 TA1 Acknowledgment Error Codes](../core/x12-ta1-acknowledgment-error-codes.md).</span></span>|  
  
 <span data-ttu-id="74490-135">\* 引擎行为基于数据元素验证;除了安全和身份验证信息，这将基于配置信息中的字符串比较。</span><span class="sxs-lookup"><span data-stu-id="74490-135">\* Engine behavior is based off data element validation; except for security and authentication information, which will be based off string comparisons in configuration information.</span></span>