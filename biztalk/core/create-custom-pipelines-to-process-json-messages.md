---
title: 创建自定义管道来处理 JSON 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b04faad1-b14b-4146-82c7-88a38d2a46a5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20b5600cfa54e5df6ae72c3a5f3bb03a255d4c08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354279"
---
# <a name="create-custom-pipelines-to-process-json-messages"></a><span data-ttu-id="be7a0-102">创建自定义管道来处理 JSON 消息</span><span class="sxs-lookup"><span data-stu-id="be7a0-102">Create custom pipelines to process JSON messages</span></span>
> [!NOTE]
>  <span data-ttu-id="be7a0-103">本教程仅适用于 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="be7a0-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="be7a0-104">提供可用于处理 JSON 消息中的管道组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="be7a0-104">provides pipeline components that can be used to process JSON messages within a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="be7a0-105">在此步骤中，我们使用这些管道组件来创建可以在配置时使用的自定义管道[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="be7a0-105">In this step, we use those pipeline components to create custom pipelines that can be used when configuring a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="create-a-custom-receive-pipeline"></a><span data-ttu-id="be7a0-106">创建自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="be7a0-106">Create a custom receive pipeline</span></span>  
  
1. <span data-ttu-id="be7a0-107">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，从解决方案资源管理器，右键单击项目，然后指向**添加** > **新项** > **接收管道**.</span><span class="sxs-lookup"><span data-stu-id="be7a0-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Receive Pipeline**.</span></span> <span data-ttu-id="be7a0-108">管道命名为`JSONToXmlReceivePipeline.btp`，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="be7a0-108">Provide the pipeline name as `JSONToXmlReceivePipeline.btp`, and then click **Add**.</span></span>  
  
2. <span data-ttu-id="be7a0-109">内**解码**阶段将添加新**JSON 解码器**。</span><span class="sxs-lookup"><span data-stu-id="be7a0-109">Within the **Decode** stage add the new **JSON decoder**.</span></span> <span data-ttu-id="be7a0-110">中的其他阶段以及其他管道组件，如屏幕截图中中, 所示，并保存更改。</span><span class="sxs-lookup"><span data-stu-id="be7a0-110">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
    <span data-ttu-id="be7a0-111">![自定义接收管道](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span><span class="sxs-lookup"><span data-stu-id="be7a0-111">![Custom receive pipeline](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span></span>  
  
## <a name="create-a-custom-send-pipeline"></a><span data-ttu-id="be7a0-112">创建自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="be7a0-112">Create a custom send pipeline</span></span>  
  
1. <span data-ttu-id="be7a0-113">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，从解决方案资源管理器，右键单击项目，然后指向**添加** > **新项** > **发送管道**.</span><span class="sxs-lookup"><span data-stu-id="be7a0-113">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Send Pipeline**.</span></span> <span data-ttu-id="be7a0-114">管道命名为`XmlToJSONSendPipeline.btp`，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="be7a0-114">Provide the pipeline name as `XmlToJSONSendPipeline.btp`, and then click **Add**.</span></span>  
  
2. <span data-ttu-id="be7a0-115">内**编码**阶段将添加新**JSON 编码器**。</span><span class="sxs-lookup"><span data-stu-id="be7a0-115">Within the **Encode** stage add the new **JSON encoder**.</span></span> <span data-ttu-id="be7a0-116">中的其他阶段以及其他管道组件，如屏幕截图中中, 所示，并保存更改。</span><span class="sxs-lookup"><span data-stu-id="be7a0-116">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
    <span data-ttu-id="be7a0-117">![自定义发送管道](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span><span class="sxs-lookup"><span data-stu-id="be7a0-117">![Custom send pipeline](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be7a0-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="be7a0-118">See Also</span></span>  
 [<span data-ttu-id="be7a0-119">使用 BizTalk Server 处理 JSON 消息</span><span class="sxs-lookup"><span data-stu-id="be7a0-119">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)