---
title: 教程以了解 WCF LOB 适配器 SDK |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99002b01-da8a-483e-ada3-1ffbe9cd7357
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3efc47a5df445e18e4a78a005c31791fe1f1fa24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226117"
---
# <a name="tutorials-to-learn-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="04d44-102">若要了解 WCF LOB 适配器 SDK 的教程</span><span class="sxs-lookup"><span data-stu-id="04d44-102">Tutorials to learn the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="04d44-103">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]教程包含有关如何使用信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]开发功能丰富线业务适配器以便于您的企业中企业应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="04d44-103">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] tutorials contain information about how you can use [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] to develop feature-rich line of business adapters to facilitate enterprise application integration within your enterprise.</span></span> <span data-ttu-id="04d44-104">通过使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，可由任何应用程序可以使用 WCF 绑定使用的操作和你公开的数据包括[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="04d44-104">By using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], the operations and data you expose can be consumed by any application that can consume a WCF binding, including [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="04d44-105">本教程包含围绕一组预定义的操作的简单示例。</span><span class="sxs-lookup"><span data-stu-id="04d44-105">The tutorials contain simple examples built around a set of predefined operations.</span></span> <span data-ttu-id="04d44-106">不需要企业系统可用于完成这些教程的实际行。</span><span class="sxs-lookup"><span data-stu-id="04d44-106">You do not need an actual line of business system available to complete these tutorials.</span></span> <span data-ttu-id="04d44-107">但是，这些教程中提供的详细信息可应用于你适配器的开发需求中,，从了解元数据来编写出站的处理程序和更高版本。</span><span class="sxs-lookup"><span data-stu-id="04d44-107">However, details provided in the tutorials can be applied to your adapter development needs, from understanding metadata to writing outbound handlers and beyond.</span></span>  

> [!TIP]
> <span data-ttu-id="04d44-108">已完成的 Echo 适配器是在你 BizTalk 安装文件附带`\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples`或`\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`。</span><span class="sxs-lookup"><span data-stu-id="04d44-108">The completed Echo Adapter is included with your BizTalk installation files at `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` or `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.</span></span>
  
 <span data-ttu-id="04d44-109">使用以下教程以了解如何使用的关键部分[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="04d44-109">Use the following tutorials to learn how to use key parts of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]:</span></span>  
  
-   <span data-ttu-id="04d44-110">[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="04d44-110">[Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).</span></span> <span data-ttu-id="04d44-111">提供有关创建适配器，公开从一组预定义的方法，后者将作为企业系统的行的字符串操作的分步说明。</span><span class="sxs-lookup"><span data-stu-id="04d44-111">Provides step-by-step instructions for creating an adapter that exposes string operations from a set of predefined methods that act as the line of business system.</span></span> <span data-ttu-id="04d44-112">适配器提供了许多常用的处理程序中实现[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]包括搜索、 浏览、 入站和出站操作。</span><span class="sxs-lookup"><span data-stu-id="04d44-112">The adapter provides an implementation for many of the common handlers in the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] including search, browse, inbound and outbound operations.</span></span> <span data-ttu-id="04d44-113">在成功完成本教程中，你将具有的功能的适配器。</span><span class="sxs-lookup"><span data-stu-id="04d44-113">At the successful completion of this tutorial, you will have a functional adapter.</span></span>  
  
-   <span data-ttu-id="04d44-114">[教程 2： 使用.NET Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)。</span><span class="sxs-lookup"><span data-stu-id="04d44-114">[Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md).</span></span> <span data-ttu-id="04d44-115">提供使用 Echo 适配器开发中的分步指导[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)从.NET 项目。</span><span class="sxs-lookup"><span data-stu-id="04d44-115">Provides step-by-step instructions for consuming the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) from a .NET project.</span></span> <span data-ttu-id="04d44-116">将添加到新项目中，适配器服务引用，并提供代码来测试 Echo 适配器的入站和出站操作。</span><span class="sxs-lookup"><span data-stu-id="04d44-116">You will add an adapter service reference to a new project, and provide code to test the inbound and outbound operations of the Echo Adapter.</span></span>  
  
-   <span data-ttu-id="04d44-117">[教程 3： 承载在 IIS 中的 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)。</span><span class="sxs-lookup"><span data-stu-id="04d44-117">[Tutorial 3: Hosting the Echo Adapter in IIS](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md).</span></span> <span data-ttu-id="04d44-118">提供承载 Echo 适配器开发中的分步指导[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)Internet 信息服务 (IIS) 中处理。</span><span class="sxs-lookup"><span data-stu-id="04d44-118">Provides step-by-step instructions for hosting the Echo Adapter developed in [Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) in the Internet Information Services (IIS) process.</span></span> <span data-ttu-id="04d44-119">你还将使用 svcutil.exe （ServiceModel 元数据实用工具） 创建简单的客户端应用程序使用托管适配器 EchoString 操作。</span><span class="sxs-lookup"><span data-stu-id="04d44-119">You will also use svcutil.exe (ServiceModel Metadata Utility) to create a simple client application to consume the EchoString operation of the hosted adapter.</span></span>  
  
 <span data-ttu-id="04d44-120">这些教程提供了了解的一些关键功能的结构化的方法[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="04d44-120">These tutorials provide a structured approach to understanding some of the key features of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="04d44-121">它们可以已完成，但不知道[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]或[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="04d44-121">They can be completed with no knowledge of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] or [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].</span></span> <span data-ttu-id="04d44-122">但是，你将了解详细了解适配器设计背后的概念并了解如何适配器设计可帮助实现过程中如果[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="04d44-122">However, you will learn more if you understand the concepts behind adapter design, and understand how adapter design is facilitated in the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="04d44-123">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="04d44-123">For more information, see:</span></span>  
  
-   [<span data-ttu-id="04d44-124">常见的开发人员任务 wcf LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="04d44-124">Common Developer Tasks for the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/common-developer-tasks-for-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="04d44-125">WCF LOB 适配器 SDK 的关键组成部分</span><span class="sxs-lookup"><span data-stu-id="04d44-125">Key Components of the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/key-components-of-the-wcf-lob-adapter-sdk.md)  
  
 <span data-ttu-id="04d44-126">在开始这些教程之前，应查看中的要求[在开始本教程之前](../../core/before-you-begin-the-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="04d44-126">Before you begin these tutorials, you should review the requirements in [Before You Begin the Tutorials](../../core/before-you-begin-the-tutorial.md).</span></span>  
  
 
## <a name="in-this-section"></a><span data-ttu-id="04d44-127">本节内容</span><span class="sxs-lookup"><span data-stu-id="04d44-127">In This Section</span></span>  
  
-   [<span data-ttu-id="04d44-128">在开始本教程之前</span><span class="sxs-lookup"><span data-stu-id="04d44-128">Before You Begin the Tutorials</span></span>](../../core/before-you-begin-the-tutorial.md)  
  
-   [<span data-ttu-id="04d44-129">教程 1： 开发 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="04d44-129">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)  
  
-   [<span data-ttu-id="04d44-130">教程 2： 使用.NET Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="04d44-130">Tutorial 2: Consume the Echo Adapter from .NET</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)  
  
-   [<span data-ttu-id="04d44-131">教程 3： 承载在 IIS 中的 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="04d44-131">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)  
  
## <a name="see-also"></a><span data-ttu-id="04d44-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04d44-132">See Also</span></span>  
 [<span data-ttu-id="04d44-133">BizTalk Server 入门</span><span class="sxs-lookup"><span data-stu-id="04d44-133">Getting started with BizTalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)