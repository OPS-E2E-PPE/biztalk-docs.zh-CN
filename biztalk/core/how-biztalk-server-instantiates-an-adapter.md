---
title: "BizTalk Server 如何实例化适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ebe7585-5939-4142-9281-990b4849e28d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32e6e40bf39c09e747391bba51a54143fc67e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-biztalk-server-instantiates-an-adapter"></a><span data-ttu-id="8d458-102">BizTalk Server 如何实例化适配器</span><span class="sxs-lookup"><span data-stu-id="8d458-102">How BizTalk Server Instantiates an Adapter</span></span>
<span data-ttu-id="8d458-103">在 BizTalk 服务启动时，所有接收适配器都将被实例化，只要它们具有一个或多个已配置且处于活动状态的接收位置。</span><span class="sxs-lookup"><span data-stu-id="8d458-103">When the BizTalk service starts, all receive adapters are instantiated, as long as they have one or more configured and active receive locations.</span></span> <span data-ttu-id="8d458-104">默认情况下，在消息引擎从队列中删除要通过使用某一发送适配器发送的第一个消息前，将不会实例化该发送适配器。</span><span class="sxs-lookup"><span data-stu-id="8d458-104">By default a send adapter is not instantiated until the Messaging Engine removes from the queue the first message to be sent by using that send adapter.</span></span> <span data-ttu-id="8d458-105">（这有时称为"延迟创建。）但是，如果你需要实例化服务启动后上的发送适配器，你可以使用**InitTransmitterOnServiceStart**适配器功能。</span><span class="sxs-lookup"><span data-stu-id="8d458-105">(This is sometimes called "lazy creation.") However, if you need to instantiate a send adapter on service startup, you can use the **InitTransmitterOnServiceStart** adapter capability.</span></span> <span data-ttu-id="8d458-106">这将引导消息引擎在服务启动时创建发送适配器，而非使用默认的“懒创建”方法。</span><span class="sxs-lookup"><span data-stu-id="8d458-106">This directs the Messaging Engine to create the send adapter on service startup rather than using the default lazy creation.</span></span> <span data-ttu-id="8d458-107">默认的“懒创建”方法有助于减少在终结点上未配置适配器时占用的系统资源量。</span><span class="sxs-lookup"><span data-stu-id="8d458-107">The default lazy creation approach helps to reduce the amount of system resources used when adapters are not configured on endpoints.</span></span>  
  
 <span data-ttu-id="8d458-108">在创建自定义适配器时，建议使用托管代码。</span><span class="sxs-lookup"><span data-stu-id="8d458-108">When you create a custom adapter, we recommend that you use managed code.</span></span> <span data-ttu-id="8d458-109">但是，可以使用本地 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="8d458-109">However, it is possible to use native COM components.</span></span> <span data-ttu-id="8d458-110">对于 COM 组件，该适配器在正常的方式使用中实例化**CoCreateInstance**。</span><span class="sxs-lookup"><span data-stu-id="8d458-110">For COM components the adapter is instantiated in the normal manner using **CoCreateInstance**.</span></span>  
  
 <span data-ttu-id="8d458-111">对于托管代码中，你需要指定.NET**类型**在配置文件中; 中的程序集路径是可选的。</span><span class="sxs-lookup"><span data-stu-id="8d458-111">For managed code, you need to specify the .NET **type** in the configuration file; the assembly path is optional.</span></span>  
  
 <span data-ttu-id="8d458-112">下面介绍可行的部署选项：</span><span class="sxs-lookup"><span data-stu-id="8d458-112">The following deployment options are possible:</span></span>  
  
|<span data-ttu-id="8d458-113">.NET 类型</span><span class="sxs-lookup"><span data-stu-id="8d458-113">.NET type</span></span>|<span data-ttu-id="8d458-114">程序集路径</span><span class="sxs-lookup"><span data-stu-id="8d458-114">Assembly path</span></span>|<span data-ttu-id="8d458-115">程序集部署方法</span><span class="sxs-lookup"><span data-stu-id="8d458-115">Assembly deployment method</span></span>|  
|---------------|-------------------|--------------------------------|  
|<span data-ttu-id="8d458-116">Specified</span><span class="sxs-lookup"><span data-stu-id="8d458-116">Specified</span></span>|<span data-ttu-id="8d458-117">未指定</span><span class="sxs-lookup"><span data-stu-id="8d458-117">Not specified</span></span>|<span data-ttu-id="8d458-118">通过 XCopy 复制方式将程序集复制到产品目录或者产品目录中的子目录，其名称与该程序集同名</span><span class="sxs-lookup"><span data-stu-id="8d458-118">XCopy assembly to product directory or subdirectory in product directory with the same name as the assembly</span></span>|  
|<span data-ttu-id="8d458-119">Specified</span><span class="sxs-lookup"><span data-stu-id="8d458-119">Specified</span></span>|<span data-ttu-id="8d458-120">未指定</span><span class="sxs-lookup"><span data-stu-id="8d458-120">Not specified</span></span>|<span data-ttu-id="8d458-121">全局程序集缓存 (GAC) 程序集</span><span class="sxs-lookup"><span data-stu-id="8d458-121">Global assembly cache (GAC) assembly</span></span>|  
|<span data-ttu-id="8d458-122">Specified</span><span class="sxs-lookup"><span data-stu-id="8d458-122">Specified</span></span>|<span data-ttu-id="8d458-123">Specified</span><span class="sxs-lookup"><span data-stu-id="8d458-123">Specified</span></span>|<span data-ttu-id="8d458-124">将程序集以 XCopy 方式复制到指定目录</span><span class="sxs-lookup"><span data-stu-id="8d458-124">XCopy assembly to specified directory</span></span>|  
  
 <span data-ttu-id="8d458-125">**故障排除提示：**当你创建使用托管的代码中，如果无法创建适配器时，使用 fuslogvw.exe 工具来确定是否存在无法解析的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="8d458-125">**Troubleshooting Tip:** When you create an adapter using managed code, if the creation fails, use the fuslogvw.exe tool to determine if there are references to assemblies that cannot be resolved.</span></span> <span data-ttu-id="8d458-126">这是一个常见错误。</span><span class="sxs-lookup"><span data-stu-id="8d458-126">This is a common mistake.</span></span>  
  
 <span data-ttu-id="8d458-127">下图显示根据指定的配置创建适配器的逻辑：</span><span class="sxs-lookup"><span data-stu-id="8d458-127">The following figure shows the logic for creating adapters, depending on the configuration specified:</span></span>  
  
 ![](../core/media/initializingtheadapter.gif "InitializingTheAdapter")  
  
 <span data-ttu-id="8d458-128">下表提供了一个示例，介绍如何配置接收适配器以及配置运行时程序集的方式。</span><span class="sxs-lookup"><span data-stu-id="8d458-128">The following table gives an example of how a receive adapter may be configured, and the ways the run-time assembly may be configured.</span></span>  
  
|<span data-ttu-id="8d458-129">程序集部署方法</span><span class="sxs-lookup"><span data-stu-id="8d458-129">Assembly deployment method</span></span>|<span data-ttu-id="8d458-130">InboundTypeName</span><span class="sxs-lookup"><span data-stu-id="8d458-130">InboundTypeName</span></span>|<span data-ttu-id="8d458-131">InboundAssemblyPath</span><span class="sxs-lookup"><span data-stu-id="8d458-131">InboundAssemblyPath</span></span>|  
|--------------------------------|---------------------|-------------------------|  
|<span data-ttu-id="8d458-132">指定程序集位置</span><span class="sxs-lookup"><span data-stu-id="8d458-132">Specify assembly location</span></span>|<span data-ttu-id="8d458-133">Microsoft.Samples.MyReceiveAdapter</span><span class="sxs-lookup"><span data-stu-id="8d458-133">Microsoft.Samples.MyReceiveAdapter</span></span>|<span data-ttu-id="8d458-134">C:\MyAdapter\MyAdapter.dll</span><span class="sxs-lookup"><span data-stu-id="8d458-134">C:\MyAdapter\MyAdapter.dll</span></span>|  
|<span data-ttu-id="8d458-135">指定 .NET 类型（包括公钥、版本和区域性信息）</span><span class="sxs-lookup"><span data-stu-id="8d458-135">Specify .NET type (include public key, version, and culture information)</span></span>|<span data-ttu-id="8d458-136">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span><span class="sxs-lookup"><span data-stu-id="8d458-136">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span></span>|<span data-ttu-id="8d458-137">N/A</span><span class="sxs-lookup"><span data-stu-id="8d458-137">N/A</span></span>|  
|<span data-ttu-id="8d458-138">GAC 程序集</span><span class="sxs-lookup"><span data-stu-id="8d458-138">GAC assembly</span></span>|<span data-ttu-id="8d458-139">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span><span class="sxs-lookup"><span data-stu-id="8d458-139">Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020</span></span>|<span data-ttu-id="8d458-140">N/A</span><span class="sxs-lookup"><span data-stu-id="8d458-140">N/A</span></span>|