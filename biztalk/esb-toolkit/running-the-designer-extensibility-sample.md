---
title: "运行设计器扩展性示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05ac3b50-5bf2-4566-8654-472391476d1f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b26c483568e1ceb05679d7548721c1cce818fde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-designer-extensibility-sample"></a>运行设计器扩展性示例
设计器扩展性示例使用两个示例扩展程序来演示如何提供设计时配置选项的自定义解析程序和路线的服务。  
  
 **若要运行设计器扩展性示例**  
  
1.  启动 [!INCLUDE[vs2010](../includes/vs2010-md.md)]。  
  
2.  在 Visual Studio 中，依次指向**新建**上**文件**菜单，，然后单击**项目**。  
  
3.  选择 C# 类库模板类型**ItineraryLibrary**中**名称**框中，并依次**确定**。  
  
4.  在解决方案资源管理器，右键单击 ItineraryLibrary 项目，指向**添加**，然后单击**新路线**。  
  
5.  在**名称**框中，键入**TestItinerary**，然后按 ENTER。  
  
6.  在工具箱中，单击 On 负载增加模型元素，并将它拖动到设计图面。  
  
7.  在工具箱中，单击路线服务模型元素，并将它拖动到设计图面。  
  
8.  在工具箱中，单击另一个路线服务模型元素，并将它拖动到设计图面。  
  
9. 在工具箱中，单击 Off 负载增加模型元素，并将它拖动到设计图面。  
  
10. 在工具箱中，单击连接器工具，然后拖动之间的连接**OnRamp1**模型元素和**ItineraryService1**模型元素。  
  
11. 在工具箱中，单击连接器工具，然后拖动之间的连接**ItineraryService1**模型元素和**ItineraryService2**模型元素。  
  
12. 在工具箱中，单击连接器工具，然后拖动之间的连接**ItineraryService2**模型元素和**OffRamp1**模型元素。  
  
13. 单击**OnRamp1**模型元素，并在属性窗口中，将扩展程序属性为**上负载增加 ESB 服务扩展**。  
  
14. 设置**BizTalk 应用程序**属性**Microsoft.Practices.ESB**。  
  
15. 设置**接收端口**属性**OnRamp.Itinerary**。  
  
16. 单击**ItinearyService1**模型元素，并在属性窗口中，将**扩展程序**属性**示例业务流程路线服务扩展**。  
  
    > [!NOTE]
    >  这是自定义设计器扩展性示例的一部分安装的扩展。 它允许你将属性添加到传递给基于业务流程的路线服务的属性包。  
  
17. 设置**OtherValue**属性**1**。  
  
18. 设置**ServiceName**属性**Microsoft.Practices.ESB.Services.Routing**。  
  
19. 设置**SomeValue**属性**2**。  
  
20. 右键单击**冲突解决程序**集合**ItineraryService1**，然后单击**添加新解析程序**。  
  
21. 单击**Resolver1**，然后在属性窗口中，设置**解析程序实现**属性**示例冲突解决程序扩展**。  
  
22. 设置**SomeResolverValue**属性**测试**，然后将版本属性设置为**1.0**。  
  
23. 单击**ItineraryService2**模型元素，并在属性窗口中，将**路线服务扩展程序**属性**关闭负载增加路线服务扩展**.  
  
24. 设置**关闭负载增加**属性**OffRamp1 > 发送处理程序**。  
  
25. 单击**OffRamp1**模型元素，并在属性窗口中，将**扩展程序**属性**关闭负载增加 ESB 服务扩展**。  
  
26. 设置**BizTalk 应用程序**属性**GlobalBank.ESB**。  
  
27. 设置**发送端口**属性**DynamicResolutionOneWay**。  
  
28. 右键单击设计图面上，并依次**导出模型**。  
  
29. 检查生成的 XML。  
  
    > [!NOTE]
    >  请注意**PropertyBag**元素和它包含的属性。 另请注意的示例解析程序连接字符串和配置它的方式根据输入的属性。