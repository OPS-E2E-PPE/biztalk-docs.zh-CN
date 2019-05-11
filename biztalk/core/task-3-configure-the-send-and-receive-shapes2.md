---
title: 任务 3：配置发送和接收 Shapes2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ebe7141-f2bd-4e6a-9204-d61bd64286af
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea0f66b7604f2cc03596bcf8d9c458b40349c9ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399235"
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a><span data-ttu-id="1bf73-102">任务 3：配置发送和接收形状</span><span class="sxs-lookup"><span data-stu-id="1bf73-102">Task 3: Configure the Send and Receive Shapes</span></span>
<span data-ttu-id="1bf73-103">使用以下过程来配置发送和接收形状。</span><span class="sxs-lookup"><span data-stu-id="1bf73-103">Use the following procedure to configure the Send and Receive shapes.</span></span>  
  
### <a name="to-configure-the-send-and-receive-shapes"></a><span data-ttu-id="1bf73-104">若要配置发送和接收形状</span><span class="sxs-lookup"><span data-stu-id="1bf73-104">To configure the Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="1bf73-105">将发送和接收形状从工具箱中按以下顺序业务流程的中心。</span><span class="sxs-lookup"><span data-stu-id="1bf73-105">Drag Send and Receive shapes from the tool box into the center of the orchestration in the following order.</span></span>  
  
2.  <span data-ttu-id="1bf73-106">设置以下参数：</span><span class="sxs-lookup"><span data-stu-id="1bf73-106">Set the following parameters:</span></span>  
  
    |<span data-ttu-id="1bf73-107">形状</span><span class="sxs-lookup"><span data-stu-id="1bf73-107">Shape</span></span>|<span data-ttu-id="1bf73-108">“属性”</span><span class="sxs-lookup"><span data-stu-id="1bf73-108">Name</span></span>|<span data-ttu-id="1bf73-109">设置</span><span class="sxs-lookup"><span data-stu-id="1bf73-109">Setting</span></span>|  
    |-----------|----------|-------------|  
    |<span data-ttu-id="1bf73-110">Receive1</span><span class="sxs-lookup"><span data-stu-id="1bf73-110">Receive1</span></span>|<span data-ttu-id="1bf73-111">Activate</span><span class="sxs-lookup"><span data-stu-id="1bf73-111">Activate</span></span>|<span data-ttu-id="1bf73-112">True</span><span class="sxs-lookup"><span data-stu-id="1bf73-112">True</span></span>|  
    ||<span data-ttu-id="1bf73-113">消息</span><span class="sxs-lookup"><span data-stu-id="1bf73-113">Message</span></span>|<span data-ttu-id="1bf73-114">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="1bf73-114">BeginDocMsg</span></span>|  
    ||<span data-ttu-id="1bf73-115">“属性”</span><span class="sxs-lookup"><span data-stu-id="1bf73-115">Name</span></span>|<span data-ttu-id="1bf73-116">ReceiveBeginDoc</span><span class="sxs-lookup"><span data-stu-id="1bf73-116">ReceiveBeginDoc</span></span>|  
    ||<span data-ttu-id="1bf73-117">操作</span><span class="sxs-lookup"><span data-stu-id="1bf73-117">Operation</span></span>|<span data-ttu-id="1bf73-118">BeginDoc.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="1bf73-118">BeginDoc.Operation_1.Request</span></span>|  
    |<span data-ttu-id="1bf73-119">Send1 上</span><span class="sxs-lookup"><span data-stu-id="1bf73-119">Send1</span></span>|<span data-ttu-id="1bf73-120">消息</span><span class="sxs-lookup"><span data-stu-id="1bf73-120">Message</span></span>|<span data-ttu-id="1bf73-121">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="1bf73-121">BeginDocSessionMsg</span></span>|  
    ||<span data-ttu-id="1bf73-122">“属性”</span><span class="sxs-lookup"><span data-stu-id="1bf73-122">Name</span></span>|<span data-ttu-id="1bf73-123">SendBeginDoc</span><span class="sxs-lookup"><span data-stu-id="1bf73-123">SendBeginDoc</span></span>|  
    ||<span data-ttu-id="1bf73-124">操作</span><span class="sxs-lookup"><span data-stu-id="1bf73-124">Operation</span></span>|<span data-ttu-id="1bf73-125">JDEPort.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="1bf73-125">JDEPort.Operation_1.Request</span></span>|  
    |<span data-ttu-id="1bf73-126">Receive2</span><span class="sxs-lookup"><span data-stu-id="1bf73-126">Receive2</span></span>|<span data-ttu-id="1bf73-127">Activate</span><span class="sxs-lookup"><span data-stu-id="1bf73-127">Activate</span></span>|<span data-ttu-id="1bf73-128">False</span><span class="sxs-lookup"><span data-stu-id="1bf73-128">False</span></span>|  
    ||<span data-ttu-id="1bf73-129">消息</span><span class="sxs-lookup"><span data-stu-id="1bf73-129">Message</span></span>|<span data-ttu-id="1bf73-130">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="1bf73-130">BeginDocResponseMsg</span></span>|  
    ||<span data-ttu-id="1bf73-131">“属性”</span><span class="sxs-lookup"><span data-stu-id="1bf73-131">Name</span></span>|<span data-ttu-id="1bf73-132">ReceiveBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="1bf73-132">ReceiveBeginDocResponse</span></span>|  
    ||<span data-ttu-id="1bf73-133">操作</span><span class="sxs-lookup"><span data-stu-id="1bf73-133">Operation</span></span>|<span data-ttu-id="1bf73-134">JDEPort.Operation_1.Response</span><span class="sxs-lookup"><span data-stu-id="1bf73-134">JDEPort.Operation_1.Response</span></span>|  
    |<span data-ttu-id="1bf73-135">Send2 上</span><span class="sxs-lookup"><span data-stu-id="1bf73-135">Send2</span></span>|<span data-ttu-id="1bf73-136">消息</span><span class="sxs-lookup"><span data-stu-id="1bf73-136">Message</span></span>|<span data-ttu-id="1bf73-137">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="1bf73-137">EditLineSessionMsg</span></span>|  
    ||<span data-ttu-id="1bf73-138">“属性”</span><span class="sxs-lookup"><span data-stu-id="1bf73-138">Name</span></span>|<span data-ttu-id="1bf73-139">SendEditLine</span><span class="sxs-lookup"><span data-stu-id="1bf73-139">SendEditLine</span></span>|  
    ||<span data-ttu-id="1bf73-140">操作</span><span class="sxs-lookup"><span data-stu-id="1bf73-140">Operation</span></span>|<span data-ttu-id="1bf73-141">JDEPort.Operation_2.Request</span><span class="sxs-lookup"><span data-stu-id="1bf73-141">JDEPort.Operation_2.Request</span></span>|  
    |<span data-ttu-id="1bf73-142">Receive3</span><span class="sxs-lookup"><span data-stu-id="1bf73-142">Receive3</span></span>|<span data-ttu-id="1bf73-143">Activate</span><span class="sxs-lookup"><span data-stu-id="1bf73-143">Activate</span></span>|<span data-ttu-id="1bf73-144">False</span><span class="sxs-lookup"><span data-stu-id="1bf73-144">False</span></span>|  
    ||<span data-ttu-id="1bf73-145">消息</span><span class="sxs-lookup"><span data-stu-id="1bf73-145">Message</span></span>|<span data-ttu-id="1bf73-146">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="1bf73-146">EditLineResponseMsg</span></span>|  
    ||<span data-ttu-id="1bf73-147">“属性”</span><span class="sxs-lookup"><span data-stu-id="1bf73-147">Name</span></span>|<span data-ttu-id="1bf73-148">ReceiveEditLine</span><span class="sxs-lookup"><span data-stu-id="1bf73-148">ReceiveEditLine</span></span>|  
    ||<span data-ttu-id="1bf73-149">操作</span><span class="sxs-lookup"><span data-stu-id="1bf73-149">Operation</span></span>|<span data-ttu-id="1bf73-150">JDEPort.Operation_2.Response</span><span class="sxs-lookup"><span data-stu-id="1bf73-150">JDEPort.Operation_2.Response</span></span>|  
    |<span data-ttu-id="1bf73-151">Send3</span><span class="sxs-lookup"><span data-stu-id="1bf73-151">Send3</span></span>|<span data-ttu-id="1bf73-152">消息</span><span class="sxs-lookup"><span data-stu-id="1bf73-152">Message</span></span>|<span data-ttu-id="1bf73-153">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="1bf73-153">EndDocSessionMsg</span></span>|  
    ||<span data-ttu-id="1bf73-154">“属性”</span><span class="sxs-lookup"><span data-stu-id="1bf73-154">Name</span></span>|<span data-ttu-id="1bf73-155">SendEndDoc</span><span class="sxs-lookup"><span data-stu-id="1bf73-155">SendEndDoc</span></span>|  
    ||<span data-ttu-id="1bf73-156">操作</span><span class="sxs-lookup"><span data-stu-id="1bf73-156">Operation</span></span>|<span data-ttu-id="1bf73-157">JDEPort.Operation_3.Request</span><span class="sxs-lookup"><span data-stu-id="1bf73-157">JDEPort.Operation_3.Request</span></span>|  
    |<span data-ttu-id="1bf73-158">Receive4</span><span class="sxs-lookup"><span data-stu-id="1bf73-158">Receive4</span></span>|<span data-ttu-id="1bf73-159">Activate</span><span class="sxs-lookup"><span data-stu-id="1bf73-159">Activate</span></span>|<span data-ttu-id="1bf73-160">False</span><span class="sxs-lookup"><span data-stu-id="1bf73-160">False</span></span>|  
    ||<span data-ttu-id="1bf73-161">消息</span><span class="sxs-lookup"><span data-stu-id="1bf73-161">Message</span></span>|<span data-ttu-id="1bf73-162">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="1bf73-162">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="1bf73-163">“属性”</span><span class="sxs-lookup"><span data-stu-id="1bf73-163">Name</span></span>|<span data-ttu-id="1bf73-164">ReceiveEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="1bf73-164">ReceiveEndDocResponse</span></span>|  
    ||<span data-ttu-id="1bf73-165">操作</span><span class="sxs-lookup"><span data-stu-id="1bf73-165">Operation</span></span>|<span data-ttu-id="1bf73-166">JDEPort.Operation_3.Response</span><span class="sxs-lookup"><span data-stu-id="1bf73-166">JDEPort.Operation_3.Response</span></span>|  
    |<span data-ttu-id="1bf73-167">Send4</span><span class="sxs-lookup"><span data-stu-id="1bf73-167">Send4</span></span>|<span data-ttu-id="1bf73-168">消息</span><span class="sxs-lookup"><span data-stu-id="1bf73-168">Message</span></span>|<span data-ttu-id="1bf73-169">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="1bf73-169">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="1bf73-170">“属性”</span><span class="sxs-lookup"><span data-stu-id="1bf73-170">Name</span></span>|<span data-ttu-id="1bf73-171">SendEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="1bf73-171">SendEndDocResponse</span></span>|  
    ||<span data-ttu-id="1bf73-172">操作</span><span class="sxs-lookup"><span data-stu-id="1bf73-172">Operation</span></span>|<span data-ttu-id="1bf73-173">EndDocOut.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="1bf73-173">EndDocOut.Operation_1.Request</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1bf73-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="1bf73-174">See Also</span></span>  
 <span data-ttu-id="1bf73-175">[任务 1:创建端口](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="1bf73-175">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="1bf73-176">[任务 2:创建消息](../core/task-2-create-the-messages2.md) </span><span class="sxs-lookup"><span data-stu-id="1bf73-176">[Task 2: Create the Messages](../core/task-2-create-the-messages2.md) </span></span>  
 <span data-ttu-id="1bf73-177">[任务 4:配置构造消息形状](../core/task-4-configure-the-construct-message-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="1bf73-177">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape1.md) </span></span>  
 [<span data-ttu-id="1bf73-178">任务 5:配置转换形状</span><span class="sxs-lookup"><span data-stu-id="1bf73-178">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)