---
title: 运行 Namespace 组件示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f334a8-06de-4a56-a41a-3df088bf4a72
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31a7ced4587f693c13f3fd45f24057eb882f1d43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242719"
---
# <a name="running-the-namespace-component-sample"></a><span data-ttu-id="60a0e-102">运行 Namespace 组件示例</span><span class="sxs-lookup"><span data-stu-id="60a0e-102">Running the Namespace Component Sample</span></span>
<span data-ttu-id="60a0e-103">Namespace 组件示例应用程序包含四个接收位置 / 发送端口对。</span><span class="sxs-lookup"><span data-stu-id="60a0e-103">The Namespace Component sample application contains four receive location/send port pairs.</span></span> <span data-ttu-id="60a0e-104">每一对表示一个测试。</span><span class="sxs-lookup"><span data-stu-id="60a0e-104">Each pair represents a test.</span></span> <span data-ttu-id="60a0e-105">以下是四种测试：</span><span class="sxs-lookup"><span data-stu-id="60a0e-105">The following are the four tests:</span></span>  

- <span data-ttu-id="60a0e-106">**将添加到直通**。</span><span class="sxs-lookup"><span data-stu-id="60a0e-106">**Add to Pass-through**.</span></span> <span data-ttu-id="60a0e-107">此测试将命名空间添加到 XML 消息文档和消息将直接写入到一个文件，以便您可以看到新的命名空间。</span><span class="sxs-lookup"><span data-stu-id="60a0e-107">This test adds a namespace to an XML message document and writes the message directly to a file so that you can see the new namespace.</span></span> <span data-ttu-id="60a0e-108">此测试的输入的文件是 TEST_Add_to_PassThrough.0000.ns.xml。</span><span class="sxs-lookup"><span data-stu-id="60a0e-108">The input file for this test is TEST_Add_to_PassThrough.0000.ns.xml.</span></span> <span data-ttu-id="60a0e-109">此测试使用**NamespaceSampleReceivePipeline** ，其中包含**AddNamespace**组件。</span><span class="sxs-lookup"><span data-stu-id="60a0e-109">This test uses the **NamespaceSampleReceivePipeline** that contains an **AddNamespace** component.</span></span>  

- <span data-ttu-id="60a0e-110">**将添加到删除**。</span><span class="sxs-lookup"><span data-stu-id="60a0e-110">**Add to Remove**.</span></span> <span data-ttu-id="60a0e-111">此测试将命名空间添加到的 XML 文档的消息，并将其删除。</span><span class="sxs-lookup"><span data-stu-id="60a0e-111">This test adds a namespace to an XML document message and then removes it.</span></span> <span data-ttu-id="60a0e-112">它然后将消息直接写入一个文件。</span><span class="sxs-lookup"><span data-stu-id="60a0e-112">It then writes the message directly to a file.</span></span> <span data-ttu-id="60a0e-113">此测试的输入的文件是 TEST_ Add_to_Remove.0000.ns.xml。</span><span class="sxs-lookup"><span data-stu-id="60a0e-113">The input file for this test is TEST_ Add_to_Remove.0000.ns.xml.</span></span> <span data-ttu-id="60a0e-114">此测试使用**NamespaceSampleReceivePipeline** ，其中包含**AddNamespace**组件并**NamespaceSampleSendPipeline** ，其中包含**RemoveNamespace**组件。</span><span class="sxs-lookup"><span data-stu-id="60a0e-114">This test uses the **NamespaceSampleReceivePipeline** that contains an **AddNamespace** component and the **NamespaceSampleSendPipeline** that contains a **RemoveNamespace** component.</span></span>  

- <span data-ttu-id="60a0e-115">**传递到删除**。</span><span class="sxs-lookup"><span data-stu-id="60a0e-115">**Pass-through to Remove**.</span></span> <span data-ttu-id="60a0e-116">此测试从 XML 文档消息中删除所有命名空间和消息将直接写入到一个文件，以便你可以确认这一点。</span><span class="sxs-lookup"><span data-stu-id="60a0e-116">This test removes all namespaces from an XML document message and writes the message directly to a file so that you can confirm this.</span></span> <span data-ttu-id="60a0e-117">此测试的输入的文件是 TEST_PassThrough_to_Remove.0000.ns.xml。</span><span class="sxs-lookup"><span data-stu-id="60a0e-117">The input file for this test is TEST_PassThrough_to_Remove.0000.ns.xml.</span></span> <span data-ttu-id="60a0e-118">此测试使用**NamespaceSampleSendPipeline** ，其中包含**RemoveNamespace**组件。</span><span class="sxs-lookup"><span data-stu-id="60a0e-118">This test uses the **NamespaceSampleSendPipeline** that contains a **RemoveNamespace** component.</span></span>  

- <span data-ttu-id="60a0e-119">**添加通过提取到直通**。</span><span class="sxs-lookup"><span data-stu-id="60a0e-119">**Add Via Extraction to Pass-through**.</span></span> <span data-ttu-id="60a0e-120">此测试中提取**OrderDetails**元素的 XML 文档的消息并将事件写入包含文件直接将此元素的新消息。</span><span class="sxs-lookup"><span data-stu-id="60a0e-120">This test extracts the **OrderDetails** element of an XML document message and writes a new message containing this element directly to a file.</span></span> <span data-ttu-id="60a0e-121">此测试的输入的文件是 TEST_AddViaExtraction_to_PassThrough.0000.ns.xml。</span><span class="sxs-lookup"><span data-stu-id="60a0e-121">The input file for this test is TEST_AddViaExtraction_to_PassThrough.0000.ns.xml.</span></span> <span data-ttu-id="60a0e-122">此测试使用**NamespaceSampleReceivePipeline** ，其中包含**AddNamespace**组件与**ExtractionNodeXPath**属性设置为 **/CanonicalOrder/OrderDetails** （任何有效的 XPath，返回对应的元素为此属性就足够了）。</span><span class="sxs-lookup"><span data-stu-id="60a0e-122">This test uses the **NamespaceSampleReceivePipeline** that contains an **AddNamespace** component with the **ExtractionNodeXPath** property set to **/CanonicalOrder/OrderDetails** (any valid XPath that returns an element will suffice for this property).</span></span>  

  <span data-ttu-id="60a0e-123">在示例应用程序的基础的接收位置具有适用于每个测试类型的文件掩码和相关的接收端口名称在发送端口筛选器。</span><span class="sxs-lookup"><span data-stu-id="60a0e-123">The underlying receive locations in the sample application have file masks that are appropriate for each of the test types, and the related send ports filter on the receive port name.</span></span> <span data-ttu-id="60a0e-124">因此，若要执行测试，您只需相应地命名的消息放入输入文件夹。</span><span class="sxs-lookup"><span data-stu-id="60a0e-124">Therefore, to execute a test, you just drop the appropriately named message into the input folder.</span></span> <span data-ttu-id="60a0e-125">示例应用程序执行测试，并将更新后的消息放入输出文件夹使用适用于当前测试的名称，并包括消息 id。</span><span class="sxs-lookup"><span data-stu-id="60a0e-125">The sample application executes the test and drops the updated message into the output folder using a name appropriate for the current test, and including the Message ID.</span></span>  

  <span data-ttu-id="60a0e-126">本节包含下列主题：</span><span class="sxs-lookup"><span data-stu-id="60a0e-126">This section contains the following topics:</span></span>  

- [<span data-ttu-id="60a0e-127">运行命名空间组件测试</span><span class="sxs-lookup"><span data-stu-id="60a0e-127">Running the Namespace Component Tests</span></span>](../esb-toolkit/running-the-namespace-component-tests.md)  

- [<span data-ttu-id="60a0e-128">添加命名空间示例工作原理</span><span class="sxs-lookup"><span data-stu-id="60a0e-128">How the Add Namespace Sample Works</span></span>](../esb-toolkit/how-the-add-namespace-sample-works.md)  

- [<span data-ttu-id="60a0e-129">删除命名空间示例工作原理</span><span class="sxs-lookup"><span data-stu-id="60a0e-129">How the Remove Namespace Sample Works</span></span>](../esb-toolkit/how-the-remove-namespace-sample-works.md)
