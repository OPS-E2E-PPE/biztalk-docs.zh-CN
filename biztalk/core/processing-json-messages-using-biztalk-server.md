---
title: 处理 JSON 消息使用 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6db1421-9478-477c-8645-09eefba06246
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db57847964c7e3da452675945b7d4557ae7cbc85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986342"
---
# <a name="processing-json-messages-using-biztalk-server"></a><span data-ttu-id="cb1a7-102">使用 BizTalk Server 处理 JSON 消息</span><span class="sxs-lookup"><span data-stu-id="cb1a7-102">Processing JSON messages using BizTalk Server</span></span>
> [!NOTE]
>  <span data-ttu-id="cb1a7-103">本教程仅适用于 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="cb1a7-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="cb1a7-104">本教程说明了如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 来处理 JSON 消息。</span><span class="sxs-lookup"><span data-stu-id="cb1a7-104">This tutorial demonstrates how to process JSON messages using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="cb1a7-105">本教程使用自定义管道组件，与 BizTalk Server 现已推出。</span><span class="sxs-lookup"><span data-stu-id="cb1a7-105">The tutorial uses custom pipeline components, now available with BizTalk Server.</span></span> <span data-ttu-id="cb1a7-106">这些管道组件可在将 JSON 消息接收到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程中时将消息转换为 XML，并会在向外发送消息时将消息从 XML 转换为 JSON。</span><span class="sxs-lookup"><span data-stu-id="cb1a7-106">These pipeline components convert the JSON message to XML (while receiving the message into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration, and converts the message from XML to JSON while sending the message out.</span></span>  
  
## <a name="what-does-this-tutorial-do"></a><span data-ttu-id="cb1a7-107">本教程有什么作用？</span><span class="sxs-lookup"><span data-stu-id="cb1a7-107">What does this tutorial do?</span></span>  
 <span data-ttu-id="cb1a7-108">为了说明 JSON 处理，我们将创建一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它将按给定顺序执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cb1a7-108">To demonstrate JSON processing, we create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that does the following, in the given order:</span></span>  
  
1. <span data-ttu-id="cb1a7-109">接收 JSON 采购订单，并在接收管道中使用 JSON 解码器组件将 JSON 消息转换为 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="cb1a7-109">Receives a JSON purchase order and in the receive pipeline, uses a JSON decoder component to transform the JSON message to XML message.</span></span>  
  
2. <span data-ttu-id="cb1a7-110">使用映射将 XML 采购订单转换为 XML 发票。</span><span class="sxs-lookup"><span data-stu-id="cb1a7-110">Transforms the XML purchase order into an XML invoice using a map.</span></span>  
  
3. <span data-ttu-id="cb1a7-111">在发送管道中，使用 JSON 编码器将 XML 发票转换为 JSON 发票并发送出去。</span><span class="sxs-lookup"><span data-stu-id="cb1a7-111">In the send pipeline, uses a JSON encoder to transform the XML invoice into a JSON invoice and sends it out.</span></span>  
  
   <span data-ttu-id="cb1a7-112">![处理 BizTalk Server 中的 JSON 消息](../core/media/btsjson-flow.png "BTSJSON_Flow")</span><span class="sxs-lookup"><span data-stu-id="cb1a7-112">![Processing JSON messages in BizTalk Server](../core/media/btsjson-flow.png "BTSJSON_Flow")</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="cb1a7-113">如何使用本教程？</span><span class="sxs-lookup"><span data-stu-id="cb1a7-113">How to use this tutorial?</span></span>  
 <span data-ttu-id="cb1a7-114">本教程围绕一个示例 (**BTSJSON**)，可以从下载[MSDN 代码库](http://go.microsoft.com/fwlink/?LinkId=403197)。</span><span class="sxs-lookup"><span data-stu-id="cb1a7-114">This tutorial is built around a sample (**BTSJSON**) that can be downloaded from the [MSDN Code Gallery](http://go.microsoft.com/fwlink/?LinkId=403197).</span></span> <span data-ttu-id="cb1a7-115">你可以借助此示例和本教程来了解此示例的构建方式。</span><span class="sxs-lookup"><span data-stu-id="cb1a7-115">You could use the sample and go through this tutorial to understand how the sample was built.</span></span> <span data-ttu-id="cb1a7-116">你也可以使用本教程来从头创建自己的解决方案。</span><span class="sxs-lookup"><span data-stu-id="cb1a7-116">Or, you could use this tutorial to create your own solution ground-up.</span></span> <span data-ttu-id="cb1a7-117">本教程针对的是第二种方法，以便于你了解此解决方案的构建方式。</span><span class="sxs-lookup"><span data-stu-id="cb1a7-117">This tutorial is targeted towards the second approach so that you understand how this solution was built.</span></span> <span data-ttu-id="cb1a7-118">另外，本教程尽量与示例保持一致，并对项目（如架构、转换）使用与示例中相同的名称。</span><span class="sxs-lookup"><span data-stu-id="cb1a7-118">Also, as much as possible, the tutorial is consistent with the sample and uses the same names for artifacts (for example, schemas, transforms) as used in the sample.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cb1a7-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="cb1a7-119">In This Section</span></span>  
  
-   [<span data-ttu-id="cb1a7-120">为 JSON 消息生成 XSD 架构</span><span class="sxs-lookup"><span data-stu-id="cb1a7-120">Generate an XSD schema for JSON message</span></span>](../core/generate-an-xsd-schema-for-json-message.md)  
  
-   [<span data-ttu-id="cb1a7-121">创建处理 JSON 消息的自定义管道</span><span class="sxs-lookup"><span data-stu-id="cb1a7-121">Create custom pipelines to process JSON messages</span></span>](../core/create-custom-pipelines-to-process-json-messages.md)  
  
-   [<span data-ttu-id="cb1a7-122">创建 BizTalk Server 业务流程</span><span class="sxs-lookup"><span data-stu-id="cb1a7-122">Create a BizTalk Server orchestration</span></span>](../core/create-a-biztalk-server-orchestration.md)  
  
-   [<span data-ttu-id="cb1a7-123">部署并测试应用程序</span><span class="sxs-lookup"><span data-stu-id="cb1a7-123">Deploy and test the application</span></span>](../core/deploy-and-test-the-application.md)  
  
## <a name="see-also"></a><span data-ttu-id="cb1a7-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb1a7-124">See Also</span></span>  
 [<span data-ttu-id="cb1a7-125">BizTalk Server 教程</span><span class="sxs-lookup"><span data-stu-id="cb1a7-125">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)