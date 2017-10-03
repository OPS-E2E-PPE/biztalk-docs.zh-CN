---
title: "单元测试 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c40e5b82-dbb2-4767-8286-88e2de4129f3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa6dd215aee23f49442e614649fa33f7321d42e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unit-testing"></a><span data-ttu-id="5f51c-102">单元测试</span><span class="sxs-lookup"><span data-stu-id="5f51c-102">Unit Testing</span></span>
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="5f51c-103">引入了单元测试可在中启用的功能**部署**BizTalk 项目属性页。</span><span class="sxs-lookup"><span data-stu-id="5f51c-103"> introduces a unit testing feature that can be enabled on the **Deployment** property page of a BizTalk project.</span></span> <span data-ttu-id="5f51c-104">以下屏幕截图显示当你右键单击某个项目并单击时从项目设计器访问此项目设置**属性**。</span><span class="sxs-lookup"><span data-stu-id="5f51c-104">The following screenshot shows this project setting accessed from Project Designer when you right-click a project and click **Properties**.</span></span>  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 <span data-ttu-id="5f51c-105">**项目设计器公开启用单元测试项目属性中的部署选项卡的屏幕截图**</span><span class="sxs-lookup"><span data-stu-id="5f51c-105">**Screenshot of the Deployment tab in Project Designer exposing the Enable Unit Testing project property**</span></span>  
  
 <span data-ttu-id="5f51c-106">此功能允许您为架构、映射和管道创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="5f51c-106">This feature allows you to create unit tests for schemas, maps, and pipelines.</span></span> <span data-ttu-id="5f51c-107">中的主题[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]文档提供一些示例方法使用的单元测试功能。</span><span class="sxs-lookup"><span data-stu-id="5f51c-107">The topics in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] documentation provide some example approaches to using the unit testing feature.</span></span> <span data-ttu-id="5f51c-108">启用此功能并且重建项目之后，将从以下基类中派生项目类以支持单元测试。</span><span class="sxs-lookup"><span data-stu-id="5f51c-108">When this feature is enabled and the project rebuilt, the artifact classes will be derived from the following base classes to support unit testing.</span></span>  
  
|<span data-ttu-id="5f51c-109">项目类型</span><span class="sxs-lookup"><span data-stu-id="5f51c-109">Artifact type</span></span>|<span data-ttu-id="5f51c-110">基类</span><span class="sxs-lookup"><span data-stu-id="5f51c-110">Base class</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="5f51c-111">架构</span><span class="sxs-lookup"><span data-stu-id="5f51c-111">Schema</span></span>|<span data-ttu-id="5f51c-112">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span><span class="sxs-lookup"><span data-stu-id="5f51c-112">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span></span>|  
|<span data-ttu-id="5f51c-113">映射</span><span class="sxs-lookup"><span data-stu-id="5f51c-113">Map</span></span>|<span data-ttu-id="5f51c-114">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span><span class="sxs-lookup"><span data-stu-id="5f51c-114">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span></span>|  
|<span data-ttu-id="5f51c-115">管道</span><span class="sxs-lookup"><span data-stu-id="5f51c-115">Pipeline</span></span>|<span data-ttu-id="5f51c-116">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span><span class="sxs-lookup"><span data-stu-id="5f51c-116">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span></span>|  
  
 <span data-ttu-id="5f51c-117">有关单元测试功能引入了[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，请参阅中的以下主题[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="5f51c-117">For more information about the unit testing feature introduced with [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], see the following topics in the [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help:</span></span>  
  
-   <span data-ttu-id="5f51c-118">[使用单元测试功能包含架构和映射](http://go.microsoft.com/fwlink/?LinkId=150482)(http://go.microsoft.com/fwlink/?LinkId=150482)。</span><span class="sxs-lookup"><span data-stu-id="5f51c-118">[Using the Unit Testing Feature with Schemas and Maps](http://go.microsoft.com/fwlink/?LinkId=150482) (http://go.microsoft.com/fwlink/?LinkId=150482).</span></span>  
  
-   <span data-ttu-id="5f51c-119">[使用单元测试使用管道功能](http://go.microsoft.com/fwlink/?LinkId=150483)(http://go.microsoft.com/fwlink/?LinkId=150483)</span><span class="sxs-lookup"><span data-stu-id="5f51c-119">[Using the Unit Testing Feature with Pipelines](http://go.microsoft.com/fwlink/?LinkId=150483) (http://go.microsoft.com/fwlink/?LinkId=150483)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f51c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f51c-120">See Also</span></span>  
 [<span data-ttu-id="5f51c-121">实现自动测试</span><span class="sxs-lookup"><span data-stu-id="5f51c-121">Implementing Automated Testing</span></span>](../technical-guides/implementing-automated-testing.md)