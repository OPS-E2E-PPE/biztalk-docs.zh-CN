---
title: 使用 BizTalk Server 项目进行单元测试 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2594f29-fc34-4dda-9316-2afd4e0056d7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da7147f4c2500946fb97c47592a2a4a35d3dcf62
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008118"
---
# <a name="unit-testing-with-biztalk-server-projects"></a><span data-ttu-id="eea4f-102">使用 BizTalk Server 项目进行单元测试</span><span class="sxs-lookup"><span data-stu-id="eea4f-102">Unit Testing with BizTalk Server Projects</span></span>
<span data-ttu-id="eea4f-103">BizTalk Server 引入单元测试可在中启用的功能**部署**BizTalk 项目属性页。</span><span class="sxs-lookup"><span data-stu-id="eea4f-103">BizTalk Server introduced a unit testing feature that can be enabled on the **Deployment** property page of a BizTalk project.</span></span> <span data-ttu-id="eea4f-104">以下屏幕截图显示当你右键单击某个项目并单击时从项目设计器访问此项目设置**属性**。</span><span class="sxs-lookup"><span data-stu-id="eea4f-104">The following screenshot shows this project setting accessed from Project Designer when you right-click a project and click the **Properties**.</span></span>  
  
 <span data-ttu-id="eea4f-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span><span class="sxs-lookup"><span data-stu-id="eea4f-105">![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")</span></span>  
  
 <span data-ttu-id="eea4f-106">**项目设计器公开启用单元测试项目属性中的部署选项卡的屏幕截图。**</span><span class="sxs-lookup"><span data-stu-id="eea4f-106">**Screenshot of the Deployment tab in Project Designer exposing the Enable Unit Testing project property.**</span></span>  
  
 <span data-ttu-id="eea4f-107">此功能允许您为架构、映射和管道创建单元测试。</span><span class="sxs-lookup"><span data-stu-id="eea4f-107">This feature allows you to create unit tests for schemas, maps, and pipelines.</span></span> <span data-ttu-id="eea4f-108">本部分中的主题提供使用单元测试功能的一些示例方法。</span><span class="sxs-lookup"><span data-stu-id="eea4f-108">The topics in this section provide some example approaches to using the unit testing feature.</span></span> <span data-ttu-id="eea4f-109">启用此功能并且重建项目之后，将从以下基类中派生项目类以支持单元测试。</span><span class="sxs-lookup"><span data-stu-id="eea4f-109">When this feature is enabled and the project rebuilt, the artifact classes will be derived from the following base classes to support unit testing.</span></span>  
  
|<span data-ttu-id="eea4f-110">项目类型</span><span class="sxs-lookup"><span data-stu-id="eea4f-110">Artifact type</span></span>|<span data-ttu-id="eea4f-111">基类</span><span class="sxs-lookup"><span data-stu-id="eea4f-111">Base class</span></span>|  
|-------------------|----------------|  
|<span data-ttu-id="eea4f-112">架构</span><span class="sxs-lookup"><span data-stu-id="eea4f-112">Schema</span></span>|<span data-ttu-id="eea4f-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span><span class="sxs-lookup"><span data-stu-id="eea4f-113">**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**</span></span>|  
|<span data-ttu-id="eea4f-114">映射</span><span class="sxs-lookup"><span data-stu-id="eea4f-114">Map</span></span>|<span data-ttu-id="eea4f-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span><span class="sxs-lookup"><span data-stu-id="eea4f-115">**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**</span></span>|  
|<span data-ttu-id="eea4f-116">管道</span><span class="sxs-lookup"><span data-stu-id="eea4f-116">Pipeline</span></span>|<span data-ttu-id="eea4f-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span><span class="sxs-lookup"><span data-stu-id="eea4f-117">**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="eea4f-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="eea4f-118">In This Section</span></span>  
  
-   [<span data-ttu-id="eea4f-119">使用单元测试与架构和映射的功能</span><span class="sxs-lookup"><span data-stu-id="eea4f-119">Using the Unit Testing Feature with Schemas and Maps</span></span>](../core/using-the-unit-testing-feature-with-schemas-and-maps.md)  
  
-   [<span data-ttu-id="eea4f-120">使用单元测试使用管道功能</span><span class="sxs-lookup"><span data-stu-id="eea4f-120">Using the Unit Testing Feature with Pipelines</span></span>](../core/using-the-unit-testing-feature-with-pipelines.md)  
  
## <a name="related-sections"></a><span data-ttu-id="eea4f-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="eea4f-121">Related Sections</span></span>  
 [<span data-ttu-id="eea4f-122">使用单元测试 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="eea4f-122">Working with Unit Tests (Visual Studio)</span></span>](http://go.microsoft.com/fwlink/?LinkId=128890)