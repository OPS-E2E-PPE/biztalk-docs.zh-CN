---
title: 第 1 步：引用架构 DLL1 |Microsoft Docs
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
ms.openlocfilehash: 41fa9a1e50fda5e31cb6a6c49f4b6e758671d103
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392951"
---
# <a name="step-1-reference-the-schema-dll"></a>第 1 步：引用架构 DLL
在 BizTalk 中，消息是不可变的。 因此，若要更改属性值必须创建和修改新消息。 创建和修改新消息的方法是插入消息赋值形状在接收和发送形状之间。  
  
 但是，您必须首先引用架构 DLL 才能访问 j.d. Edwards EnterpriseOne 上下文属性。  
  
### <a name="to-reference-the-schema-dll"></a>若要引用架构 DLL  
  
1. 创建工作文件夹，例如，c:\class\JDE\BeginDoc 为你的项目和文件夹将在其中放置测试 XML，例如，c:\class\JDE\input。  
  
2. 创建静态要求响应发送端口将请求发送到 J.D. Edwards EnterpriseOne。  
  
    ![JDOneWorld 传输属性](../core/media/example-2waysendport-ow.gif "example_2waysendport_OW")  
  
3. 在解决方案编辑器中，右键单击你的项目。  
  
   1. 选择**外**，选择**添加生成的项**，然后单击**添加适配器**。  
  
   2. 选择用于 J.D.的 Microsoft BizTalk 适配器 Edwards EnterpriseOne 和刚创建的端口。  
  
   3. 在中**添加适配器向导**，选择**CSALES\B4200310**。  
  
   4. 单击**完成**生成包含格式的消息的架构。  
  
      ![添加适配器向导](../core/media/add-adapter-wizard.gif "add_adapter_wizard")  
  
4. 在 Visual Studio 中，打开解决方案资源管理器。  
  
5. 右键单击**引用**，然后选择**添加引用**。  
  
6. 上**添加引用**屏幕上，单击**浏览**按钮。  
  
7. 上**选择组件**屏幕上，导航到 %SystemDrive%\Program Files\Common Files\Microsoft BizTalk Adapters for Enterprise Applications\bin。  
  
8. 选择**Microsoft.Adapters.JDEProperties.dll**，然后单击**打开**。  
  
9. 上**添加引用**屏幕上，该 DLL 中将显示**选定的组件**部分。  
  
     ![选择属性屏幕](../core/media/properties-selection.gif "properties_selection")  
  
10. 单击“确定” 。  
  
11. 双击业务流程访问业务流程设计器。  
  
     \- 或 -  
  
     选择**视图**，选择**其他 Windows**，然后单击**业务流程视图**。  
  
     将显示业务流程视图。  
  
## <a name="see-also"></a>请参阅  
 [步骤 2：创建业务流程](../core/step-2-create-the-orchestration2.md)   
 [任务 4:配置构造消息形状](../core/task-4-configure-the-construct-message-shape1.md)   
 [任务 5:配置转换形状](../core/task-5-configure-the-transform-shape2.md)   
 [步骤 3：完成并运行项目](../core/step-3-complete-and-run-the-project1.md)   
 [步骤 4：创建示例 XML BeginDoc](../core/step-4-create-a-sample-xml-begindoc2.md)