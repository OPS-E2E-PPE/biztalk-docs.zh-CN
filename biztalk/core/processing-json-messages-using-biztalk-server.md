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
ms.openlocfilehash: 7336b515d196fadc6e8e6cc4fe0bcf500b883189
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396984"
---
# <a name="processing-json-messages-using-biztalk-server"></a><span data-ttu-id="ac925-102">使用 BizTalk Server 处理 JSON 消息</span><span class="sxs-lookup"><span data-stu-id="ac925-102">Processing JSON messages using BizTalk Server</span></span>
> [!NOTE]
>  <span data-ttu-id="ac925-103">本教程仅适用于 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="ac925-103">This tutorial applies to BizTalk Server only.</span></span>  
  
 <span data-ttu-id="ac925-104">本教程演示如何处理 JSON 消息使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ac925-104">This tutorial demonstrates how to process JSON messages using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="ac925-105">本教程使用自定义管道组件，与 BizTalk Server 现已推出。</span><span class="sxs-lookup"><span data-stu-id="ac925-105">The tutorial uses custom pipeline components, now available with BizTalk Server.</span></span> <span data-ttu-id="ac925-106">这些管道组件将 JSON 消息转换为 XML (接收到消息时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程，并将转换该消息从 XML 到 JSON 时将消息发送。</span><span class="sxs-lookup"><span data-stu-id="ac925-106">These pipeline components convert the JSON message to XML (while receiving the message into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration, and converts the message from XML to JSON while sending the message out.</span></span>  
  
## <a name="what-does-this-tutorial-do"></a><span data-ttu-id="ac925-107">此教程，请执行是什么？</span><span class="sxs-lookup"><span data-stu-id="ac925-107">What does this tutorial do?</span></span>  
 <span data-ttu-id="ac925-108">为了说明 JSON 处理，我们将创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以下内容，按给定顺序执行的：</span><span class="sxs-lookup"><span data-stu-id="ac925-108">To demonstrate JSON processing, we create a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that does the following, in the given order:</span></span>  
  
1. <span data-ttu-id="ac925-109">接收 JSON 采购订单并在接收管道中，使用 JSON 解码器组件将转换为 XML 消息的 JSON 消息。</span><span class="sxs-lookup"><span data-stu-id="ac925-109">Receives a JSON purchase order and in the receive pipeline, uses a JSON decoder component to transform the JSON message to XML message.</span></span>  
  
2. <span data-ttu-id="ac925-110">将 XML 采购订单转换为使用映射的 XML 发票。</span><span class="sxs-lookup"><span data-stu-id="ac925-110">Transforms the XML purchase order into an XML invoice using a map.</span></span>  
  
3. <span data-ttu-id="ac925-111">在发送管道中，使用 JSON 编码器将 XML 转换为 JSON 发票发票并发送出去。</span><span class="sxs-lookup"><span data-stu-id="ac925-111">In the send pipeline, uses a JSON encoder to transform the XML invoice into a JSON invoice and sends it out.</span></span>  
  
   <span data-ttu-id="ac925-112">![处理 BizTalk Server 中的 JSON 消息](../core/media/btsjson-flow.png "BTSJSON_Flow")</span><span class="sxs-lookup"><span data-stu-id="ac925-112">![Processing JSON messages in BizTalk Server](../core/media/btsjson-flow.png "BTSJSON_Flow")</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="ac925-113">如何使用此教程？</span><span class="sxs-lookup"><span data-stu-id="ac925-113">How to use this tutorial?</span></span>  
 <span data-ttu-id="ac925-114">本教程围绕一个示例 (**BTSJSON**)，可以从下载[MSDN 代码库](http://go.microsoft.com/fwlink/?LinkId=403197)。</span><span class="sxs-lookup"><span data-stu-id="ac925-114">This tutorial is built around a sample (**BTSJSON**) that can be downloaded from the [MSDN Code Gallery](http://go.microsoft.com/fwlink/?LinkId=403197).</span></span> <span data-ttu-id="ac925-115">可使用该示例并浏览本教程来了解该示例如何生成。</span><span class="sxs-lookup"><span data-stu-id="ac925-115">You could use the sample and go through this tutorial to understand how the sample was built.</span></span> <span data-ttu-id="ac925-116">或者，可以使用本教程来创建你自己的解决方案从头。</span><span class="sxs-lookup"><span data-stu-id="ac925-116">Or, you could use this tutorial to create your own solution ground-up.</span></span> <span data-ttu-id="ac925-117">本教程主要用于第二种方法，以便您了解此解决方案的构建方式。</span><span class="sxs-lookup"><span data-stu-id="ac925-117">This tutorial is targeted towards the second approach so that you understand how this solution was built.</span></span> <span data-ttu-id="ac925-118">此外，尽可能多地，教程是与示例一致，作为使用与示例中使用的项目 （例如，架构、 转换） 相同的名称。</span><span class="sxs-lookup"><span data-stu-id="ac925-118">Also, as much as possible, the tutorial is consistent with the sample and uses the same names for artifacts (for example, schemas, transforms) as used in the sample.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac925-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="ac925-119">In This Section</span></span>  
  
-   [<span data-ttu-id="ac925-120">为 JSON 消息生成 XSD 架构</span><span class="sxs-lookup"><span data-stu-id="ac925-120">Generate an XSD schema for JSON message</span></span>](../core/generate-an-xsd-schema-for-json-message.md)  
  
-   [<span data-ttu-id="ac925-121">创建处理 JSON 消息的自定义管道</span><span class="sxs-lookup"><span data-stu-id="ac925-121">Create custom pipelines to process JSON messages</span></span>](../core/create-custom-pipelines-to-process-json-messages.md)  
  
-   [<span data-ttu-id="ac925-122">创建 BizTalk Server 业务流程</span><span class="sxs-lookup"><span data-stu-id="ac925-122">Create a BizTalk Server orchestration</span></span>](../core/create-a-biztalk-server-orchestration.md)  
  
-   [<span data-ttu-id="ac925-123">部署并测试应用程序</span><span class="sxs-lookup"><span data-stu-id="ac925-123">Deploy and test the application</span></span>](../core/deploy-and-test-the-application.md)  
  
## <a name="see-also"></a><span data-ttu-id="ac925-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac925-124">See Also</span></span>  
 [<span data-ttu-id="ac925-125">BizTalk Server 教程</span><span class="sxs-lookup"><span data-stu-id="ac925-125">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)