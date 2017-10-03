---
title: "BizTalk Server Integration2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 562a628d-52cb-4aae-8729-b5ba855bea5f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c550e9953332458fd79f4a3f6b7e29bece9fa127
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-integration"></a><span data-ttu-id="a79c2-102">BizTalk Server 的集成</span><span class="sxs-lookup"><span data-stu-id="a79c2-102">BizTalk Server Integration</span></span>
<span data-ttu-id="a79c2-103">AmberPoint 包作为自定义的 BizTalk 管道组件其 Microsoft BizTalk Server 集成产品。</span><span class="sxs-lookup"><span data-stu-id="a79c2-103">AmberPoint packages its Microsoft BizTalk Server integration product as a custom BizTalk pipeline component.</span></span> <span data-ttu-id="a79c2-104">你可以将此组件添加到你现有的自定义管线，使用[!INCLUDE[vs2010](../includes/vs2010-md.md)]，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="a79c2-104">You can add this component to your existing custom pipelines using [!INCLUDE[vs2010](../includes/vs2010-md.md)], as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="a79c2-105">![Visual Studio 管道](../esb-toolkit/media/ch9-visualstudiopipeline.jpg "Ch9 VisualStudioPipeline")</span><span class="sxs-lookup"><span data-stu-id="a79c2-105">![VisualStudio Pipeline](../esb-toolkit/media/ch9-visualstudiopipeline.jpg "Ch9-VisualStudioPipeline")</span></span>  
  
 <span data-ttu-id="a79c2-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="a79c2-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="a79c2-107">**安装到发送管道 AmberPoint 组件**</span><span class="sxs-lookup"><span data-stu-id="a79c2-107">**Installing the AmberPoint component into a send pipeline**</span></span>  
  
 <span data-ttu-id="a79c2-108">此外，AmberPoint 附带四个预定义的管道，你可以直接绑定到现有接收位置和发送端口使用 BizTalk 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a79c2-108">In addition, AmberPoint ships four predefined pipelines that you can bind directly to existing receive locations and send ports using the BizTalk Administration Console.</span></span> <span data-ttu-id="a79c2-109">图 2 显示给适配器接收管道的绑定。</span><span class="sxs-lookup"><span data-stu-id="a79c2-109">Figure 2 shows the binding of a receive pipeline to an adapter.</span></span>  
  
 <span data-ttu-id="a79c2-110">![绑定 AmberPoint](../esb-toolkit/media/ch9-bindingamberpoint.jpg "Ch9 BindingAmberPoint")</span><span class="sxs-lookup"><span data-stu-id="a79c2-110">![Binding AmberPoint](../esb-toolkit/media/ch9-bindingamberpoint.jpg "Ch9-BindingAmberPoint")</span></span>  
  
 <span data-ttu-id="a79c2-111">**图 2**</span><span class="sxs-lookup"><span data-stu-id="a79c2-111">**Figure 2**</span></span>  
  
 <span data-ttu-id="a79c2-112">**绑定 AmberPoint 接收管道到适配器**</span><span class="sxs-lookup"><span data-stu-id="a79c2-112">**Binding an AmberPoint receive pipeline to an adapter**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a79c2-113">AmberPoint SOA 管理系统 (SMS) 产品是一种产品与集成的 AmberPoint，Inc.的[!INCLUDE[prague](../includes/prague-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a79c2-113">The AmberPoint SOA Management System (SMS) product is a product from AmberPoint, Inc. that integrates with [!INCLUDE[prague](../includes/prague-md.md)].</span></span> <span data-ttu-id="a79c2-114">关于 AmberPoint 和其 SOA 监管产品的详细信息，请参阅[AmberPoint](http://go.microsoft.com/fwlink/?LinkId=188561) Web 站点。</span><span class="sxs-lookup"><span data-stu-id="a79c2-114">For more information about AmberPoint and their SOA governance products, see the [AmberPoint](http://go.microsoft.com/fwlink/?LinkId=188561) Web site.</span></span>