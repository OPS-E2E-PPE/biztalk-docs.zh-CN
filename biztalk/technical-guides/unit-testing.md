---
title: 单元测试 |Microsoft 文档
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
ms.openlocfilehash: d5f792adf73fb1e3791f0dfe6c8c5f60a3bb81e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009830"
---
# <a name="unit-testing"></a>单元测试
BizTalk Server 引入了单元测试可在中启用的功能**部署**BizTalk 项目属性页。 以下屏幕截图显示当你右键单击某个项目并单击时从项目设计器访问此项目设置**属性**。  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 **项目设计器公开启用单元测试项目属性中的部署选项卡的屏幕截图**  
  
 此功能允许您为架构、映射和管道创建单元测试。 BizTalk Server 文档中的主题提供对使用单元测试功能的一些示例方法。 启用此功能并且重建项目之后，将从以下基类中派生项目类以支持单元测试。  
  
|项目类型|基类|  
|-------------------|----------------|  
|架构|**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**|  
|映射|**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**|  
|管道|**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**|  
  
 有关的单元测试与 BizTalk Server 引入的功能的详细信息，请参阅 BizTalk Server 帮助中的以下主题：  
  
-   [使用单元测试功能包含架构和映射](http://go.microsoft.com/fwlink/?LinkId=150482)(http://go.microsoft.com/fwlink/?LinkId=150482)。  
  
-   [使用单元测试使用管道功能](http://go.microsoft.com/fwlink/?LinkId=150483)(http://go.microsoft.com/fwlink/?LinkId=150483)  
  
## <a name="see-also"></a>另请参阅  
 [实现自动测试](../technical-guides/implementing-automated-testing.md)