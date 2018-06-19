---
title: 步骤 1： 引用架构 DLL1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47e4b773-e484-4931-9ab2-b8dd0080ea1c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c2d5051c7dfd3c0f971b34922ca4e5747117c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279437"
---
# <a name="step-1-reference-the-schema-dll"></a>步骤 1： 引用 DLL 的架构
在 BizTalk 中，消息是不可改变的。 因此，若要更改属性值，必须创建和修改新消息。 通过在接收形状和发送形状之间插入消息赋值形状可以创建和修改新消息。  
  
 但是，必须首先引用架构 DLL 才能访问 J.D. Edwards EnterpriseOne 上下文属性。  
  
### <a name="to-reference-the-schema-dll"></a>若要引用 DLL 的架构  
  
1.  为项目创建工作文件夹，例如 c:\class\JDE\BeginDoc，并创建用于放置测试 XML 的文件夹，例如 c:\class\JDE\input。  
  
2.  创建静态请求-响应发送端口将请求发送到 J.D. Edwards EnterpriseOne。  
  
     ![JDOneWorld 传输属性](../core/media/example-2waysendport-ow.gif "example_2waysendport_OW")  
  
3.  在解决方案编辑器中，右键单击项目。  
  
    1.  选择**添加**，选择**添加生成的项**，然后单击**添加适配器**。  
  
    2.  为 J.D.选择 Microsoft BizTalk 适配器 Edwards EnterpriseOne 和刚创建的端口。  
  
    3.  在**添加适配器向导**，选择**CSALES\B4200310**。  
  
    4.  单击**完成**来生成包含格式的消息的架构。  
  
     ![添加适配器向导](../core/media/add-adapter-wizard.gif "add_adapter_wizard")  
  
4.  在 Visual Studio 中，打开解决方案资源管理器。  
  
5.  右键单击**引用**，然后选择**添加引用**。  
  
6.  上**添加引用**屏幕上，单击**浏览**按钮。  
  
7.  上**选择组件**屏幕上，为企业 Applications\bin 导航到 %SystemDrive%\Program Files\Common Files\Microsoft BizTalk 适配器。  
  
8.  选择**Microsoft.Adapters.JDEProperties.dll**，然后单击**打开**。  
  
9. 上**添加引用**DLL 中出现的屏幕，**选定的组件**部分。  
  
     ![属性选择屏幕](../core/media/properties-selection.gif "properties_selection")  
  
10. 单击 **“确定”**。  
  
11. 双击业务流程可访问业务流程设计器。  
  
     \- 或 -  
  
     选择**视图**，选择**其他窗口**，然后单击**业务流程视图**。  
  
     随即将显示业务流程视图。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 2： 创建业务流程](../core/step-2-create-the-orchestration2.md)   
 [任务 4： 配置构造消息形状](../core/task-4-configure-the-construct-message-shape1.md)   
 [任务 5： 配置转换形状](../core/task-5-configure-the-transform-shape2.md)   
 [步骤 3： 完成并运行项目](../core/step-3-complete-and-run-the-project1.md)   
 [步骤 4： 创建示例 XML BeginDoc](../core/step-4-create-a-sample-xml-begindoc2.md)