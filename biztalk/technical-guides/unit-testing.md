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
ms.openlocfilehash: d5f792adf73fb1e3791f0dfe6c8c5f60a3bb81e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="unit-testing"></a><span data-ttu-id="f8ceb-102">单元测试</span><span class="sxs-lookup"><span data-stu-id="f8ceb-102">Unit Testing</span></span>
<span data-ttu-id="f8ceb-103">BizTalk Server 引入了单元测试可在中启用的功能**部署**BizTalk 项目属性页。</span><span class="sxs-lookup"><span data-stu-id="f8ceb-103">BizTalk Server introduces a unit testing feature that can be enabled on the **Deployment** property page of a BizTalk project.</span></span> <span data-ttu-id="f8ceb-104">以下屏幕截图显示当你右键单击某个项目并单击时从项目设计器访问此项目设置**属性**。</span><span class="sxs-lookup"><span data-stu-id="f8ceb-104">The following screenshot shows this project setting accessed from Project Designer when you right-click a project and click **Properties**.</span></span>  
  
 <span data-ttu-id="f8ceb-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span><span class="sxs-lookup"><span data-stu-id="f8ceb-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span></span>  
  
 <span data-ttu-id="f8ceb-106">**项目设计器公开启用单元测试项目属性中的部署选项卡的屏幕截图**</span><span class="sxs-lookup"><span data-stu-id="f8ceb-106">**Screenshot of the Deployment tab in Project Designer exposing the Enable Unit Testing project property**</span></span>  
  
 <span data-ttu-id="f8ceb-107">此功能允许您为架构、映射和管道创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="f8ceb-107">This feature allows you to create unit tests for schemas, maps, and pipelines.</span></span> <span data-ttu-id="f8ceb-108">BizTalk Server 文档中的主题提供对使用单元测试功能的一些示例方法。</span><span class="sxs-lookup"><span data-stu-id="f8ceb-108">The topics in the BizTalk Server documentation provide some example approaches to using the unit testing feature.</span></span> <span data-ttu-id="f8ceb-109">启用此功能并且重建项目之后，将从以下基类中派生项目类以支持单元测试。</span><span class="sxs-lookup"><span data-stu-id="f8ceb-109">When this feature is enabled and the project rebuilt, the artifact classes will be derived from the following base classes to support unit testing.</span></span>  
  
|<span data-ttu-id="f8ceb-110">项目类型</span><span class="sxs-lookup"><span data-stu-id="f8ceb-110">Artifact type</span></span>|<span data-ttu-id="f8ceb-111">基类</span><span class="sxs-lookup"><span data-stu-id="f8ceb-111">Base class</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="f8ceb-112">架构</span><span class="sxs-lookup"><span data-stu-id="f8ceb-112">Schema</span></span>|<span data-ttu-id="f8ceb-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span><span class="sxs-lookup"><span data-stu-id="f8ceb-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span></span>|  
|<span data-ttu-id="f8ceb-114">映射</span><span class="sxs-lookup"><span data-stu-id="f8ceb-114">Map</span></span>|<span data-ttu-id="f8ceb-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span><span class="sxs-lookup"><span data-stu-id="f8ceb-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span></span>|  
|<span data-ttu-id="f8ceb-116">管道</span><span class="sxs-lookup"><span data-stu-id="f8ceb-116">Pipeline</span></span>|<span data-ttu-id="f8ceb-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span><span class="sxs-lookup"><span data-stu-id="f8ceb-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span></span>|  
  
 <span data-ttu-id="f8ceb-118">有关的单元测试与 BizTalk Server 引入的功能的详细信息，请参阅 BizTalk Server 帮助中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="f8ceb-118">For more information about the unit testing feature introduced with BizTalk Server, see the following topics in the BizTalk Server Help:</span></span>  
  
-   <span data-ttu-id="f8ceb-119">[使用单元测试功能包含架构和映射](http://go.microsoft.com/fwlink/?LinkId=150482)(http://go.microsoft.com/fwlink/?LinkId=150482)。</span><span class="sxs-lookup"><span data-stu-id="f8ceb-119">[Using the Unit Testing Feature with Schemas and Maps](http://go.microsoft.com/fwlink/?LinkId=150482) (http://go.microsoft.com/fwlink/?LinkId=150482).</span></span>  
  
-   <span data-ttu-id="f8ceb-120">[使用单元测试使用管道功能](http://go.microsoft.com/fwlink/?LinkId=150483)(http://go.microsoft.com/fwlink/?LinkId=150483)</span><span class="sxs-lookup"><span data-stu-id="f8ceb-120">[Using the Unit Testing Feature with Pipelines](http://go.microsoft.com/fwlink/?LinkId=150483) (http://go.microsoft.com/fwlink/?LinkId=150483)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ceb-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8ceb-121">See Also</span></span>  
 [<span data-ttu-id="f8ceb-122">实现自动测试</span><span class="sxs-lookup"><span data-stu-id="f8ceb-122">Implementing Automated Testing</span></span>](../technical-guides/implementing-automated-testing.md)