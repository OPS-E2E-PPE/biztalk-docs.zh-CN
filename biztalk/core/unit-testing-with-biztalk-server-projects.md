---
title: 使用 BizTalk Server 项目进行单元测试 |Microsoft Docs
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
ms.openlocfilehash: 19cb904341baf5d6a48af2ea55006522793b3d59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292637"
---
# <a name="unit-testing-with-biztalk-server-projects"></a>使用 BizTalk Server 项目进行单元测试
BizTalk Server 引入了单元测试功能，可以在启用了**部署**BizTalk 项目属性页。 以下屏幕截图显示右键单击项目，然后单击从项目设计器访问此项目设置**属性**。  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 **项目设计器将公开启用单元测试项目属性中的部署选项卡的屏幕截图。**  
  
 此功能允许你创建单元测试的架构、 映射和管道。 在本部分中的主题提供使用单元测试功能的一些示例方法。 当启用此功能并重新生成项目，类将派生自以下基类以支持单元测试的项目。  
  
|项目类型|基类|  
|-------------------|----------------|  
|架构|**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**|  
|映射|**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**|  
|管道|**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用单元测试功能架构和映射](../core/using-the-unit-testing-feature-with-schemas-and-maps.md)  
  
-   [使用单元测试功能管道](../core/using-the-unit-testing-feature-with-pipelines.md)  
  
## <a name="related-sections"></a>相关章节  
 [使用单元测试 (Visual Studio)](http://go.microsoft.com/fwlink/?LinkId=128890)