---
title: 单元测试 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c40e5b82-dbb2-4767-8286-88e2de4129f3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d92743dbfde629212231e9fb8a1e73496f4ca6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400598"
---
# <a name="unit-testing"></a>单元测试
BizTalk Server 引入了单元测试功能，可以在启用了**部署**BizTalk 项目属性页。 以下屏幕截图显示右键单击项目，然后单击从项目设计器访问此项目设置**属性**。  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 **项目设计器将公开启用单元测试项目属性中的部署选项卡的屏幕截图**  
  
 此功能允许你创建单元测试的架构、 映射和管道。 BizTalk Server 文档中的主题提供使用单元测试功能的一些示例方法。 当启用此功能并重新生成项目，类将派生自以下基类以支持单元测试的项目。  
  
|项目类型|基类|  
|-------------------|----------------|  
|架构|**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**|  
|映射|**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**|  
|管道|**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**|  
  
 有关单元测试与 BizTalk Server 中引入的功能的详细信息，请参阅 BizTalk Server 帮助中的以下主题：  
  
-   [使用单元测试功能架构和映射](http://go.microsoft.com/fwlink/?LinkId=150482)(http://go.microsoft.com/fwlink/?LinkId=150482)。  
  
-   [使用单元测试功能管道](http://go.microsoft.com/fwlink/?LinkId=150483)(http://go.microsoft.com/fwlink/?LinkId=150483)  
  
## <a name="see-also"></a>请参阅  
 [实现自动测试](../technical-guides/implementing-automated-testing.md)