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
# <a name="unit-testing"></a>单元测试
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]引入了单元测试可在中启用的功能**部署**BizTalk 项目属性页。 以下屏幕截图显示当你右键单击某个项目并单击时从项目设计器访问此项目设置**属性**。  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 **项目设计器公开启用单元测试项目属性中的部署选项卡的屏幕截图**  
  
 此功能允许您为架构、映射和管道创建单元测试。 中的主题[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]文档提供一些示例方法使用的单元测试功能。 启用此功能并且重建项目之后，将从以下基类中派生项目类以支持单元测试。  
  
|项目类型|基类|  
|-------------------|----------------|  
|架构|**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**|  
|映射|**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**|  
|管道|**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**|  
  
 有关单元测试功能引入了[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，请参阅中的以下主题[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]帮助：  
  
-   [使用单元测试功能包含架构和映射](http://go.microsoft.com/fwlink/?LinkId=150482)(http://go.microsoft.com/fwlink/?LinkId=150482)。  
  
-   [使用单元测试使用管道功能](http://go.microsoft.com/fwlink/?LinkId=150483)(http://go.microsoft.com/fwlink/?LinkId=150483)  
  
## <a name="see-also"></a>另请参阅  
 [实现自动测试](../technical-guides/implementing-automated-testing.md)