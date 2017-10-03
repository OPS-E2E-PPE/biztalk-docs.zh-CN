---
title: "教程 2： 使用.NET Echo 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e489c79-51b4-4067-9584-67c67f86aedd
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5291fc9e465476ea804cd8c46b1b53ea6c02d842
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-2-consume-the-echo-adapter-from-net"></a><span data-ttu-id="47ad7-102">教程 2： 使用.NET Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="47ad7-102">Tutorial 2: Consume the Echo Adapter from .NET</span></span>
<span data-ttu-id="47ad7-103">此部分可为使用通过.NET Echo 适配器公开的入站和出站操作的步骤。</span><span class="sxs-lookup"><span data-stu-id="47ad7-103">This section gives the steps for consuming the inbound and outbound operations exposed by the Echo adapter from .NET.</span></span> <span data-ttu-id="47ad7-104">Echo 适配器为了开发的[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="47ad7-104">The Echo adapter was developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47ad7-105">Echo 适配器和测试代码是在你 BizTalk 安装文件附带`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`或`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`。</span><span class="sxs-lookup"><span data-stu-id="47ad7-105">The Echo Adapter and test code is included with your BizTalk installation files at `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` or `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="47ad7-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="47ad7-106">In This Section</span></span>  
  
-   [<span data-ttu-id="47ad7-107">步骤 1： 测试 Echo 适配器的出站处理的程序</span><span class="sxs-lookup"><span data-stu-id="47ad7-107">Step 1: Test Outbound Handler of the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-test-outbound-handler-of-the-echo-adapter.md)  
  
-   [<span data-ttu-id="47ad7-108">步骤 2： 测试入站的回显适配器处理程序</span><span class="sxs-lookup"><span data-stu-id="47ad7-108">Step 2: Test Inbound Handler of the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="47ad7-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47ad7-109">See Also</span></span>  
 <span data-ttu-id="47ad7-110">[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="47ad7-110">[Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="47ad7-111">WCF LOB 适配器 SDK 教程</span><span class="sxs-lookup"><span data-stu-id="47ad7-111">WCF LOB Adapter SDK Tutorials</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)