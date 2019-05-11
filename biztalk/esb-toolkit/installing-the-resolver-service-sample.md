---
title: 安装解析程序服务示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fce9bbeb-9377-41af-8ca7-740ce4d1f617
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88168abccba2fc8eb266816b6820bbcdc72d0c67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249731"
---
# <a name="installing-the-resolver-service-sample"></a><span data-ttu-id="dfb9e-102">安装解析程序服务示例</span><span class="sxs-lookup"><span data-stu-id="dfb9e-102">Installing the Resolver Service Sample</span></span>
<span data-ttu-id="dfb9e-103">本部分介绍安装解析程序服务示例的过程。</span><span class="sxs-lookup"><span data-stu-id="dfb9e-103">This section describes the process for installing the Resolver Service sample.</span></span> <span data-ttu-id="dfb9e-104">解析程序服务依赖于[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心解决方案。</span><span class="sxs-lookup"><span data-stu-id="dfb9e-104">The Resolver Service depends on the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core solution.</span></span> <span data-ttu-id="dfb9e-105">安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]core 自动复制和安装本示例为正确的位置所需的核心程序集。</span><span class="sxs-lookup"><span data-stu-id="dfb9e-105">Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automatically copies and installs the core assemblies required by this sample to the correct locations.</span></span>  
  
 <span data-ttu-id="dfb9e-106">**若要从解决方案项目中安装解析程序服务示例**</span><span class="sxs-lookup"><span data-stu-id="dfb9e-106">**To install the Resolver Service sample from the solution project**</span></span>  
  
1.  <span data-ttu-id="dfb9e-107">在 Windows 资源管理器中，打开 \Source\Samples\ResolverService\Install\Scripts 文件夹。</span><span class="sxs-lookup"><span data-stu-id="dfb9e-107">In Windows Explorer, open the \Source\Samples\ResolverService\Install\Scripts folder.</span></span>  
  
2.  <span data-ttu-id="dfb9e-108">双击 Setup_bin.cmd 文件。</span><span class="sxs-lookup"><span data-stu-id="dfb9e-108">Double-click the Setup_bin.cmd file.</span></span>  
  
3.  <span data-ttu-id="dfb9e-109">若要确认已成功安装该示例中，或者如果运行的应用程序时遇到问题，可以使用下表中提供的列表来检查是否存在所需的程序集和其他项目。</span><span class="sxs-lookup"><span data-stu-id="dfb9e-109">To confirm successful installation of the sample, or if you are encountering issues when you run applications, you can use the list provided in the following table to check for the presence of the required assemblies and other artifacts.</span></span>  
  
|<span data-ttu-id="dfb9e-110">Location</span><span class="sxs-lookup"><span data-stu-id="dfb9e-110">Location</span></span>|<span data-ttu-id="dfb9e-111">Category</span><span class="sxs-lookup"><span data-stu-id="dfb9e-111">Category</span></span>|<span data-ttu-id="dfb9e-112">名称和版本的组件</span><span class="sxs-lookup"><span data-stu-id="dfb9e-112">Name and version of the component</span></span>|  
|--------------|--------------|---------------------------------------|  
|<span data-ttu-id="dfb9e-113">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="dfb9e-113">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="dfb9e-114">业务流程</span><span class="sxs-lookup"><span data-stu-id="dfb9e-114">Orchestrations</span></span>|<span data-ttu-id="dfb9e-115">（无）</span><span class="sxs-lookup"><span data-stu-id="dfb9e-115">(none)</span></span>|  
|<span data-ttu-id="dfb9e-116">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="dfb9e-116">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="dfb9e-117">发送端口</span><span class="sxs-lookup"><span data-stu-id="dfb9e-117">Send Ports</span></span>|<span data-ttu-id="dfb9e-118">（无）</span><span class="sxs-lookup"><span data-stu-id="dfb9e-118">(none)</span></span>|  
|<span data-ttu-id="dfb9e-119">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="dfb9e-119">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="dfb9e-120">接收端口</span><span class="sxs-lookup"><span data-stu-id="dfb9e-120">Receive Ports</span></span>|<span data-ttu-id="dfb9e-121">（无）</span><span class="sxs-lookup"><span data-stu-id="dfb9e-121">(none)</span></span>|  
|<span data-ttu-id="dfb9e-122">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="dfb9e-122">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="dfb9e-123">接收位置</span><span class="sxs-lookup"><span data-stu-id="dfb9e-123">Receive Locations</span></span>|<span data-ttu-id="dfb9e-124">（无）</span><span class="sxs-lookup"><span data-stu-id="dfb9e-124">(none)</span></span>|  
|<span data-ttu-id="dfb9e-125">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="dfb9e-125">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="dfb9e-126">架构</span><span class="sxs-lookup"><span data-stu-id="dfb9e-126">Schemas</span></span>|<span data-ttu-id="dfb9e-127">（无）</span><span class="sxs-lookup"><span data-stu-id="dfb9e-127">(none)</span></span>|  
|<span data-ttu-id="dfb9e-128">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="dfb9e-128">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="dfb9e-129">管道</span><span class="sxs-lookup"><span data-stu-id="dfb9e-129">Pipelines</span></span>|<span data-ttu-id="dfb9e-130">（无）</span><span class="sxs-lookup"><span data-stu-id="dfb9e-130">(none)</span></span>|  
|<span data-ttu-id="dfb9e-131">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="dfb9e-131">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="dfb9e-132">资源</span><span class="sxs-lookup"><span data-stu-id="dfb9e-132">Resources</span></span>|<span data-ttu-id="dfb9e-133">（无）</span><span class="sxs-lookup"><span data-stu-id="dfb9e-133">(none)</span></span>|  
|<span data-ttu-id="dfb9e-134">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="dfb9e-134">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="dfb9e-135">策略</span><span class="sxs-lookup"><span data-stu-id="dfb9e-135">Policies</span></span>|<span data-ttu-id="dfb9e-136">ResolveEndpoint</span><span class="sxs-lookup"><span data-stu-id="dfb9e-136">ResolveEndpoint</span></span>|  
|||<span data-ttu-id="dfb9e-137">ResolveMap</span><span class="sxs-lookup"><span data-stu-id="dfb9e-137">ResolveMap</span></span>|  
|<span data-ttu-id="dfb9e-138">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="dfb9e-138">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="dfb9e-139">地图</span><span class="sxs-lookup"><span data-stu-id="dfb9e-139">Maps</span></span>|<span data-ttu-id="dfb9e-140">（无）</span><span class="sxs-lookup"><span data-stu-id="dfb9e-140">(none)</span></span>|  
|<span data-ttu-id="dfb9e-141">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="dfb9e-141">Global assembly cache</span></span>|<span data-ttu-id="dfb9e-142">程序集</span><span class="sxs-lookup"><span data-stu-id="dfb9e-142">Assemblies</span></span>|<span data-ttu-id="dfb9e-143">（无）</span><span class="sxs-lookup"><span data-stu-id="dfb9e-143">(none)</span></span>|  
|<span data-ttu-id="dfb9e-144">%Program Files %\\BizTalk Server\Pipeline 组件</span><span class="sxs-lookup"><span data-stu-id="dfb9e-144">%Program Files%\\BizTalk Server\Pipeline Components</span></span>|<span data-ttu-id="dfb9e-145">管道组件</span><span class="sxs-lookup"><span data-stu-id="dfb9e-145">Pipeline components</span></span>|<span data-ttu-id="dfb9e-146">（无）</span><span class="sxs-lookup"><span data-stu-id="dfb9e-146">(none)</span></span>|