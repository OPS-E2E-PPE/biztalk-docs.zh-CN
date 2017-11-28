---
title: "接收来自 PeopleSoft |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9acc71ec-05b8-4490-b3ba-0ce7f27a5a6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11c5add7e71e56f250b95736d97f0434adf72282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receiving-from-peoplesoft"></a><span data-ttu-id="a62e4-102">接收来自 PeopleSoft</span><span class="sxs-lookup"><span data-stu-id="a62e4-102">Receiving from PeopleSoft</span></span>
<span data-ttu-id="a62e4-103">PeopleSoft 企业 Microsoft 适配器是发送适配器。</span><span class="sxs-lookup"><span data-stu-id="a62e4-103">The Microsoft Adapter for PeopleSoft Enterprise is a send adapter.</span></span> <span data-ttu-id="a62e4-104">该适配器支持要求响应，从而您可以发送查询并获得响应。</span><span class="sxs-lookup"><span data-stu-id="a62e4-104">The adapter supports solicit-response, so that you can send a query and get back a response.</span></span> <span data-ttu-id="a62e4-105">但是，如果你只希望从 PeopleSoft 接收数据，你必须执行两个附加步骤：</span><span class="sxs-lookup"><span data-stu-id="a62e4-105">However, if you want only to receive data from PeopleSoft, you must take two additional steps:</span></span>  
  
1.  <span data-ttu-id="a62e4-106">创建使用设置 Namespace 管道组件的自定义接收管道。</span><span class="sxs-lookup"><span data-stu-id="a62e4-106">Create a custom receive pipeline using the Set Namespace pipeline component.</span></span>  
  
2.  <span data-ttu-id="a62e4-107">接收端口访问从创建 PeopleSoft 例如端口使用 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="a62e4-107">Create a receive port accessible from PeopleSoft such as a port using the HTTP Adapter.</span></span> <span data-ttu-id="a62e4-108">使用与接收端口的自定义接收管道。</span><span class="sxs-lookup"><span data-stu-id="a62e4-108">Use the custom receive pipeline with the receive port.</span></span>  
  
## <a name="the-set-namespace-pipeline-component"></a><span data-ttu-id="a62e4-109">设置 Namespace 管道组件</span><span class="sxs-lookup"><span data-stu-id="a62e4-109">The Set Namespace Pipeline Component</span></span>  
 <span data-ttu-id="a62e4-110">从 PeopleSoft 接收的消息不包括命名空间。</span><span class="sxs-lookup"><span data-stu-id="a62e4-110">Messages received from PeopleSoft do not include namespaces.</span></span> <span data-ttu-id="a62e4-111">设置 Namespace 管道组件，可将命名空间添加到传入的消息。</span><span class="sxs-lookup"><span data-stu-id="a62e4-111">The Set Namespace pipeline component enables you to add a namespace to the incoming message.</span></span>  
  
 <span data-ttu-id="a62e4-112">设置 Namespace 管道组件的默认位置是 C:\Program Files\Microsoft BizTalk 适配器企业 Applications\Pipeline 组件。</span><span class="sxs-lookup"><span data-stu-id="a62e4-112">The default location for the Set Namespace pipeline component is C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\Pipeline Component.</span></span> <span data-ttu-id="a62e4-113">你需要将该组件，Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll，复制到由 BizTalk 使用的管道组件的目录。</span><span class="sxs-lookup"><span data-stu-id="a62e4-113">You need to copy the component, Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll, to the Pipeline Component directory used by BizTalk.</span></span> <span data-ttu-id="a62e4-114">你还需要将该组件添加到 Visual Studio 工具箱中，以在管道设计器中使用它。</span><span class="sxs-lookup"><span data-stu-id="a62e4-114">You also need to add the component to the Visual Studio Toolbox in order to use it in the Pipeline Designer.</span></span>  
  
 <span data-ttu-id="a62e4-115">有关在何处安装组件的信息，请参阅[部署管道组件](../core/deploying-pipeline-components.md)。</span><span class="sxs-lookup"><span data-stu-id="a62e4-115">For information about where to install the component, see [Deploying Pipeline Components](../core/deploying-pipeline-components.md).</span></span>  
  
 <span data-ttu-id="a62e4-116">有关将组件添加到 Visual Studio 工具箱的信息，请参阅[如何使用工具箱](../core/how-to-use-the-toolbox.md)。</span><span class="sxs-lookup"><span data-stu-id="a62e4-116">For information about adding the component to the Visual Studio Toolbox, see [How to Use the Toolbox](../core/how-to-use-the-toolbox.md).</span></span>  
  
## <a name="configuring-the-set-namespace-pipeline-component"></a><span data-ttu-id="a62e4-117">配置集 Namespace 管道组件</span><span class="sxs-lookup"><span data-stu-id="a62e4-117">Configuring the Set Namespace Pipeline Component</span></span>  
 <span data-ttu-id="a62e4-118">设置 Namespace 管道组件具有两个属性可以设置：</span><span class="sxs-lookup"><span data-stu-id="a62e4-118">The Set Namespace pipeline component has two properties you can set:</span></span>  
  
|<span data-ttu-id="a62e4-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a62e4-119">Use this</span></span>|<span data-ttu-id="a62e4-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a62e4-120">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="a62e4-121">**默认目标 Namespace**</span><span class="sxs-lookup"><span data-stu-id="a62e4-121">**Default Target Namespace**</span></span>|<span data-ttu-id="a62e4-122">传入消息中将固定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="a62e4-122">Put a fixed namespace in the incoming message.</span></span>|  
|<span data-ttu-id="a62e4-123">**目标 Namespace XPath**</span><span class="sxs-lookup"><span data-stu-id="a62e4-123">**Target Namespace XPath**</span></span>|<span data-ttu-id="a62e4-124">从传入的消息将其从指定的 XPath 位置提取命名空间。</span><span class="sxs-lookup"><span data-stu-id="a62e4-124">Extract the namespace from the incoming message taking it from the location specified by the XPath.</span></span> <span data-ttu-id="a62e4-125">如果组件未找到有效的命名空间，它记录应用程序事件日志中的警告，并且如果指定，将使用默认目标 Namespace。</span><span class="sxs-lookup"><span data-stu-id="a62e4-125">If the component does not find a valid namespace, it logs a warning in the Application Event Log and, if it is specified, uses the Default Target Namespace.</span></span>|  
  
 <span data-ttu-id="a62e4-126">如果将这两个属性保留为空，则该组件不会对传入消息分配命名空间，而未写入警告到应用程序事件日志中。</span><span class="sxs-lookup"><span data-stu-id="a62e4-126">If you leave both properties blank, the component does not assign namespaces to incoming messages but does write warnings to the Application Event Log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62e4-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a62e4-127">See Also</span></span>  
 [<span data-ttu-id="a62e4-128">开发应用程序</span><span class="sxs-lookup"><span data-stu-id="a62e4-128">Developing Applications</span></span>](../core/developing-applications4.md)