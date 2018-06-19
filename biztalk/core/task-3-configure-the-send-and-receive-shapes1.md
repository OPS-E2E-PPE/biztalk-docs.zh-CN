---
title: 任务 3： 配置发送和接收 Shapes1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e258d22-755b-48a4-9f9e-e9398f6b68b1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c730cc6bc5cb11c27152613f331bda6b15be390
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278813"
---
# <a name="task-3-configure-the-send-and-receive-shapes"></a><span data-ttu-id="fa0cf-102">任务 3： 配置发送和接收形状</span><span class="sxs-lookup"><span data-stu-id="fa0cf-102">Task 3: Configure the Send and Receive Shapes</span></span>
<span data-ttu-id="fa0cf-103">使用以下过程可以配置发送和接收形状。</span><span class="sxs-lookup"><span data-stu-id="fa0cf-103">Use the following procedure to configure the Send and Receive shapes.</span></span>  
  
### <a name="to-configure-the-send-and-receive-shapes"></a><span data-ttu-id="fa0cf-104">若要配置发送和接收形状</span><span class="sxs-lookup"><span data-stu-id="fa0cf-104">To configure the Send and Receive shapes</span></span>  
  
1.  <span data-ttu-id="fa0cf-105">按以下顺序将发送和接收形状从工具箱拖到业务流程的中心。</span><span class="sxs-lookup"><span data-stu-id="fa0cf-105">Drag Send and Receive shapes from the tool box into the center of the orchestration in the following order.</span></span>  
  
2.  <span data-ttu-id="fa0cf-106">设置以下参数：</span><span class="sxs-lookup"><span data-stu-id="fa0cf-106">Set the following parameters:</span></span>  
  
    |<span data-ttu-id="fa0cf-107">形状</span><span class="sxs-lookup"><span data-stu-id="fa0cf-107">Shape</span></span>|<span data-ttu-id="fa0cf-108">Name</span><span class="sxs-lookup"><span data-stu-id="fa0cf-108">Name</span></span>|<span data-ttu-id="fa0cf-109">设置</span><span class="sxs-lookup"><span data-stu-id="fa0cf-109">Setting</span></span>|  
    |-----------|----------|-------------|  
    |<span data-ttu-id="fa0cf-110">Receive1</span><span class="sxs-lookup"><span data-stu-id="fa0cf-110">Receive1</span></span>|<span data-ttu-id="fa0cf-111">Activate</span><span class="sxs-lookup"><span data-stu-id="fa0cf-111">Activate</span></span>|<span data-ttu-id="fa0cf-112">True</span><span class="sxs-lookup"><span data-stu-id="fa0cf-112">True</span></span>|  
    ||<span data-ttu-id="fa0cf-113">消息</span><span class="sxs-lookup"><span data-stu-id="fa0cf-113">Message</span></span>|<span data-ttu-id="fa0cf-114">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="fa0cf-114">BeginDocMsg</span></span>|  
    ||<span data-ttu-id="fa0cf-115">Name</span><span class="sxs-lookup"><span data-stu-id="fa0cf-115">Name</span></span>|<span data-ttu-id="fa0cf-116">ReceiveBeginDoc</span><span class="sxs-lookup"><span data-stu-id="fa0cf-116">ReceiveBeginDoc</span></span>|  
    ||<span data-ttu-id="fa0cf-117">运算</span><span class="sxs-lookup"><span data-stu-id="fa0cf-117">Operation</span></span>|<span data-ttu-id="fa0cf-118">BeginDoc.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="fa0cf-118">BeginDoc.Operation_1.Request</span></span>|  
    |<span data-ttu-id="fa0cf-119">Send1</span><span class="sxs-lookup"><span data-stu-id="fa0cf-119">Send1</span></span>|<span data-ttu-id="fa0cf-120">消息</span><span class="sxs-lookup"><span data-stu-id="fa0cf-120">Message</span></span>|<span data-ttu-id="fa0cf-121">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="fa0cf-121">BeginDocSessionMsg</span></span>|  
    ||<span data-ttu-id="fa0cf-122">Name</span><span class="sxs-lookup"><span data-stu-id="fa0cf-122">Name</span></span>|<span data-ttu-id="fa0cf-123">SendBeginDoc</span><span class="sxs-lookup"><span data-stu-id="fa0cf-123">SendBeginDoc</span></span>|  
    ||<span data-ttu-id="fa0cf-124">运算</span><span class="sxs-lookup"><span data-stu-id="fa0cf-124">Operation</span></span>|<span data-ttu-id="fa0cf-125">JDEPort.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="fa0cf-125">JDEPort.Operation_1.Request</span></span>|  
    |<span data-ttu-id="fa0cf-126">Receive2</span><span class="sxs-lookup"><span data-stu-id="fa0cf-126">Receive2</span></span>|<span data-ttu-id="fa0cf-127">Activate</span><span class="sxs-lookup"><span data-stu-id="fa0cf-127">Activate</span></span>|<span data-ttu-id="fa0cf-128">False</span><span class="sxs-lookup"><span data-stu-id="fa0cf-128">False</span></span>|  
    ||<span data-ttu-id="fa0cf-129">消息</span><span class="sxs-lookup"><span data-stu-id="fa0cf-129">Message</span></span>|<span data-ttu-id="fa0cf-130">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="fa0cf-130">BeginDocResponseMsg</span></span>|  
    ||<span data-ttu-id="fa0cf-131">Name</span><span class="sxs-lookup"><span data-stu-id="fa0cf-131">Name</span></span>|<span data-ttu-id="fa0cf-132">ReceiveBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="fa0cf-132">ReceiveBeginDocResponse</span></span>|  
    ||<span data-ttu-id="fa0cf-133">运算</span><span class="sxs-lookup"><span data-stu-id="fa0cf-133">Operation</span></span>|<span data-ttu-id="fa0cf-134">JDEPort.Operation_1.Response</span><span class="sxs-lookup"><span data-stu-id="fa0cf-134">JDEPort.Operation_1.Response</span></span>|  
    |<span data-ttu-id="fa0cf-135">Send2</span><span class="sxs-lookup"><span data-stu-id="fa0cf-135">Send2</span></span>|<span data-ttu-id="fa0cf-136">消息</span><span class="sxs-lookup"><span data-stu-id="fa0cf-136">Message</span></span>|<span data-ttu-id="fa0cf-137">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="fa0cf-137">EditLineSessionMsg</span></span>|  
    ||<span data-ttu-id="fa0cf-138">Name</span><span class="sxs-lookup"><span data-stu-id="fa0cf-138">Name</span></span>|<span data-ttu-id="fa0cf-139">SendEditLine</span><span class="sxs-lookup"><span data-stu-id="fa0cf-139">SendEditLine</span></span>|  
    ||<span data-ttu-id="fa0cf-140">运算</span><span class="sxs-lookup"><span data-stu-id="fa0cf-140">Operation</span></span>|<span data-ttu-id="fa0cf-141">JDEPort.Operation_2.Request</span><span class="sxs-lookup"><span data-stu-id="fa0cf-141">JDEPort.Operation_2.Request</span></span>|  
    |<span data-ttu-id="fa0cf-142">Receive3</span><span class="sxs-lookup"><span data-stu-id="fa0cf-142">Receive3</span></span>|<span data-ttu-id="fa0cf-143">Activate</span><span class="sxs-lookup"><span data-stu-id="fa0cf-143">Activate</span></span>|<span data-ttu-id="fa0cf-144">False</span><span class="sxs-lookup"><span data-stu-id="fa0cf-144">False</span></span>|  
    ||<span data-ttu-id="fa0cf-145">消息</span><span class="sxs-lookup"><span data-stu-id="fa0cf-145">Message</span></span>|<span data-ttu-id="fa0cf-146">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="fa0cf-146">EditLineResponseMsg</span></span>|  
    ||<span data-ttu-id="fa0cf-147">Name</span><span class="sxs-lookup"><span data-stu-id="fa0cf-147">Name</span></span>|<span data-ttu-id="fa0cf-148">ReceiveEditLine</span><span class="sxs-lookup"><span data-stu-id="fa0cf-148">ReceiveEditLine</span></span>|  
    ||<span data-ttu-id="fa0cf-149">运算</span><span class="sxs-lookup"><span data-stu-id="fa0cf-149">Operation</span></span>|<span data-ttu-id="fa0cf-150">JDEPort.Operation_2.Response</span><span class="sxs-lookup"><span data-stu-id="fa0cf-150">JDEPort.Operation_2.Response</span></span>|  
    |<span data-ttu-id="fa0cf-151">Send3</span><span class="sxs-lookup"><span data-stu-id="fa0cf-151">Send3</span></span>|<span data-ttu-id="fa0cf-152">消息</span><span class="sxs-lookup"><span data-stu-id="fa0cf-152">Message</span></span>|<span data-ttu-id="fa0cf-153">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="fa0cf-153">EndDocSessionMsg</span></span>|  
    ||<span data-ttu-id="fa0cf-154">Name</span><span class="sxs-lookup"><span data-stu-id="fa0cf-154">Name</span></span>|<span data-ttu-id="fa0cf-155">SendEndDoc</span><span class="sxs-lookup"><span data-stu-id="fa0cf-155">SendEndDoc</span></span>|  
    ||<span data-ttu-id="fa0cf-156">运算</span><span class="sxs-lookup"><span data-stu-id="fa0cf-156">Operation</span></span>|<span data-ttu-id="fa0cf-157">JDEPort.Operation_3.Request</span><span class="sxs-lookup"><span data-stu-id="fa0cf-157">JDEPort.Operation_3.Request</span></span>|  
    |<span data-ttu-id="fa0cf-158">Receive4</span><span class="sxs-lookup"><span data-stu-id="fa0cf-158">Receive4</span></span>|<span data-ttu-id="fa0cf-159">Activate</span><span class="sxs-lookup"><span data-stu-id="fa0cf-159">Activate</span></span>|<span data-ttu-id="fa0cf-160">False</span><span class="sxs-lookup"><span data-stu-id="fa0cf-160">False</span></span>|  
    ||<span data-ttu-id="fa0cf-161">消息</span><span class="sxs-lookup"><span data-stu-id="fa0cf-161">Message</span></span>|<span data-ttu-id="fa0cf-162">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="fa0cf-162">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="fa0cf-163">Name</span><span class="sxs-lookup"><span data-stu-id="fa0cf-163">Name</span></span>|<span data-ttu-id="fa0cf-164">ReceiveEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="fa0cf-164">ReceiveEndDocResponse</span></span>|  
    ||<span data-ttu-id="fa0cf-165">运算</span><span class="sxs-lookup"><span data-stu-id="fa0cf-165">Operation</span></span>|<span data-ttu-id="fa0cf-166">JDEPort.Operation_3.Response</span><span class="sxs-lookup"><span data-stu-id="fa0cf-166">JDEPort.Operation_3.Response</span></span>|  
    |<span data-ttu-id="fa0cf-167">Send4</span><span class="sxs-lookup"><span data-stu-id="fa0cf-167">Send4</span></span>|<span data-ttu-id="fa0cf-168">消息</span><span class="sxs-lookup"><span data-stu-id="fa0cf-168">Message</span></span>|<span data-ttu-id="fa0cf-169">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="fa0cf-169">EndDocResponseMsg</span></span>|  
    ||<span data-ttu-id="fa0cf-170">Name</span><span class="sxs-lookup"><span data-stu-id="fa0cf-170">Name</span></span>|<span data-ttu-id="fa0cf-171">SendEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="fa0cf-171">SendEndDocResponse</span></span>|  
    ||<span data-ttu-id="fa0cf-172">运算</span><span class="sxs-lookup"><span data-stu-id="fa0cf-172">Operation</span></span>|<span data-ttu-id="fa0cf-173">EndDocOut.Operation_1.Request</span><span class="sxs-lookup"><span data-stu-id="fa0cf-173">EndDocOut.Operation_1.Request</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa0cf-174">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa0cf-174">See Also</span></span>  
 <span data-ttu-id="fa0cf-175">[任务 1： 创建端口](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="fa0cf-175">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="fa0cf-176">[任务 2： 创建消息](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="fa0cf-176">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="fa0cf-177">[任务 4： 配置构造消息形状](../core/task-4-configure-the-construct-message-shape2.md) </span><span class="sxs-lookup"><span data-stu-id="fa0cf-177">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape2.md) </span></span>  
 [<span data-ttu-id="fa0cf-178">任务 5： 配置转换形状</span><span class="sxs-lookup"><span data-stu-id="fa0cf-178">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)