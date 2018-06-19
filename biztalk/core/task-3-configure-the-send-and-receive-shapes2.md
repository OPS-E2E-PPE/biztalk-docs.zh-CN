---
title: 任务 3： 配置发送和接收 Shapes2 |Microsoft 文档
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
ms.openlocfilehash: 6923a90b43d1bdc3004a03ac588dd2410d81a3cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279021"
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a><span data-ttu-id="ea2fc-102">任务 3： 配置发送和接收形状</span><span class="sxs-lookup"><span data-stu-id="ea2fc-102">Task 3: Configure the Send and Receive Shapes</span></span>
<span data-ttu-id="ea2fc-103">使用以下过程可以配置发送和接收形状。</span><span class="sxs-lookup"><span data-stu-id="ea2fc-103">Use the following procedure to configure the Send and Receive shapes.</span></span>  
  
### <a name="to-configure-the-send-and-receive-shapes"></a><span data-ttu-id="ea2fc-104">若要配置发送和接收形状</span><span class="sxs-lookup"><span data-stu-id="ea2fc-104">To configure the Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="ea2fc-105">按以下顺序将发送和接收形状从工具箱拖到业务流程的中心。</span><span class="sxs-lookup"><span data-stu-id="ea2fc-105">Drag Send and Receive shapes from the tool box into the center of the orchestration in the following order.</span></span>  
  
2.  <span data-ttu-id="ea2fc-106">设置以下参数：</span><span class="sxs-lookup"><span data-stu-id="ea2fc-106">Set the following parameters:</span></span>  
  
    |<span data-ttu-id="ea2fc-107">形状</span><span class="sxs-lookup"><span data-stu-id="ea2fc-107">Shape</span></span>|<span data-ttu-id="ea2fc-108">Name</span><span class="sxs-lookup"><span data-stu-id="ea2fc-108">Name</span></span>|<span data-ttu-id="ea2fc-109">设置</span><span class="sxs-lookup"><span data-stu-id="ea2fc-109">Setting</span></span>|  
    |-----------|----------|-------------|  
    |<span data-ttu-id="ea2fc-110">Receive1</span><span class="sxs-lookup"><span data-stu-id="ea2fc-110">Receive1</span></span>|<span data-ttu-id="ea2fc-111">Activate</span><span class="sxs-lookup"><span data-stu-id="ea2fc-111">Activate</span></span>|<span data-ttu-id="ea2fc-112">True</span><span class="sxs-lookup"><span data-stu-id="ea2fc-112">True</span></span>|  
    ||<span data-ttu-id="ea2fc-113">消息</span><span class="sxs-lookup"><span data-stu-id="ea2fc-113">Message</span></span>|<span data-ttu-id="ea2fc-114">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="ea2fc-114">BeginDocMsg</span></span>|  
    ||<span data-ttu-id="ea2fc-115">Name</span><span class="sxs-lookup"><span data-stu-id="ea2fc-115">Name</span></span>|<span data-ttu-id="ea2fc-116">ReceiveBeginDoc</span><span class="sxs-lookup"><span data-stu-id="ea2fc-116">ReceiveBeginDoc</span></span>|  
    ||<span data-ttu-id="ea2fc-117">运算</span><span class="sxs-lookup"><span data-stu-id="ea2fc-117">Operation</span></span>|<span data-ttu-id="ea2fc-118">BeginDoc.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="ea2fc-118">BeginDoc.Operation_1.Request</span></span>|  
    |<span data-ttu-id="ea2fc-119">Send1</span><span class="sxs-lookup"><span data-stu-id="ea2fc-119">Send1</span></span>|<span data-ttu-id="ea2fc-120">消息</span><span class="sxs-lookup"><span data-stu-id="ea2fc-120">Message</span></span>|<span data-ttu-id="ea2fc-121">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="ea2fc-121">BeginDocSessionMsg</span></span>|  
    ||<span data-ttu-id="ea2fc-122">Name</span><span class="sxs-lookup"><span data-stu-id="ea2fc-122">Name</span></span>|<span data-ttu-id="ea2fc-123">SendBeginDoc</span><span class="sxs-lookup"><span data-stu-id="ea2fc-123">SendBeginDoc</span></span>|  
    ||<span data-ttu-id="ea2fc-124">运算</span><span class="sxs-lookup"><span data-stu-id="ea2fc-124">Operation</span></span>|<span data-ttu-id="ea2fc-125">JDEPort.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="ea2fc-125">JDEPort.Operation_1.Request</span></span>|  
    |<span data-ttu-id="ea2fc-126">Receive2</span><span class="sxs-lookup"><span data-stu-id="ea2fc-126">Receive2</span></span>|<span data-ttu-id="ea2fc-127">Activate</span><span class="sxs-lookup"><span data-stu-id="ea2fc-127">Activate</span></span>|<span data-ttu-id="ea2fc-128">False</span><span class="sxs-lookup"><span data-stu-id="ea2fc-128">False</span></span>|  
    ||<span data-ttu-id="ea2fc-129">消息</span><span class="sxs-lookup"><span data-stu-id="ea2fc-129">Message</span></span>|<span data-ttu-id="ea2fc-130">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="ea2fc-130">BeginDocResponseMsg</span></span>|  
    ||<span data-ttu-id="ea2fc-131">Name</span><span class="sxs-lookup"><span data-stu-id="ea2fc-131">Name</span></span>|<span data-ttu-id="ea2fc-132">ReceiveBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="ea2fc-132">ReceiveBeginDocResponse</span></span>|  
    ||<span data-ttu-id="ea2fc-133">运算</span><span class="sxs-lookup"><span data-stu-id="ea2fc-133">Operation</span></span>|<span data-ttu-id="ea2fc-134">JDEPort.Operation_1.Response</span><span class="sxs-lookup"><span data-stu-id="ea2fc-134">JDEPort.Operation_1.Response</span></span>|  
    |<span data-ttu-id="ea2fc-135">Send2</span><span class="sxs-lookup"><span data-stu-id="ea2fc-135">Send2</span></span>|<span data-ttu-id="ea2fc-136">消息</span><span class="sxs-lookup"><span data-stu-id="ea2fc-136">Message</span></span>|<span data-ttu-id="ea2fc-137">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="ea2fc-137">EditLineSessionMsg</span></span>|  
    ||<span data-ttu-id="ea2fc-138">Name</span><span class="sxs-lookup"><span data-stu-id="ea2fc-138">Name</span></span>|<span data-ttu-id="ea2fc-139">SendEditLine</span><span class="sxs-lookup"><span data-stu-id="ea2fc-139">SendEditLine</span></span>|  
    ||<span data-ttu-id="ea2fc-140">运算</span><span class="sxs-lookup"><span data-stu-id="ea2fc-140">Operation</span></span>|<span data-ttu-id="ea2fc-141">JDEPort.Operation_2.Request</span><span class="sxs-lookup"><span data-stu-id="ea2fc-141">JDEPort.Operation_2.Request</span></span>|  
    |<span data-ttu-id="ea2fc-142">Receive3</span><span class="sxs-lookup"><span data-stu-id="ea2fc-142">Receive3</span></span>|<span data-ttu-id="ea2fc-143">Activate</span><span class="sxs-lookup"><span data-stu-id="ea2fc-143">Activate</span></span>|<span data-ttu-id="ea2fc-144">False</span><span class="sxs-lookup"><span data-stu-id="ea2fc-144">False</span></span>|  
    ||<span data-ttu-id="ea2fc-145">消息</span><span class="sxs-lookup"><span data-stu-id="ea2fc-145">Message</span></span>|<span data-ttu-id="ea2fc-146">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="ea2fc-146">EditLineResponseMsg</span></span>|  
    ||<span data-ttu-id="ea2fc-147">Name</span><span class="sxs-lookup"><span data-stu-id="ea2fc-147">Name</span></span>|<span data-ttu-id="ea2fc-148">ReceiveEditLine</span><span class="sxs-lookup"><span data-stu-id="ea2fc-148">ReceiveEditLine</span></span>|  
    ||<span data-ttu-id="ea2fc-149">运算</span><span class="sxs-lookup"><span data-stu-id="ea2fc-149">Operation</span></span>|<span data-ttu-id="ea2fc-150">JDEPort.Operation_2.Response</span><span class="sxs-lookup"><span data-stu-id="ea2fc-150">JDEPort.Operation_2.Response</span></span>|  
    |<span data-ttu-id="ea2fc-151">Send3</span><span class="sxs-lookup"><span data-stu-id="ea2fc-151">Send3</span></span>|<span data-ttu-id="ea2fc-152">消息</span><span class="sxs-lookup"><span data-stu-id="ea2fc-152">Message</span></span>|<span data-ttu-id="ea2fc-153">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="ea2fc-153">EndDocSessionMsg</span></span>|  
    ||<span data-ttu-id="ea2fc-154">Name</span><span class="sxs-lookup"><span data-stu-id="ea2fc-154">Name</span></span>|<span data-ttu-id="ea2fc-155">SendEndDoc</span><span class="sxs-lookup"><span data-stu-id="ea2fc-155">SendEndDoc</span></span>|  
    ||<span data-ttu-id="ea2fc-156">运算</span><span class="sxs-lookup"><span data-stu-id="ea2fc-156">Operation</span></span>|<span data-ttu-id="ea2fc-157">JDEPort.Operation_3.Request</span><span class="sxs-lookup"><span data-stu-id="ea2fc-157">JDEPort.Operation_3.Request</span></span>|  
    |<span data-ttu-id="ea2fc-158">Receive4</span><span class="sxs-lookup"><span data-stu-id="ea2fc-158">Receive4</span></span>|<span data-ttu-id="ea2fc-159">Activate</span><span class="sxs-lookup"><span data-stu-id="ea2fc-159">Activate</span></span>|<span data-ttu-id="ea2fc-160">False</span><span class="sxs-lookup"><span data-stu-id="ea2fc-160">False</span></span>|  
    ||<span data-ttu-id="ea2fc-161">消息</span><span class="sxs-lookup"><span data-stu-id="ea2fc-161">Message</span></span>|<span data-ttu-id="ea2fc-162">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="ea2fc-162">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="ea2fc-163">Name</span><span class="sxs-lookup"><span data-stu-id="ea2fc-163">Name</span></span>|<span data-ttu-id="ea2fc-164">ReceiveEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="ea2fc-164">ReceiveEndDocResponse</span></span>|  
    ||<span data-ttu-id="ea2fc-165">运算</span><span class="sxs-lookup"><span data-stu-id="ea2fc-165">Operation</span></span>|<span data-ttu-id="ea2fc-166">JDEPort.Operation_3.Response</span><span class="sxs-lookup"><span data-stu-id="ea2fc-166">JDEPort.Operation_3.Response</span></span>|  
    |<span data-ttu-id="ea2fc-167">Send4</span><span class="sxs-lookup"><span data-stu-id="ea2fc-167">Send4</span></span>|<span data-ttu-id="ea2fc-168">消息</span><span class="sxs-lookup"><span data-stu-id="ea2fc-168">Message</span></span>|<span data-ttu-id="ea2fc-169">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="ea2fc-169">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="ea2fc-170">Name</span><span class="sxs-lookup"><span data-stu-id="ea2fc-170">Name</span></span>|<span data-ttu-id="ea2fc-171">SendEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="ea2fc-171">SendEndDocResponse</span></span>|  
    ||<span data-ttu-id="ea2fc-172">运算</span><span class="sxs-lookup"><span data-stu-id="ea2fc-172">Operation</span></span>|<span data-ttu-id="ea2fc-173">EndDocOut.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="ea2fc-173">EndDocOut.Operation_1.Request</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea2fc-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea2fc-174">See Also</span></span>  
 <span data-ttu-id="ea2fc-175">[任务 1： 创建端口](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="ea2fc-175">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="ea2fc-176">[任务 2： 创建消息](../core/task-2-create-the-messages2.md) </span><span class="sxs-lookup"><span data-stu-id="ea2fc-176">[Task 2: Create the Messages](../core/task-2-create-the-messages2.md) </span></span>  
 <span data-ttu-id="ea2fc-177">[任务 4： 配置构造消息形状](../core/task-4-configure-the-construct-message-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="ea2fc-177">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape1.md) </span></span>  
 [<span data-ttu-id="ea2fc-178">任务 5： 配置转换形状</span><span class="sxs-lookup"><span data-stu-id="ea2fc-178">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)