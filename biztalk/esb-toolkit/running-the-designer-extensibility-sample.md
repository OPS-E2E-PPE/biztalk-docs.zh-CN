---
title: 运行设计器扩展性示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05ac3b50-5bf2-4566-8654-472391476d1f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdfaf1ca75d480e219b0c99fb903b1997859a18f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292493"
---
# <a name="running-the-designer-extensibility-sample"></a>运行设计器扩展性示例
设计器扩展性示例使用两个示例扩展程序来演示如何为自定义冲突解决程序和路线服务提供设计时配置选项。  
  
 **若要运行设计器扩展性示例**  
  
1.  启动 Visual Studio。  
  
2.  在 Visual Studio 中，指向**新建**上**文件**菜单，并单击**项目**。  
  
3.  选择C#类库模板中，键入**ItineraryLibrary**中**名称**框中，然后依次**确定**。  
  
4.  在解决方案资源管理器，右键单击 ItineraryLibrary 项目，指向**外**，然后单击**新路线**。  
  
5.  在中**名称**框中，键入**TestItinerary**，然后按 ENTER。  
  
6.  在工具箱中，单击 On 接入点模型元素，并将它拖动到设计图面。  
  
7.  在工具箱中，单击路线服务模型元素，并将它拖动到设计图面。  
  
8.  在工具箱中，单击另一个路线服务模型元素，并将它拖动到设计图面。  
  
9. 在工具箱中，单击 Off 接入点模型元素，并将它拖动到设计图面。  
  
10. 在工具箱中，单击连接器工具，然后拖动之间的连接**OnRamp1**模型元素和**ItineraryService1**模型元素。  
  
11. 在工具箱中，单击连接器工具，然后拖动之间的连接**ItineraryService1**模型元素和**ItineraryService2**模型元素。  
  
12. 在工具箱中，单击连接器工具，然后拖动之间的连接**ItineraryService2**模型元素和**OffRamp1**模型元素。  
  
13. 单击**OnRamp1**模型元素，，然后在属性窗口中，将扩展程序属性设置为**接入点 ESB 服务扩展**。  
  
14. 设置**BizTalk 应用程序**属性设置为**Microsoft.Practices.ESB**。  
  
15. 设置**接收端口**属性设置为**OnRamp.Itinerary**。  
  
16. 单击**ItinearyService1**模型元素，并在属性窗口中设置**Extender**属性设置为**示例业务流程路线服务扩展**。  
  
    > [!NOTE]
    >  这是设计器扩展性示例的一部分安装的自定义扩展。 它允许您将属性添加到传递给业务流程基于路线服务的属性包。  
  
17. 设置**OtherValue**属性设置为**1**。  
  
18. 设置**ServiceName**属性设置为**Microsoft.Practices.ESB.Services.Routing**。  
  
19. 设置**SomeValue**属性设置为**2**。  
  
20. 右键单击**冲突解决程序**系列**ItineraryService1**，然后单击**添加新解析程序**。  
  
21. 单击**Resolver1**，然后在属性窗口中设置**解析程序实现**属性设置为**解析程序扩展插件示例**。  
  
22. 设置**SomeResolverValue**属性设置为**测试**，然后将版本属性设置为**1.0**。  
  
23. 单击**ItineraryService2**模型元素，并在属性窗口中设置**路线服务扩展器**属性设置为**关闭接入点路线服务扩展**.  
  
24. 设置**关闭负载增加**属性设置为**OffRamp1 > 发送处理程序**。  
  
25. 单击**OffRamp1**模型元素，并在属性窗口中设置**Extender**属性设置为**关闭负载增加 ESB 服务扩展**。  
  
26. 设置**BizTalk 应用程序**属性设置为**GlobalBank.ESB**。  
  
27. 设置**发送端口**属性设置为**DynamicResolutionOneWay**。  
  
28. 右键单击设计图面上，然后依次**导出模型**。  
  
29. 检查生成的 XML。  
  
    > [!NOTE]
    >  请注意**PropertyBag**元素和它包含的属性。 此外请注意示例冲突解决程序连接字符串和配置方式基于输入的属性。