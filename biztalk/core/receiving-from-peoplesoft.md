---
title: 从 PeopleSoft 接收 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9acc71ec-05b8-4490-b3ba-0ce7f27a5a6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3861d885188762b69a08359fbaf9161e02aa5759
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398083"
---
# <a name="receiving-from-peoplesoft"></a><span data-ttu-id="31cea-102">从 PeopleSoft 接收</span><span class="sxs-lookup"><span data-stu-id="31cea-102">Receiving from PeopleSoft</span></span>
<span data-ttu-id="31cea-103">用于 PeopleSoft Enterprise 的 Microsoft 适配器是一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="31cea-103">The Microsoft Adapter for PeopleSoft Enterprise is a send adapter.</span></span> <span data-ttu-id="31cea-104">适配器支持要求-响应，以便可以发送查询并获得响应。</span><span class="sxs-lookup"><span data-stu-id="31cea-104">The adapter supports solicit-response, so that you can send a query and get back a response.</span></span> <span data-ttu-id="31cea-105">但是，如果只想从 PeopleSoft 接收数据，必须执行额外两个步骤：</span><span class="sxs-lookup"><span data-stu-id="31cea-105">However, if you want only to receive data from PeopleSoft, you must take two additional steps:</span></span>  
  
1.  <span data-ttu-id="31cea-106">创建使用设置 Namespace 管道组件的自定义接收管道。</span><span class="sxs-lookup"><span data-stu-id="31cea-106">Create a custom receive pipeline using the Set Namespace pipeline component.</span></span>  
  
2.  <span data-ttu-id="31cea-107">创建可接收端口从访问 PeopleSoft 如使用 HTTP 适配器的端口。</span><span class="sxs-lookup"><span data-stu-id="31cea-107">Create a receive port accessible from PeopleSoft such as a port using the HTTP Adapter.</span></span> <span data-ttu-id="31cea-108">使用自定义接收管道与接收端口。</span><span class="sxs-lookup"><span data-stu-id="31cea-108">Use the custom receive pipeline with the receive port.</span></span>  
  
## <a name="set-namespace-pipeline-component"></a><span data-ttu-id="31cea-109">设置 Namespace 管道组件</span><span class="sxs-lookup"><span data-stu-id="31cea-109">Set Namespace Pipeline Component</span></span>  
 <span data-ttu-id="31cea-110">从 PeopleSoft 接收的消息不包括命名空间。</span><span class="sxs-lookup"><span data-stu-id="31cea-110">Messages received from PeopleSoft do not include namespaces.</span></span> <span data-ttu-id="31cea-111">设置 Namespace 管道组件，可将一个命名空间添加到传入的消息。</span><span class="sxs-lookup"><span data-stu-id="31cea-111">The Set Namespace pipeline component enables you to add a namespace to the incoming message.</span></span>  
  
 <span data-ttu-id="31cea-112">设置 Namespace 管道组件的默认位置是 C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\Pipeline 组件。</span><span class="sxs-lookup"><span data-stu-id="31cea-112">The default location for the Set Namespace pipeline component is C:\Program Files\Microsoft BizTalk Adapters for Enterprise Applications\Pipeline Component.</span></span> <span data-ttu-id="31cea-113">您需要将该组件，Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll，复制到 biztalk 使用的管道组件的目录。</span><span class="sxs-lookup"><span data-stu-id="31cea-113">You need to copy the component, Microsoft.BizTalk.Adapters.Pipeline.SetNSForMsg.dll, to the Pipeline Component directory used by BizTalk.</span></span> <span data-ttu-id="31cea-114">您还需要将组件添加到 Visual Studio 工具箱中，以在管道设计器中使用它。</span><span class="sxs-lookup"><span data-stu-id="31cea-114">You also need to add the component to the Visual Studio Toolbox in order to use it in the Pipeline Designer.</span></span>  
  
 <span data-ttu-id="31cea-115">有关在何处安装该组件的信息，请参阅[部署管道组件](../core/deploying-pipeline-components.md)。</span><span class="sxs-lookup"><span data-stu-id="31cea-115">For information about where to install the component, see [Deploying Pipeline Components](../core/deploying-pipeline-components.md).</span></span>  
  
 <span data-ttu-id="31cea-116">有关将组件添加到 Visual Studio 工具箱的信息，请参阅[如何使用工具箱](../core/how-to-use-the-toolbox.md)。</span><span class="sxs-lookup"><span data-stu-id="31cea-116">For information about adding the component to the Visual Studio Toolbox, see [How to Use the Toolbox](../core/how-to-use-the-toolbox.md).</span></span>  
  
## <a name="configure-the-set-namespace-pipeline-component"></a><span data-ttu-id="31cea-117">配置集 Namespace 管道组件</span><span class="sxs-lookup"><span data-stu-id="31cea-117">Configure the Set Namespace Pipeline Component</span></span>  
 <span data-ttu-id="31cea-118">设置 Namespace 管道组件具有两个属性可以设置：</span><span class="sxs-lookup"><span data-stu-id="31cea-118">The Set Namespace pipeline component has two properties you can set:</span></span>  
  
|<span data-ttu-id="31cea-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="31cea-119">Use this</span></span>|<span data-ttu-id="31cea-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="31cea-120">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="31cea-121">**默认目标 Namespace**</span><span class="sxs-lookup"><span data-stu-id="31cea-121">**Default Target Namespace**</span></span>|<span data-ttu-id="31cea-122">将传入消息中的固定的命名空间。</span><span class="sxs-lookup"><span data-stu-id="31cea-122">Put a fixed namespace in the incoming message.</span></span>|  
|<span data-ttu-id="31cea-123">**目标 Namespace XPath**</span><span class="sxs-lookup"><span data-stu-id="31cea-123">**Target Namespace XPath**</span></span>|<span data-ttu-id="31cea-124">从指定的 xpath 的位置将其传入消息中提取命名空间。</span><span class="sxs-lookup"><span data-stu-id="31cea-124">Extract the namespace from the incoming message taking it from the location specified by the XPath.</span></span> <span data-ttu-id="31cea-125">如果该组件未找到有效的命名空间，它在应用程序事件日志中记录一个警告，并且如果指定，将使用默认目标 Namespace。</span><span class="sxs-lookup"><span data-stu-id="31cea-125">If the component does not find a valid namespace, it logs a warning in the Application Event Log and, if it is specified, uses the Default Target Namespace.</span></span>|  
  
 <span data-ttu-id="31cea-126">如果将这两个属性留空，该组件不会对传入消息分配命名空间，而 does 写入警告应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="31cea-126">If you leave both properties blank, the component does not assign namespaces to incoming messages but does write warnings to the Application Event Log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31cea-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="31cea-127">See Also</span></span>  
 [<span data-ttu-id="31cea-128">开发应用程序</span><span class="sxs-lookup"><span data-stu-id="31cea-128">Developing Applications</span></span>](../core/developing-applications4.md)