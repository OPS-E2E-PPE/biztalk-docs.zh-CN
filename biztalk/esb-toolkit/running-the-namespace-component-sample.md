---
title: "运行 Namespace 组件示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f334a8-06de-4a56-a41a-3df088bf4a72
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fc142ca70971f023e491dbdeee693a8d41c42fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-namespace-component-sample"></a><span data-ttu-id="d0d6f-102">运行 Namespace 组件示例</span><span class="sxs-lookup"><span data-stu-id="d0d6f-102">Running the Namespace Component Sample</span></span>
<span data-ttu-id="d0d6f-103">Namespace 组件示例应用程序包含四个接收位置/发送端口对。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-103">The Namespace Component sample application contains four receive location/send port pairs.</span></span> <span data-ttu-id="d0d6f-104">每个对表示一个测试。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-104">Each pair represents a test.</span></span> <span data-ttu-id="d0d6f-105">以下是四种测试：</span><span class="sxs-lookup"><span data-stu-id="d0d6f-105">The following are the four tests:</span></span>  
  
-   <span data-ttu-id="d0d6f-106">**将添加到传递**。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-106">**Add to Pass-through**.</span></span> <span data-ttu-id="d0d6f-107">此测试将命名空间添加到 XML 消息文档，并将消息直接写入文件，以便你可以看到新的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-107">This test adds a namespace to an XML message document and writes the message directly to a file so that you can see the new namespace.</span></span> <span data-ttu-id="d0d6f-108">此测试的输入的文件是 TEST_Add_to_PassThrough.0000.ns.xml。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-108">The input file for this test is TEST_Add_to_PassThrough.0000.ns.xml.</span></span> <span data-ttu-id="d0d6f-109">此测试使用**NamespaceSampleReceivePipeline**包含**AddNamespace**组件。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-109">This test uses the **NamespaceSampleReceivePipeline** that contains an **AddNamespace** component.</span></span>  
  
-   <span data-ttu-id="d0d6f-110">**将添加到删除**。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-110">**Add to Remove**.</span></span> <span data-ttu-id="d0d6f-111">此测试将命名空间添加为 XML 文档消息，并将其删除。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-111">This test adds a namespace to an XML document message and then removes it.</span></span> <span data-ttu-id="d0d6f-112">它然后将消息直接写入文件。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-112">It then writes the message directly to a file.</span></span> <span data-ttu-id="d0d6f-113">此测试的输入的文件是 TEST_ Add_to_Remove.0000.ns.xml。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-113">The input file for this test is TEST_ Add_to_Remove.0000.ns.xml.</span></span> <span data-ttu-id="d0d6f-114">此测试使用**NamespaceSampleReceivePipeline**包含**AddNamespace**组件和**NamespaceSampleSendPipeline**包含**RemoveNamespace**组件。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-114">This test uses the **NamespaceSampleReceivePipeline** that contains an **AddNamespace** component and the **NamespaceSampleSendPipeline** that contains a **RemoveNamespace** component.</span></span>  
  
-   <span data-ttu-id="d0d6f-115">**传递到删除**。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-115">**Pass-through to Remove**.</span></span> <span data-ttu-id="d0d6f-116">此测试从 XML 文档消息中移除所有命名空间，并将消息直接写入文件，以便你可以对此进行确认。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-116">This test removes all namespaces from an XML document message and writes the message directly to a file so that you can confirm this.</span></span> <span data-ttu-id="d0d6f-117">此测试的输入的文件是 TEST_PassThrough_to_Remove.0000.ns.xml。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-117">The input file for this test is TEST_PassThrough_to_Remove.0000.ns.xml.</span></span> <span data-ttu-id="d0d6f-118">此测试使用**NamespaceSampleSendPipeline**包含**RemoveNamespace**组件。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-118">This test uses the **NamespaceSampleSendPipeline** that contains a **RemoveNamespace** component.</span></span>  
  
-   <span data-ttu-id="d0d6f-119">**通过传递到提取添加**。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-119">**Add Via Extraction to Pass-through**.</span></span> <span data-ttu-id="d0d6f-120">此测试中提取**OrderDetails**元素的 XML 文档的消息和写入新消息包含此元素直接到文件。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-120">This test extracts the **OrderDetails** element of an XML document message and writes a new message containing this element directly to a file.</span></span> <span data-ttu-id="d0d6f-121">此测试的输入的文件是 TEST_AddViaExtraction_to_PassThrough.0000.ns.xml。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-121">The input file for this test is TEST_AddViaExtraction_to_PassThrough.0000.ns.xml.</span></span> <span data-ttu-id="d0d6f-122">此测试使用**NamespaceSampleReceivePipeline**包含**AddNamespace**组件**ExtractionNodeXPath**属性设置为**/CanonicalOrder/OrderDetails** （任何有效的 XPath，它返回元素。 此属性就足够了）。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-122">This test uses the **NamespaceSampleReceivePipeline** that contains an **AddNamespace** component with the **ExtractionNodeXPath** property set to **/CanonicalOrder/OrderDetails** (any valid XPath that returns an element will suffice for this property).</span></span>  
  
 <span data-ttu-id="d0d6f-123">在示例应用程序的基础接收位置具有文件掩码适用于每个测试类型中，并相关，则将发送端口筛选器上的接收端口名称。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-123">The underlying receive locations in the sample application have file masks that are appropriate for each of the test types, and the related send ports filter on the receive port name.</span></span> <span data-ttu-id="d0d6f-124">因此，若要执行测试，你只需放在适当命名的消息的输入的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-124">Therefore, to execute a test, you just drop the appropriately named message into the input folder.</span></span> <span data-ttu-id="d0d6f-125">示例应用程序执行测试并将更新的消息放置到输出文件夹中使用适用于当前的测试，名称且包括消息 id。</span><span class="sxs-lookup"><span data-stu-id="d0d6f-125">The sample application executes the test and drops the updated message into the output folder using a name appropriate for the current test, and including the Message ID.</span></span>  
  
 <span data-ttu-id="d0d6f-126">本节包含下列主题：</span><span class="sxs-lookup"><span data-stu-id="d0d6f-126">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="d0d6f-127">运行 Namespace 组件测试</span><span class="sxs-lookup"><span data-stu-id="d0d6f-127">Running the Namespace Component Tests</span></span>](../esb-toolkit/running-the-namespace-component-tests.md)  
  
-   [<span data-ttu-id="d0d6f-128">如何添加 Namespace 示例的工作机制</span><span class="sxs-lookup"><span data-stu-id="d0d6f-128">How the Add Namespace Sample Works</span></span>](../esb-toolkit/how-the-add-namespace-sample-works.md)  
  
-   [<span data-ttu-id="d0d6f-129">删除 Namespace 示例的工作原理</span><span class="sxs-lookup"><span data-stu-id="d0d6f-129">How the Remove Namespace Sample Works</span></span>](../esb-toolkit/how-the-remove-namespace-sample-works.md)