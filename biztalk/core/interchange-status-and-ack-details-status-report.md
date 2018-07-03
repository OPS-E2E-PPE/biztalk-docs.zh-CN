---
title: 交换状态和确认详细信息状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebba4af5-6dff-4bb8-9c63-739ef49bbbb8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3201bc969bc053e9a128cbb0e65a42a2714480c3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999022"
---
# <a name="interchange-status-and-ack-details-status-report"></a><span data-ttu-id="eb297-102">“交换状态和确认详细信息”状态报告</span><span class="sxs-lookup"><span data-stu-id="eb297-102">Interchange Status and ACK Details Status Report</span></span>
<span data-ttu-id="eb297-103">此状态报告显示交换及其相关交换（技术）确认和功能确认的详细信息。</span><span class="sxs-lookup"><span data-stu-id="eb297-103">This status report displays details of an interchange and its correlated interchange (technical) acknowledgment and functional acknowledgments.</span></span> <span data-ttu-id="eb297-104">显示此报告，右键单击交换 /ACK 状态报表中的某个交换，然后单击**交换状态和确认详细信息**。</span><span class="sxs-lookup"><span data-stu-id="eb297-104">You display this report for right-clicking an interchange within the Interchange/ACK status report, and then clicking **Interchange status and ack details**.</span></span>  
  
 <span data-ttu-id="eb297-105">此报告为交换及相关确认提供了以下不同的视图：</span><span class="sxs-lookup"><span data-stu-id="eb297-105">This report provides the following separate views for the interchange and the correlated acknowledgments:</span></span>  
  
## <a name="interchange-status"></a><span data-ttu-id="eb297-106">交换状态</span><span class="sxs-lookup"><span data-stu-id="eb297-106">Interchange Status</span></span>  
 <span data-ttu-id="eb297-107">此视图提供一个表格，显示了以下字段的值：</span><span class="sxs-lookup"><span data-stu-id="eb297-107">This view provides a table showing the values for the following fields:</span></span>  
  
- <span data-ttu-id="eb297-108">发送方 ID</span><span class="sxs-lookup"><span data-stu-id="eb297-108">Sender party ID</span></span>  
  
- <span data-ttu-id="eb297-109">接收方 ID</span><span class="sxs-lookup"><span data-stu-id="eb297-109">Receiver party ID</span></span>  
  
- <span data-ttu-id="eb297-110">控件 ID</span><span class="sxs-lookup"><span data-stu-id="eb297-110">Control ID</span></span>  
  
- <span data-ttu-id="eb297-111">接收方名称</span><span class="sxs-lookup"><span data-stu-id="eb297-111">Receiver party name</span></span>  
  
- <span data-ttu-id="eb297-112">发送方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="eb297-112">Sender party name</span></span>  
  
- <span data-ttu-id="eb297-113">方向</span><span class="sxs-lookup"><span data-stu-id="eb297-113">Direction</span></span>  
  
- <span data-ttu-id="eb297-114">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="eb297-114">Interchange Date Time</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="eb297-115">对于收到的文档，如果在交换中指定的日期格式为 YYMMDD 且 YY 大于等于 75，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将年份显示为 19YY。</span><span class="sxs-lookup"><span data-stu-id="eb297-115">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="eb297-116">如果日期中的 YY 小于 75，将显示为 20YY。</span><span class="sxs-lookup"><span data-stu-id="eb297-116">If the date is less than 75, it will be displayed as 20YY.</span></span>  
  > 
  >  <span data-ttu-id="eb297-117">例如，如果你收到的交换在 ISA09 中包含值 991113，则在报告中将“交换日期”显示为 11/13/1999。</span><span class="sxs-lookup"><span data-stu-id="eb297-117">For example, if you receive an interchange that contains the value 991113 in ISA09, the Interchange Date will be listed in the report as 11/13/1999.</span></span>  
  
- <span data-ttu-id="eb297-118">组计数</span><span class="sxs-lookup"><span data-stu-id="eb297-118">Group count</span></span>  
  
- <span data-ttu-id="eb297-119">端口 ID</span><span class="sxs-lookup"><span data-stu-id="eb297-119">Port ID</span></span>  
  
- <span data-ttu-id="eb297-120">交换状态</span><span class="sxs-lookup"><span data-stu-id="eb297-120">Interchange Status</span></span>  
  
- <span data-ttu-id="eb297-121">EDI 编码类型</span><span class="sxs-lookup"><span data-stu-id="eb297-121">EDI encoding type</span></span>  
  
- <span data-ttu-id="eb297-122">事务集相关 ID</span><span class="sxs-lookup"><span data-stu-id="eb297-122">Transaction Set Correlation Id</span></span>  
  
  <span data-ttu-id="eb297-123">如果为作为交换接收方的参与方启用了技术确认（在“EDI 属性”对话框的“确认处理和验证设置”页中），BizTalk Server 将期待返回为了响应它发送的交换而发回的技术（交换）确认。</span><span class="sxs-lookup"><span data-stu-id="eb297-123">If a technical acknowledgment is enabled for a party as an interchange receiver (in the ACK Processing and Validation Settings page of the EDI Properties dialog box), BizTalk Server expects a technical (interchange) acknowledgment to be returned in response to an interchange that it sends.</span></span> <span data-ttu-id="eb297-124">在最初为出站交换创建交换状态条目的时候，它将在“交换状态”字段中输入“预期的确认”。</span><span class="sxs-lookup"><span data-stu-id="eb297-124">When it initially creates an interchange status entry for an outbound interchange, it will enter ACK Expected in the Interchange Status field.</span></span> <span data-ttu-id="eb297-125">如果它收到了技术确认并且将其关联到原始交换，它会更新“交换状态”字段以指出它已收到确认。</span><span class="sxs-lookup"><span data-stu-id="eb297-125">When it receives a technical acknowledgment and correlates it to the original interchange, it will update the Interchange Status field to indicate that it has received the acknowledgment.</span></span>  
  
## <a name="interchange-ack-status"></a><span data-ttu-id="eb297-126">交换确认状态</span><span class="sxs-lookup"><span data-stu-id="eb297-126">Interchange Ack Status</span></span>  
 <span data-ttu-id="eb297-127">此视图显示交换（技术）确认的状态值：</span><span class="sxs-lookup"><span data-stu-id="eb297-127">This view displays status values for an interchange (technical) acknowledgment:</span></span>  
  
-   <span data-ttu-id="eb297-128">ACK 交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="eb297-128">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="eb297-129">接收方</span><span class="sxs-lookup"><span data-stu-id="eb297-129">Receiver party</span></span>  
  
-   <span data-ttu-id="eb297-130">发送方</span><span class="sxs-lookup"><span data-stu-id="eb297-130">Sender party</span></span>  
  
-   <span data-ttu-id="eb297-131">方向</span><span class="sxs-lookup"><span data-stu-id="eb297-131">Direction</span></span>  
  
-   <span data-ttu-id="eb297-132">ACK 交换日期</span><span class="sxs-lookup"><span data-stu-id="eb297-132">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="eb297-133">ACK 交换时间</span><span class="sxs-lookup"><span data-stu-id="eb297-133">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="eb297-134">ACK 状态</span><span class="sxs-lookup"><span data-stu-id="eb297-134">Ack Status</span></span>  
  
-   <span data-ttu-id="eb297-135">状态代码</span><span class="sxs-lookup"><span data-stu-id="eb297-135">Status Code</span></span>  
  
-   <span data-ttu-id="eb297-136">ACK 注释代码 1</span><span class="sxs-lookup"><span data-stu-id="eb297-136">Ack Note Code1</span></span>  
  
-   <span data-ttu-id="eb297-137">ACK 注释代码 2</span><span class="sxs-lookup"><span data-stu-id="eb297-137">Ack Note Code2</span></span>  
  
## <a name="functional-acks"></a><span data-ttu-id="eb297-138">功能确认</span><span class="sxs-lookup"><span data-stu-id="eb297-138">Functional Ack(s)</span></span>  
 <span data-ttu-id="eb297-139">此视图显示功能确认的状态值：</span><span class="sxs-lookup"><span data-stu-id="eb297-139">This view displays status values for an functional acknowledgment:</span></span>  
  
-   <span data-ttu-id="eb297-140">组控制编号</span><span class="sxs-lookup"><span data-stu-id="eb297-140">Group Control Number</span></span>  
  
-   <span data-ttu-id="eb297-141">接收方</span><span class="sxs-lookup"><span data-stu-id="eb297-141">Receiver party</span></span>  
  
-   <span data-ttu-id="eb297-142">发送方</span><span class="sxs-lookup"><span data-stu-id="eb297-142">Sender party</span></span>  
  
-   <span data-ttu-id="eb297-143">方向</span><span class="sxs-lookup"><span data-stu-id="eb297-143">Direction</span></span>  
  
-   <span data-ttu-id="eb297-144">“登录属性”</span><span class="sxs-lookup"><span data-stu-id="eb297-144">Status</span></span>  
  
-   <span data-ttu-id="eb297-145">状态代码</span><span class="sxs-lookup"><span data-stu-id="eb297-145">Status Code</span></span>  
  
-   <span data-ttu-id="eb297-146">功能 ID 代码</span><span class="sxs-lookup"><span data-stu-id="eb297-146">Functional ID Code</span></span>  
  
-   <span data-ttu-id="eb297-147">TS 计数</span><span class="sxs-lookup"><span data-stu-id="eb297-147">TS Count</span></span>  
  
-   <span data-ttu-id="eb297-148">ACK 交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="eb297-148">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="eb297-149">ACK 交换日期</span><span class="sxs-lookup"><span data-stu-id="eb297-149">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="eb297-150">ACK 交换时间</span><span class="sxs-lookup"><span data-stu-id="eb297-150">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="eb297-151">已送达 TS 计数</span><span class="sxs-lookup"><span data-stu-id="eb297-151">Delivered TS Count</span></span>  
  
-   <span data-ttu-id="eb297-152">已接受 TS 计数</span><span class="sxs-lookup"><span data-stu-id="eb297-152">Accepted TS Count</span></span>  
  
-   <span data-ttu-id="eb297-153">错误代码 1</span><span class="sxs-lookup"><span data-stu-id="eb297-153">ErrorCode 1</span></span>  
  
-   <span data-ttu-id="eb297-154">错误代码 2</span><span class="sxs-lookup"><span data-stu-id="eb297-154">ErrorCode 2</span></span>  
  
-   <span data-ttu-id="eb297-155">Errorcode 3</span><span class="sxs-lookup"><span data-stu-id="eb297-155">ErrorCode 3</span></span>  
  
-   <span data-ttu-id="eb297-156">错误代码 4</span><span class="sxs-lookup"><span data-stu-id="eb297-156">ErrorCode 4</span></span>  
  
-   <span data-ttu-id="eb297-157">错误代码 5</span><span class="sxs-lookup"><span data-stu-id="eb297-157">ErrorCode 5</span></span>  
  
-   <span data-ttu-id="eb297-158">接收时间</span><span class="sxs-lookup"><span data-stu-id="eb297-158">Time Received</span></span>