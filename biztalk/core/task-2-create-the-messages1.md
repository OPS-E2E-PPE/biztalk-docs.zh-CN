---
title: 任务 2：创建消息 1> |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df908ea0-b3be-47e6-99ba-4122cb1db561
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0af56f8a289498e44129ca02b669bb76d88a268
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291484"
---
# <a name="task-2-create-the-messages"></a><span data-ttu-id="a1216-102">任务 2：创建消息</span><span class="sxs-lookup"><span data-stu-id="a1216-102">Task 2: Create the Messages</span></span>
<span data-ttu-id="a1216-103">创建以下消息，将在业务流程中使用它们。</span><span class="sxs-lookup"><span data-stu-id="a1216-103">Create the following Messages, they will be used in the orchestration.</span></span>  
  
### <a name="to-create-the-messages"></a><span data-ttu-id="a1216-104">若要创建消息</span><span class="sxs-lookup"><span data-stu-id="a1216-104">To create the messages</span></span>  
  
1.  <span data-ttu-id="a1216-105">右键单击**消息**，然后选择**新消息**。</span><span class="sxs-lookup"><span data-stu-id="a1216-105">Right-click **Message**, and then select **New Message**.</span></span>  
  
2.  <span data-ttu-id="a1216-106">在下面的示例为标识符和消息类型填充 > 架构，然后选择从显示的列表，为每个消息类型。</span><span class="sxs-lookup"><span data-stu-id="a1216-106">Fill in the following for the Identifier and the Message Type>Schema and select the type from the displayed list for each message.</span></span>  
  
    |<span data-ttu-id="a1216-107">Identifier</span><span class="sxs-lookup"><span data-stu-id="a1216-107">Identifier</span></span>|<span data-ttu-id="a1216-108">消息类型 > 架构</span><span class="sxs-lookup"><span data-stu-id="a1216-108">Message Type>Schema</span></span>|  
    |----------------|--------------------------|  
    |<span data-ttu-id="a1216-109">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="a1216-109">BeginDocMsg</span></span>|<span data-ttu-id="a1216-110">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span><span class="sxs-lookup"><span data-stu-id="a1216-110">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span></span>|  
    |<span data-ttu-id="a1216-111">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="a1216-111">BeginDocResponseMsg</span></span>|<span data-ttu-id="a1216-112">BeginDocTest.B4200310Service_1.F4211FSBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="a1216-112">BeginDocTest.B4200310Service_1.F4211FSBeginDocResponse</span></span>|  
    |<span data-ttu-id="a1216-113">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="a1216-113">BeginDocSessionMsg</span></span>|<span data-ttu-id="a1216-114">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span><span class="sxs-lookup"><span data-stu-id="a1216-114">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span></span>|  
    |<span data-ttu-id="a1216-115">EditLineMsg</span><span class="sxs-lookup"><span data-stu-id="a1216-115">EditLineMsg</span></span>|<span data-ttu-id="a1216-116">BeginDocTest.B4200310Service_1.F4211FSEditLine</span><span class="sxs-lookup"><span data-stu-id="a1216-116">BeginDocTest.B4200310Service_1.F4211FSEditLine</span></span>|  
    |<span data-ttu-id="a1216-117">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="a1216-117">EditLineResponseMsg</span></span>|<span data-ttu-id="a1216-118">BeginDocTest.B4200310Service_1.F4211FSEditLineResponse</span><span class="sxs-lookup"><span data-stu-id="a1216-118">BeginDocTest.B4200310Service_1.F4211FSEditLineResponse</span></span>|  
    |<span data-ttu-id="a1216-119">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="a1216-119">EditLineSessionMsg</span></span>|<span data-ttu-id="a1216-120">BeginDocTest.B4200310Service_1.F4211FSEditLine</span><span class="sxs-lookup"><span data-stu-id="a1216-120">BeginDocTest.B4200310Service_1.F4211FSEditLine</span></span>|  
    |<span data-ttu-id="a1216-121">EndDocMsg</span><span class="sxs-lookup"><span data-stu-id="a1216-121">EndDocMsg</span></span>|<span data-ttu-id="a1216-122">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span><span class="sxs-lookup"><span data-stu-id="a1216-122">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span></span>|  
    |<span data-ttu-id="a1216-123">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="a1216-123">EndDocResponseMsg</span></span>|<span data-ttu-id="a1216-124">BeginDocTest.B4200310Service_1.F4211FSEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="a1216-124">BeginDocTest.B4200310Service_1.F4211FSEndDocResponse</span></span>|  
    |<span data-ttu-id="a1216-125">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="a1216-125">EndDocSessionMsg</span></span>|<span data-ttu-id="a1216-126">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span><span class="sxs-lookup"><span data-stu-id="a1216-126">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1216-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1216-127">See Also</span></span>  
 <span data-ttu-id="a1216-128">[任务 1:创建端口](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="a1216-128">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="a1216-129">[任务 3:配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="a1216-129">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 <span data-ttu-id="a1216-130">[任务 4:配置构造消息形状](../core/task-4-configure-the-construct-message-shape2.md) </span><span class="sxs-lookup"><span data-stu-id="a1216-130">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape2.md) </span></span>  
 [<span data-ttu-id="a1216-131">任务 5:配置转换形状</span><span class="sxs-lookup"><span data-stu-id="a1216-131">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)