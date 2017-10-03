---
title: "任务 2︰ 创建 Messages2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2db67595-bcb6-455b-ad81-07b4426b7ea4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f970e692f72af21c8b1c3c76dfdebae15350f5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="task-2-create-the-messages"></a><span data-ttu-id="ffc1e-102">任务 2： 创建消息</span><span class="sxs-lookup"><span data-stu-id="ffc1e-102">Task 2: Create the Messages</span></span>
<span data-ttu-id="ffc1e-103">请创建以下消息，业务流程中将用到这些消息。</span><span class="sxs-lookup"><span data-stu-id="ffc1e-103">Create the following Messages, which will be used in the orchestration.</span></span>  
  
### <a name="to-create-the-messages"></a><span data-ttu-id="ffc1e-104">创建消息的步骤</span><span class="sxs-lookup"><span data-stu-id="ffc1e-104">To create the messages</span></span>  
  
1.  <span data-ttu-id="ffc1e-105">右键单击**消息**，然后选择**新消息**。</span><span class="sxs-lookup"><span data-stu-id="ffc1e-105">Right-click **Message**, and then select **New Message**.</span></span>  
  
2.  <span data-ttu-id="ffc1e-106">在“标识符”和“消息类型”>“架构”中填入以下内容，然后从显示的列表中为每个消息选择类型。</span><span class="sxs-lookup"><span data-stu-id="ffc1e-106">Fill in the following for the Identifier and the Message Type>Schema and select the type from the displayed list for each message.</span></span>  
  
    |<span data-ttu-id="ffc1e-107">Identifier</span><span class="sxs-lookup"><span data-stu-id="ffc1e-107">Identifier</span></span>|<span data-ttu-id="ffc1e-108">“消息类型”>“架构”</span><span class="sxs-lookup"><span data-stu-id="ffc1e-108">Message Type > Schema</span></span>|  
    |----------------|----------------------------|  
    |<span data-ttu-id="ffc1e-109">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="ffc1e-109">BeginDocMsg</span></span>|<span data-ttu-id="ffc1e-110">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span><span class="sxs-lookup"><span data-stu-id="ffc1e-110">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span></span>|  
    |<span data-ttu-id="ffc1e-111">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="ffc1e-111">BeginDocResponseMsg</span></span>|<span data-ttu-id="ffc1e-112">BeginDocTest.B4200310Service_1.F4211FSBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="ffc1e-112">BeginDocTest.B4200310Service_1.F4211FSBeginDocResponse</span></span>|  
    |<span data-ttu-id="ffc1e-113">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="ffc1e-113">BeginDocSessionMsg</span></span>|<span data-ttu-id="ffc1e-114">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span><span class="sxs-lookup"><span data-stu-id="ffc1e-114">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span></span>|  
    |<span data-ttu-id="ffc1e-115">EditLineMsg</span><span class="sxs-lookup"><span data-stu-id="ffc1e-115">EditLineMsg</span></span>|<span data-ttu-id="ffc1e-116">BeginDocTest.B4200310Service_1.F4211FSEditLine</span><span class="sxs-lookup"><span data-stu-id="ffc1e-116">BeginDocTest.B4200310Service_1.F4211FSEditLine</span></span>|  
    |<span data-ttu-id="ffc1e-117">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="ffc1e-117">EditLineResponseMsg</span></span>|<span data-ttu-id="ffc1e-118">BeginDocTest.B4200310Service_1.F4211FSEditLineResponse</span><span class="sxs-lookup"><span data-stu-id="ffc1e-118">BeginDocTest.B4200310Service_1.F4211FSEditLineResponse</span></span>|  
    |<span data-ttu-id="ffc1e-119">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="ffc1e-119">EditLineSessionMsg</span></span>|<span data-ttu-id="ffc1e-120">BeginDocTest.B4200310Service_1.F4211FSEditLine</span><span class="sxs-lookup"><span data-stu-id="ffc1e-120">BeginDocTest.B4200310Service_1.F4211FSEditLine</span></span>|  
    |<span data-ttu-id="ffc1e-121">EndDocMsg</span><span class="sxs-lookup"><span data-stu-id="ffc1e-121">EndDocMsg</span></span>|<span data-ttu-id="ffc1e-122">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span><span class="sxs-lookup"><span data-stu-id="ffc1e-122">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span></span>|  
    |<span data-ttu-id="ffc1e-123">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="ffc1e-123">EndDocResponseMsg</span></span>|<span data-ttu-id="ffc1e-124">BeginDocTest.B4200310Service_1.F4211FSEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="ffc1e-124">BeginDocTest.B4200310Service_1.F4211FSEndDocResponse</span></span>|  
    |<span data-ttu-id="ffc1e-125">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="ffc1e-125">EndDocSessionMsg</span></span>|<span data-ttu-id="ffc1e-126">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span><span class="sxs-lookup"><span data-stu-id="ffc1e-126">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ffc1e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffc1e-127">See Also</span></span>  
 <span data-ttu-id="ffc1e-128">[任务 1： 创建端口](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="ffc1e-128">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="ffc1e-129">[任务 3： 配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes2.md) </span><span class="sxs-lookup"><span data-stu-id="ffc1e-129">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes2.md) </span></span>  
 <span data-ttu-id="ffc1e-130">[任务 4： 配置构造消息形状](../core/task-4-configure-the-construct-message-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="ffc1e-130">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape1.md) </span></span>  
 [<span data-ttu-id="ffc1e-131">任务 5： 配置转换形状</span><span class="sxs-lookup"><span data-stu-id="ffc1e-131">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)