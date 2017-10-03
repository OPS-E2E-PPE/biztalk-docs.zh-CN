---
title: "运行 Namespace 组件测试 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13768608-ade6-44c0-897f-d417c3408302
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0ae865e91fd6ff796cb870c71840bde8a95831e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-namespace-component-tests"></a><span data-ttu-id="8c1c3-102">运行 Namespace 组件测试</span><span class="sxs-lookup"><span data-stu-id="8c1c3-102">Running the Namespace Component Tests</span></span>
<span data-ttu-id="8c1c3-103">下面的过程演示如何能够运行的测试方案的所有四个[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]Namespace 组件示例。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-103">The following procedure shows how you can run all four of the test scenarios for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Namespace Component sample.</span></span>  
  
 <span data-ttu-id="8c1c3-104">**若要运行示例测试方案的 Namespace 组件**</span><span class="sxs-lookup"><span data-stu-id="8c1c3-104">**To run the Namespace Component sample test scenarios**</span></span>  
  
1.  <span data-ttu-id="8c1c3-105">首次运行此示例之前，请确保，接收位置和发送端口 URL 指向分发源文件中的相应子文件夹。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-105">Before you run this sample for the first time, make sure that the receive location and send port URL point to the appropriate subfolders in the source distribution files.</span></span> <span data-ttu-id="8c1c3-106">指定接收位置的子文件夹 \Source\Samples\Namespace\Test\Filedrop\In 和发送端口 URL 子文件夹 \Source\Samples\Namespace\Test\Filedrop\Out。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-106">Specify the subfolder \Source\Samples\Namespace\Test\Filedrop\In for the receive location and the subfolder \Source\Samples\Namespace\Test\Filedrop\Out for the send port URL.</span></span>  
  
2.  <span data-ttu-id="8c1c3-107">如果 GlobalBank.ESB 应用程序尚未运行，使用 Microsoft BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-107">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
3.  <span data-ttu-id="8c1c3-108">创建名为 TEST_Add_to_PassThrough.0000.ns.xml （位于你 ESB 安装文件夹的 \Source\Samples\Namespace\Test\Data\ 子文件夹中），文件副本并删除"TEST_"前缀重命名副本。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-108">Make a copy of the file named TEST_Add_to_PassThrough.0000.ns.xml (located in the \Source\Samples\Namespace\Test\Data\ subfolder of your ESB installation folder), and rename the copy by removing the "TEST_" prefix.</span></span>  
  
4.  <span data-ttu-id="8c1c3-109">将重命名的文件复制到 \Source\Samples\Namespace\Test\Filedrop\In 子文件夹。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-109">Copy the renamed file into the \Source\Samples\Namespace\Test\Filedrop\In subfolder.</span></span>  
  
5.  <span data-ttu-id="8c1c3-110">ESB 选取该消息、 将命名空间添加到其中，和到 \Source\Samples\Namespace\Test\Filedrop\Out 子文件夹中将删除该更新的消息。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-110">The ESB picks up the message, adds a namespace to it, and drops the updated message into the \Source\Samples\Namespace\Test\Filedrop\Out subfolder.</span></span> <span data-ttu-id="8c1c3-111">打开输入和输出中的文本编辑器来查看此测试的影响的文件。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-111">Open the input and output files in a text editor to see the effect of this test.</span></span>  
  
6.  <span data-ttu-id="8c1c3-112">现在运行第二个测试。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-112">Now run the second test.</span></span> <span data-ttu-id="8c1c3-113">创建名为 TEST_Add_to_Remove.0000.ns.xml 文件副本并将其通过删除"TEST_"前缀。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-113">Make a copy of the file named TEST_Add_to_Remove.0000.ns.xml and rename it by removing the "TEST_" prefix.</span></span>  
  
7.  <span data-ttu-id="8c1c3-114">将重命名的文件复制到 \Source\Samples\Namespace\Test\Filedrop\In 子文件夹。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-114">Copy the renamed file into the \Source\Samples\Namespace\Test\Filedrop\In subfolder.</span></span>  
  
8.  <span data-ttu-id="8c1c3-115">ESB 选取该消息，向其中添加一个命名空间、 中删除新的命名空间，并将到 \Source\Samples\Namespace\Test\Filedrop\Out 子文件夹中删除该更新的消息。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-115">The ESB picks up the message, adds a namespace to it, removes the new namespace, and drops the updated message into the \Source\Samples\Namespace\Test\Filedrop\Out subfolder.</span></span> <span data-ttu-id="8c1c3-116">打开输入和输出中的文本编辑器来查看此测试的影响的文件。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-116">Open the input and output files in a text editor to see the effect of this test.</span></span>  
  
9. <span data-ttu-id="8c1c3-117">现在运行第三个测试。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-117">Now run the third test.</span></span> <span data-ttu-id="8c1c3-118">创建名为 TEST_PassThrough_to_Remove.0000.ns.xml 文件副本并将其通过删除"TEST_"前缀。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-118">Make a copy of the file named TEST_PassThrough_to_Remove.0000.ns.xml and rename it by removing the "TEST_" prefix.</span></span>  
  
10. <span data-ttu-id="8c1c3-119">将重命名的文件复制到 \Source\Samples\Namespace\Test\Filedrop\In 子文件夹。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-119">Copy the renamed file into the \Source\Samples\Namespace\Test\Filedrop\In subfolder.</span></span>  
  
11. <span data-ttu-id="8c1c3-120">ESB 选取该消息中, 删除现有的命名空间，并将到 \Source\Samples\Namespace\Test\Filedrop\Out 子文件夹中删除该更新的消息。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-120">The ESB picks up the message, removes the existing namespace, and drops the updated message into the \Source\Samples\Namespace\Test\Filedrop\Out subfolder.</span></span> <span data-ttu-id="8c1c3-121">打开输入和输出中的文本编辑器来查看此测试的影响的文件。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-121">Open the input and output files in a text editor to see the effect of this test.</span></span>  
  
12. <span data-ttu-id="8c1c3-122">最后，运行第四次测试。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-122">Finally, run the fourth test.</span></span> <span data-ttu-id="8c1c3-123">创建名为 TEST_AddViaExtraction_to_PassThrough.0000.ns.xml 文件副本并将其通过删除"TEST_"前缀。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-123">Make a copy of the file named TEST_AddViaExtraction_to_PassThrough.0000.ns.xml and rename it by removing the "TEST_" prefix.</span></span>  
  
13. <span data-ttu-id="8c1c3-124">将重命名的文件复制到 \Source\Samples\Namespace\Test\Filedrop\In 子文件夹。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-124">Copy the renamed file into the \Source\Samples\Namespace\Test\Filedrop\In subfolder.</span></span>  
  
14. <span data-ttu-id="8c1c3-125">ESB 选取该消息，会在指定的元素中提取**ExtractionNodeXPath**属性，从指定的命名空间值，此元素用于创建一条消息，而到 \Source\Samples\ 删除更新的消息Namespace\Test\Filedrop\Out 子文件夹。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-125">The ESB picks up the message, extracts the element specified in the **ExtractionNodeXPath** property, creates a message from this element with the specified namespace values, and drops the updated message into the \Source\Samples\Namespace\Test\Filedrop\Out subfolder.</span></span> <span data-ttu-id="8c1c3-126">打开输入和输出中的文本编辑器来查看此测试的影响的文件。</span><span class="sxs-lookup"><span data-stu-id="8c1c3-126">Open the input and output files in a text editor to see the effect of this test.</span></span>