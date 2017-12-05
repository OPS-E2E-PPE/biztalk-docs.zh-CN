---
title: "使用 BizTalk Server 项目进行单元测试 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2594f29-fc34-4dda-9316-2afd4e0056d7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da7147f4c2500946fb97c47592a2a4a35d3dcf62
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="unit-testing-with-biztalk-server-projects"></a>使用 BizTalk Server 项目进行单元测试
BizTalk Server 引入单元测试可在中启用的功能**部署**BizTalk 项目属性页。 以下屏幕截图显示当你右键单击某个项目并单击时从项目设计器访问此项目设置**属性**。  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 **项目设计器公开启用单元测试项目属性中的部署选项卡的屏幕截图。**  
  
 此功能允许您为架构、映射和管道创建单元测试。 本部分中的主题提供使用单元测试功能的一些示例方法。 启用此功能并且重建项目之后，将从以下基类中派生项目类以支持单元测试。  
  
|项目类型|基类|  
|-------------------|----------------|  
|架构|**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**|  
|映射|**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**|  
|管道|**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用单元测试与架构和映射的功能](../core/using-the-unit-testing-feature-with-schemas-and-maps.md)  
  
-   [使用单元测试使用管道功能](../core/using-the-unit-testing-feature-with-pipelines.md)  
  
## <a name="related-sections"></a>相关章节  
 [使用单元测试 (Visual Studio)](http://go.microsoft.com/fwlink/?LinkId=128890)