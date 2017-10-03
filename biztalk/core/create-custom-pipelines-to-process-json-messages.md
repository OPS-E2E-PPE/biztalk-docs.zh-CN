---
title: "创建自定义管道处理 JSON 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b04faad1-b14b-4146-82c7-88a38d2a46a5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86c85f1a45dceb812fc805a66701653642d0ccb6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-custom-pipelines-to-process-json-messages"></a><span data-ttu-id="d3ece-102">创建处理 JSON 消息的自定义管道</span><span class="sxs-lookup"><span data-stu-id="d3ece-102">Create custom pipelines to process JSON messages</span></span>
> [!NOTE]
>  <span data-ttu-id="d3ece-103">本教程仅适用于 [!INCLUDE[prague](../includes/prague-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3ece-103">This tutorial applies to [!INCLUDE[prague](../includes/prague-md.md)] only.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d3ece-104"> 提供了可用于处理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序中的 JSON 消息的管道组件。</span><span class="sxs-lookup"><span data-stu-id="d3ece-104"> provides pipeline components that can be used to process JSON messages within a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span> <span data-ttu-id="d3ece-105">在此步骤中，我们使用这些管道组件来创建自定义管道，在配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序时使用。</span><span class="sxs-lookup"><span data-stu-id="d3ece-105">In this step, we use those pipeline components to create custom pipelines that can be used when configuring a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application.</span></span>  
  
## <a name="create-a-custom-receive-pipeline"></a><span data-ttu-id="d3ece-106">创建自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="d3ece-106">Create a custom receive pipeline</span></span>  
  
1.  <span data-ttu-id="d3ece-107">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，从解决方案资源管理器，右键单击项目，然后指向**添加** > **新项** > **接收管道**.</span><span class="sxs-lookup"><span data-stu-id="d3ece-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Receive Pipeline**.</span></span> <span data-ttu-id="d3ece-108">提供将管道名称作为`JSONToXmlReceivePipeline.btp`，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d3ece-108">Provide the pipeline name as `JSONToXmlReceivePipeline.btp`, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="d3ece-109">在**解码**阶段添加新**JSON 解码器**。</span><span class="sxs-lookup"><span data-stu-id="d3ece-109">Within the **Decode** stage add the new **JSON decoder**.</span></span> <span data-ttu-id="d3ece-110">在屏幕快照中所示的其他阶段以及其他管道组件中，保存更改。</span><span class="sxs-lookup"><span data-stu-id="d3ece-110">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
     <span data-ttu-id="d3ece-111">![自定义接收管道](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span><span class="sxs-lookup"><span data-stu-id="d3ece-111">![Custom receive pipeline](../core/media/btsjson-receivepipeline.png "BTSJSON_ReceivePipeline")</span></span>  
  
## <a name="create-a-custom-send-pipeline"></a><span data-ttu-id="d3ece-112">创建自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="d3ece-112">Create a custom send pipeline</span></span>  
  
1.  <span data-ttu-id="d3ece-113">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，从解决方案资源管理器，右键单击项目，然后指向**添加** > **新项** > **发送管道**.</span><span class="sxs-lookup"><span data-stu-id="d3ece-113">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application, from the Solution Explorer, right-click the project, and point to **Add** > **New Item** > **Send Pipeline**.</span></span> <span data-ttu-id="d3ece-114">提供将管道名称作为`XmlToJSONSendPipeline.btp`，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d3ece-114">Provide the pipeline name as `XmlToJSONSendPipeline.btp`, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="d3ece-115">在**编码**阶段添加新**JSON 编码器**。</span><span class="sxs-lookup"><span data-stu-id="d3ece-115">Within the **Encode** stage add the new **JSON encoder**.</span></span> <span data-ttu-id="d3ece-116">在屏幕快照中所示的其他阶段以及其他管道组件中，保存更改。</span><span class="sxs-lookup"><span data-stu-id="d3ece-116">In the other stages and other pipeline components as shown in the screenshot, and save changes.</span></span>  
  
     <span data-ttu-id="d3ece-117">![自定义发送管道](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span><span class="sxs-lookup"><span data-stu-id="d3ece-117">![Custom send pipeline](../core/media/btsjson-sendpipeline.png "BTSJSON_SendPipeline")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ece-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3ece-118">See Also</span></span>  
 [<span data-ttu-id="d3ece-119">使用 BizTalk Server 处理 JSON 消息</span><span class="sxs-lookup"><span data-stu-id="d3ece-119">Processing JSON messages using BizTalk Server</span></span>](../core/processing-json-messages-using-biztalk-server.md)