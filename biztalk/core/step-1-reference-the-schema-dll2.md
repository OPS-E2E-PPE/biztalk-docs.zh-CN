---
title: "步骤 1： 引用架构 DLL2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1db92227-6164-42b9-b60c-12dd2cae46e2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5b009e2c79c0ea68030561c51e3a90ceef24eba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-reference-the-schema-dll"></a>步骤 1： 引用 DLL 的架构
在 BizTalk 中，消息是不可改变的。 因此，若要更改属性值，必须创建和修改新消息。 通过在接收形状和发送形状之间插入消息赋值形状可以创建和修改新消息。  
  
 但是，必须首先引用架构 DLL 才能访问 J.D. Edwards 上下文属性。  
  
### <a name="to-reference-the-schema-dll"></a>若要引用 DLL 的架构  
  
1.  为项目创建工作文件夹，例如 c:\class\JDE\BeginDoc，并创建用于放置测试 XML 的文件夹，例如 c:\class\JDE\input。  
  
2.  创建静态请求-响应发送端口将请求发送到 J.D. Edwards OneWorld。  
  
     ![](../core/media/jde-example-2waysendport-ow.gif "JDE_example_2waysendport_OW")  
  
3.  在解决方案编辑器中，右键单击项目。  
  
    1.  选择**添加**，选择**添加生成的项**，然后单击**添加适配器**。  
  
    2.  为 J.D.选择 Microsoft BizTalk 适配器 Edwards OneWorld 和刚创建的端口。  
  
    3.  在**添加适配器向导**，选择**CSALES\B4200310**。  
  
    4.  单击**完成**来生成包含格式的消息的架构。  
  
     ![](../core/media/jde-add-adapter-wizard.gif "JDE_add_adapter_wizard")  
  
4.  在 Visual Studio 中，打开解决方案资源管理器。  
  
5.  右键单击**引用**，然后选择**添加引用**。  
  
6.  上**添加引用**屏幕上，单击**浏览**按钮。  
  
     ![](../core/media/jde-add-reference-dll.gif "JDE_add_reference_dll")  
  
7.  上**选择组件**屏幕上，为企业 Applications\bin 导航到 %SystemDrive%\Program Files\Common Files\Microsoft BizTalk 适配器。  
  
8.  选择**Microsoft.Adapters.JDEProperties.dll**，然后单击**打开**。  
  
9. 上**添加引用**DLL 中出现的屏幕，**选定的组件**部分。  
  
     ![](../core/media/jde-properties-selection.gif "JDE_properties_selection")  
  
10. 单击 **“确定”**。  
  
11. 双击业务流程可访问业务流程设计器。  
  
     \- 或 -  
  
     选择**视图**，选择**其他窗口**，然后单击**业务流程视图**。  
  
     随即将显示业务流程视图。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 2： 创建业务流程](../core/step-2-create-the-orchestration1.md)   
 [步骤 3： 完成并运行项目](../core/step-3-complete-and-run-the-project2.md)   
 [步骤 4： 创建示例 XML BeginDoc](../core/step-4-create-a-sample-xml-begindoc1.md)