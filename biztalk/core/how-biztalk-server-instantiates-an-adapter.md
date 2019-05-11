---
title: BizTalk Server 如何实例化适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ebe7585-5939-4142-9281-990b4849e28d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4082d9ac17ce7e97b94cd9b585eb1a6ce326f0e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344227"
---
# <a name="how-biztalk-server-instantiates-an-adapter"></a><span data-ttu-id="992a8-102">BizTalk Server 如何实例化适配器</span><span class="sxs-lookup"><span data-stu-id="992a8-102">How BizTalk Server Instantiates an Adapter</span></span>
<span data-ttu-id="992a8-103">BizTalk 服务启动时，所有接收适配器进行实例化，只要它们具有一个或多个已配置且处于活动状态的接收位置。</span><span class="sxs-lookup"><span data-stu-id="992a8-103">When the BizTalk service starts, all receive adapters are instantiated, as long as they have one or more configured and active receive locations.</span></span> <span data-ttu-id="992a8-104">默认情况下，直到要通过使用发送的第一个消息从队列删除消息引擎不实例化发送适配器的发送适配器。</span><span class="sxs-lookup"><span data-stu-id="992a8-104">By default a send adapter is not instantiated until the Messaging Engine removes from the queue the first message to be sent by using that send adapter.</span></span> <span data-ttu-id="992a8-105">（这有时称为"懒创建。）但是，如果需要实例化发送适配器在服务启动，则可以使用**InitTransmitterOnServiceStart**适配器功能。</span><span class="sxs-lookup"><span data-stu-id="992a8-105">(This is sometimes called "lazy creation.") However, if you need to instantiate a send adapter on service startup, you can use the **InitTransmitterOnServiceStart** adapter capability.</span></span> <span data-ttu-id="992a8-106">这会指示消息引擎在服务启动，而不是使用默认延迟创建创建发送适配器。</span><span class="sxs-lookup"><span data-stu-id="992a8-106">This directs the Messaging Engine to create the send adapter on service startup rather than using the default lazy creation.</span></span> <span data-ttu-id="992a8-107">默认的懒创建方法有助于减少终结点上未配置适配器时使用的系统资源的数量。</span><span class="sxs-lookup"><span data-stu-id="992a8-107">The default lazy creation approach helps to reduce the amount of system resources used when adapters are not configured on endpoints.</span></span>  
  
 <span data-ttu-id="992a8-108">创建自定义适配器时，我们建议使用托管的代码。</span><span class="sxs-lookup"><span data-stu-id="992a8-108">When you create a custom adapter, we recommend that you use managed code.</span></span> <span data-ttu-id="992a8-109">但是，就可以使用本机 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="992a8-109">However, it is possible to use native COM components.</span></span> <span data-ttu-id="992a8-110">对于 COM 组件实例化适配器中采用正常方式使用**CoCreateInstance**。</span><span class="sxs-lookup"><span data-stu-id="992a8-110">For COM components the adapter is instantiated in the normal manner using **CoCreateInstance**.</span></span>  
  
 <span data-ttu-id="992a8-111">对于托管代码中，您需要指定.NET**类型**配置文件中; 中的程序集路径是可选的。</span><span class="sxs-lookup"><span data-stu-id="992a8-111">For managed code, you need to specify the .NET **type** in the configuration file; the assembly path is optional.</span></span>  
  
 <span data-ttu-id="992a8-112">可能的部署选项包括：</span><span class="sxs-lookup"><span data-stu-id="992a8-112">The following deployment options are possible:</span></span>  
  
|<span data-ttu-id="992a8-113">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="992a8-113">.NET type</span></span>|<span data-ttu-id="992a8-114">程序集路径</span><span class="sxs-lookup"><span data-stu-id="992a8-114">Assembly path</span></span>|<span data-ttu-id="992a8-115">程序集部署方法</span><span class="sxs-lookup"><span data-stu-id="992a8-115">Assembly deployment method</span></span>|  
|---------------|-------------------|--------------------------------|  
|<span data-ttu-id="992a8-116">Specified</span><span class="sxs-lookup"><span data-stu-id="992a8-116">Specified</span></span>|<span data-ttu-id="992a8-117">未指定</span><span class="sxs-lookup"><span data-stu-id="992a8-117">Not specified</span></span>|<span data-ttu-id="992a8-118">与程序集 XCopy 到产品目录或者具有相同名称的产品目录中子目录的程序集</span><span class="sxs-lookup"><span data-stu-id="992a8-118">XCopy assembly to product directory or subdirectory in product directory with the same name as the assembly</span></span>|  
|<span data-ttu-id="992a8-119">Specified</span><span class="sxs-lookup"><span data-stu-id="992a8-119">Specified</span></span>|<span data-ttu-id="992a8-120">未指定</span><span class="sxs-lookup"><span data-stu-id="992a8-120">Not specified</span></span>|<span data-ttu-id="992a8-121">全局程序集缓存 (GAC) 程序集</span><span class="sxs-lookup"><span data-stu-id="992a8-121">Global assembly cache (GAC) assembly</span></span>|  
|<span data-ttu-id="992a8-122">Specified</span><span class="sxs-lookup"><span data-stu-id="992a8-122">Specified</span></span>|<span data-ttu-id="992a8-123">Specified</span><span class="sxs-lookup"><span data-stu-id="992a8-123">Specified</span></span>|<span data-ttu-id="992a8-124">XCopy 到指定的目录的程序集</span><span class="sxs-lookup"><span data-stu-id="992a8-124">XCopy assembly to specified directory</span></span>|  
  
 <span data-ttu-id="992a8-125">**故障排除提示：** 创建使用托管的代码中，如果在无法创建适配器时，使用 fuslogvw.exe 工具确定是否存在无法解析的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="992a8-125">**Troubleshooting Tip:** When you create an adapter using managed code, if the creation fails, use the fuslogvw.exe tool to determine if there are references to assemblies that cannot be resolved.</span></span> <span data-ttu-id="992a8-126">这是一个常见的错误。</span><span class="sxs-lookup"><span data-stu-id="992a8-126">This is a common mistake.</span></span>  
  
 <span data-ttu-id="992a8-127">下图显示了用于创建适配器，具体取决于指定的配置的逻辑：</span><span class="sxs-lookup"><span data-stu-id="992a8-127">The following figure shows the logic for creating adapters, depending on the configuration specified:</span></span>  
  
 <span data-ttu-id="992a8-128">![](../core/media/initializingtheadapter.gif "InitializingTheAdapter")</span><span class="sxs-lookup"><span data-stu-id="992a8-128">![](../core/media/initializingtheadapter.gif "InitializingTheAdapter")</span></span>  
  
 <span data-ttu-id="992a8-129">下表提供了示例的接收适配器可能配置方式，并可能配置的运行时程序集的方法。</span><span class="sxs-lookup"><span data-stu-id="992a8-129">The following table gives an example of how a receive adapter may be configured, and the ways the run-time assembly may be configured.</span></span>  
  
|<span data-ttu-id="992a8-130">程序集部署方法</span><span class="sxs-lookup"><span data-stu-id="992a8-130">Assembly deployment method</span></span>|<span data-ttu-id="992a8-131">InboundTypeName</span><span class="sxs-lookup"><span data-stu-id="992a8-131">InboundTypeName</span></span>|<span data-ttu-id="992a8-132">InboundAssemblyPath</span><span class="sxs-lookup"><span data-stu-id="992a8-132">InboundAssemblyPath</span></span>|  
|--------------------------------|---------------------|-------------------------|  
|<span data-ttu-id="992a8-133">指定程序集位置</span><span class="sxs-lookup"><span data-stu-id="992a8-133">Specify assembly location</span></span>|<span data-ttu-id="992a8-134">Microsoft.Samples.MyReceiveAdapter</span><span class="sxs-lookup"><span data-stu-id="992a8-134">Microsoft.Samples.MyReceiveAdapter</span></span>|<span data-ttu-id="992a8-135">C:\MyAdapter\MyAdapter.dll</span><span class="sxs-lookup"><span data-stu-id="992a8-135">C:\MyAdapter\MyAdapter.dll</span></span>|  
|<span data-ttu-id="992a8-136">指定.NET 类型 （包括公钥、 版本和区域性信息）</span><span class="sxs-lookup"><span data-stu-id="992a8-136">Specify .NET type (include public key, version, and culture information)</span></span>|<span data-ttu-id="992a8-137">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span><span class="sxs-lookup"><span data-stu-id="992a8-137">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span></span>|<span data-ttu-id="992a8-138">不可用</span><span class="sxs-lookup"><span data-stu-id="992a8-138">N/A</span></span>|  
|<span data-ttu-id="992a8-139">GAC 程序集</span><span class="sxs-lookup"><span data-stu-id="992a8-139">GAC assembly</span></span>|<span data-ttu-id="992a8-140">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span><span class="sxs-lookup"><span data-stu-id="992a8-140">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span></span>|<span data-ttu-id="992a8-141">不可用</span><span class="sxs-lookup"><span data-stu-id="992a8-141">N/A</span></span>|