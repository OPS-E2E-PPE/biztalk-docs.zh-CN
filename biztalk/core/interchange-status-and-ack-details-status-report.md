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
ms.openlocfilehash: 167162a47516279c22bd250589246b3dbd12f109
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381932"
---
# <a name="interchange-status-and-ack-details-status-report"></a><span data-ttu-id="0b152-102">交换状态和确认详细信息状态报告</span><span class="sxs-lookup"><span data-stu-id="0b152-102">Interchange Status and ACK Details Status Report</span></span>
<span data-ttu-id="0b152-103">此状态报告显示交换及其相关的交换 （技术） 确认和功能确认的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0b152-103">This status report displays details of an interchange and its correlated interchange (technical) acknowledgment and functional acknowledgments.</span></span> <span data-ttu-id="0b152-104">显示此报告，右键单击交换 /ACK 状态报表中的某个交换，然后单击**交换状态和确认详细信息**。</span><span class="sxs-lookup"><span data-stu-id="0b152-104">You display this report for right-clicking an interchange within the Interchange/ACK status report, and then clicking **Interchange status and ack details**.</span></span>  
  
 <span data-ttu-id="0b152-105">此报表提供的交换和相关的确认以下不同的视图：</span><span class="sxs-lookup"><span data-stu-id="0b152-105">This report provides the following separate views for the interchange and the correlated acknowledgments:</span></span>  
  
## <a name="interchange-status"></a><span data-ttu-id="0b152-106">交换状态</span><span class="sxs-lookup"><span data-stu-id="0b152-106">Interchange Status</span></span>  
 <span data-ttu-id="0b152-107">此视图提供的表格显示以下字段的值：</span><span class="sxs-lookup"><span data-stu-id="0b152-107">This view provides a table showing the values for the following fields:</span></span>  
  
- <span data-ttu-id="0b152-108">发送方 ID</span><span class="sxs-lookup"><span data-stu-id="0b152-108">Sender party ID</span></span>  
  
- <span data-ttu-id="0b152-109">接收方 ID</span><span class="sxs-lookup"><span data-stu-id="0b152-109">Receiver party ID</span></span>  
  
- <span data-ttu-id="0b152-110">控件 ID</span><span class="sxs-lookup"><span data-stu-id="0b152-110">Control ID</span></span>  
  
- <span data-ttu-id="0b152-111">接收方名称</span><span class="sxs-lookup"><span data-stu-id="0b152-111">Receiver party name</span></span>  
  
- <span data-ttu-id="0b152-112">发送方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="0b152-112">Sender party name</span></span>  
  
- <span data-ttu-id="0b152-113">Direction</span><span class="sxs-lookup"><span data-stu-id="0b152-113">Direction</span></span>  
  
- <span data-ttu-id="0b152-114">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="0b152-114">Interchange Date Time</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="0b152-115">对于收到的文档，如果交换中指定的日期格式为 YYMMDD 且 YY 大于或等于 75，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会将年份显示为 19YY。</span><span class="sxs-lookup"><span data-stu-id="0b152-115">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="0b152-116">如果日期是小于 75，将显示为 20YY。</span><span class="sxs-lookup"><span data-stu-id="0b152-116">If the date is less than 75, it will be displayed as 20YY.</span></span>  
  > 
  >  <span data-ttu-id="0b152-117">例如，如果收到包含在 ISA09 中的值 991113 的交换，交换日期将是报告中列出为 1999 年 11/13。</span><span class="sxs-lookup"><span data-stu-id="0b152-117">For example, if you receive an interchange that contains the value 991113 in ISA09, the Interchange Date will be listed in the report as 11/13/1999.</span></span>  
  
- <span data-ttu-id="0b152-118">组计数</span><span class="sxs-lookup"><span data-stu-id="0b152-118">Group count</span></span>  
  
- <span data-ttu-id="0b152-119">端口 ID</span><span class="sxs-lookup"><span data-stu-id="0b152-119">Port ID</span></span>  
  
- <span data-ttu-id="0b152-120">交换状态</span><span class="sxs-lookup"><span data-stu-id="0b152-120">Interchange Status</span></span>  
  
- <span data-ttu-id="0b152-121">EDI 编码类型</span><span class="sxs-lookup"><span data-stu-id="0b152-121">EDI encoding type</span></span>  
  
- <span data-ttu-id="0b152-122">事务集相关 Id</span><span class="sxs-lookup"><span data-stu-id="0b152-122">Transaction Set Correlation Id</span></span>  
  
  <span data-ttu-id="0b152-123">如果为参与方作为交换接收方 （在 EDI 属性对话框的确认处理和验证设置页中） 启用了技术确认，BizTalk Server 期望在响应中返回的技术 （交换） 确认发送的交换。</span><span class="sxs-lookup"><span data-stu-id="0b152-123">If a technical acknowledgment is enabled for a party as an interchange receiver (in the ACK Processing and Validation Settings page of the EDI Properties dialog box), BizTalk Server expects a technical (interchange) acknowledgment to be returned in response to an interchange that it sends.</span></span> <span data-ttu-id="0b152-124">当它最初创建交换状态条目的出站交换时，它将进入预期的确认在交换状态字段中。</span><span class="sxs-lookup"><span data-stu-id="0b152-124">When it initially creates an interchange status entry for an outbound interchange, it will enter ACK Expected in the Interchange Status field.</span></span> <span data-ttu-id="0b152-125">当它收到了技术确认，并将其关联到原始交换时，它将更新交换状态字段以指示它已收到确认。</span><span class="sxs-lookup"><span data-stu-id="0b152-125">When it receives a technical acknowledgment and correlates it to the original interchange, it will update the Interchange Status field to indicate that it has received the acknowledgment.</span></span>  
  
## <a name="interchange-ack-status"></a><span data-ttu-id="0b152-126">交换确认状态</span><span class="sxs-lookup"><span data-stu-id="0b152-126">Interchange Ack Status</span></span>  
 <span data-ttu-id="0b152-127">此视图显示交换 （技术） 确认的状态值：</span><span class="sxs-lookup"><span data-stu-id="0b152-127">This view displays status values for an interchange (technical) acknowledgment:</span></span>  
  
-   <span data-ttu-id="0b152-128">Ack 交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="0b152-128">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="0b152-129">接收方</span><span class="sxs-lookup"><span data-stu-id="0b152-129">Receiver party</span></span>  
  
-   <span data-ttu-id="0b152-130">发送方</span><span class="sxs-lookup"><span data-stu-id="0b152-130">Sender party</span></span>  
  
-   <span data-ttu-id="0b152-131">Direction</span><span class="sxs-lookup"><span data-stu-id="0b152-131">Direction</span></span>  
  
-   <span data-ttu-id="0b152-132">Ack 交换日期</span><span class="sxs-lookup"><span data-stu-id="0b152-132">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="0b152-133">Ack 交换时间</span><span class="sxs-lookup"><span data-stu-id="0b152-133">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="0b152-134">Ack 状态</span><span class="sxs-lookup"><span data-stu-id="0b152-134">Ack Status</span></span>  
  
-   <span data-ttu-id="0b152-135">状态代码</span><span class="sxs-lookup"><span data-stu-id="0b152-135">Status Code</span></span>  
  
-   <span data-ttu-id="0b152-136">Ack 注释代码 1</span><span class="sxs-lookup"><span data-stu-id="0b152-136">Ack Note Code1</span></span>  
  
-   <span data-ttu-id="0b152-137">Ack 注释代码 2</span><span class="sxs-lookup"><span data-stu-id="0b152-137">Ack Note Code2</span></span>  
  
## <a name="functional-acks"></a><span data-ttu-id="0b152-138">功能确认</span><span class="sxs-lookup"><span data-stu-id="0b152-138">Functional Ack(s)</span></span>  
 <span data-ttu-id="0b152-139">此视图显示功能确认的状态值：</span><span class="sxs-lookup"><span data-stu-id="0b152-139">This view displays status values for an functional acknowledgment:</span></span>  
  
-   <span data-ttu-id="0b152-140">组控制编号</span><span class="sxs-lookup"><span data-stu-id="0b152-140">Group Control Number</span></span>  
  
-   <span data-ttu-id="0b152-141">接收方</span><span class="sxs-lookup"><span data-stu-id="0b152-141">Receiver party</span></span>  
  
-   <span data-ttu-id="0b152-142">发送方</span><span class="sxs-lookup"><span data-stu-id="0b152-142">Sender party</span></span>  
  
-   <span data-ttu-id="0b152-143">Direction</span><span class="sxs-lookup"><span data-stu-id="0b152-143">Direction</span></span>  
  
-   <span data-ttu-id="0b152-144">“登录属性”</span><span class="sxs-lookup"><span data-stu-id="0b152-144">Status</span></span>  
  
-   <span data-ttu-id="0b152-145">状态代码</span><span class="sxs-lookup"><span data-stu-id="0b152-145">Status Code</span></span>  
  
-   <span data-ttu-id="0b152-146">功能 ID 代码</span><span class="sxs-lookup"><span data-stu-id="0b152-146">Functional ID Code</span></span>  
  
-   <span data-ttu-id="0b152-147">TS 计数</span><span class="sxs-lookup"><span data-stu-id="0b152-147">TS Count</span></span>  
  
-   <span data-ttu-id="0b152-148">Ack 交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="0b152-148">Ack Interchange Control ID</span></span>  
  
-   <span data-ttu-id="0b152-149">Ack 交换日期</span><span class="sxs-lookup"><span data-stu-id="0b152-149">Ack Interchange Date</span></span>  
  
-   <span data-ttu-id="0b152-150">Ack 交换时间</span><span class="sxs-lookup"><span data-stu-id="0b152-150">Ack Interchange Time</span></span>  
  
-   <span data-ttu-id="0b152-151">已送达的 TS 计数</span><span class="sxs-lookup"><span data-stu-id="0b152-151">Delivered TS Count</span></span>  
  
-   <span data-ttu-id="0b152-152">已接受的 TS 计数</span><span class="sxs-lookup"><span data-stu-id="0b152-152">Accepted TS Count</span></span>  
  
-   <span data-ttu-id="0b152-153">ErrorCode 1</span><span class="sxs-lookup"><span data-stu-id="0b152-153">ErrorCode 1</span></span>  
  
-   <span data-ttu-id="0b152-154">错误代码 2</span><span class="sxs-lookup"><span data-stu-id="0b152-154">ErrorCode 2</span></span>  
  
-   <span data-ttu-id="0b152-155">ErrorCode 3</span><span class="sxs-lookup"><span data-stu-id="0b152-155">ErrorCode 3</span></span>  
  
-   <span data-ttu-id="0b152-156">ErrorCode 4</span><span class="sxs-lookup"><span data-stu-id="0b152-156">ErrorCode 4</span></span>  
  
-   <span data-ttu-id="0b152-157">ErrorCode 5</span><span class="sxs-lookup"><span data-stu-id="0b152-157">ErrorCode 5</span></span>  
  
-   <span data-ttu-id="0b152-158">接收时间</span><span class="sxs-lookup"><span data-stu-id="0b152-158">Time Received</span></span>