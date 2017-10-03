---
title: "在业务流程设计器中工作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, saving
- deleting, orchestrations
- projects, orchestrations
- orchestrations, properties
- orchestrations, creating
- creating, orchestrations
- naming conventions, orchestrations
- orchestrations, naming conventions
- orchestrations, deleting
ms.assetid: 13e72b41-d9b6-4508-9a44-b3c7c1804f36
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 512dc85fb1599bdaa77fe2550390ec2ce6954643
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="working-in-orchestration-designer"></a>使用业务流程设计器
在您开始了某一 BizTalk 项目后，可以创建新的业务流程和向该项目添加现有业务流程。 请参阅下面的过程来创建和保存业务流程、将现有业务流程添加到某一项目或从项目中删除现有业务流程、更改业务流程的名称以及设置业务流程属性。  
  
### <a name="to-create-an-orchestration"></a>若要创建业务流程  
  
1.  在解决方案资源管理器，右键单击项目名称，选择**添加**，然后单击**新项**。  
  
2.  在**添加新项**对话框中，在**类别**窗格中，单击**BizTalk 项目项**，然后在**模板**窗格中，单击**BizTalk 业务流程**。  
  
3.  在**名称**底部的对话框框中，为业务流程，提供一个名称，然后单击**添加**。  
  
     新的业务流程即在业务流程设计器中创建和显示，并且相应的 .odx 文件在解决方案资源管理器中创建和显示。  
  
### <a name="to-add-an-existing-orchestration-to-a-project"></a>向项目添加现有业务流程  
  
1.  在解决方案资源管理器，右键单击项目名称，单击**添加**，然后单击**现有项**。  
  
2.  在**添加现有项**对话框中，导航到包含业务流程的目录，选择的业务流程，，然后单击**添加**。  
  
     该业务流程将添加到项目中。  
  
    > [!NOTE]
    >  添加现有文件时，该文件将复制到您的项目中。 （该文件不是只通过引用的方式添加。）如果在项目中更改该文件，原始文件仍保持不变。  
  
### <a name="to-change-the-name-of-an-orchestration"></a>更改业务流程的名称  
  
1.  在解决方案资源管理器，右键单击你想要更改，，然后单击.odx 文件**重命名**。  
  
2.  键入想要的新文件名，然后按下 ENTER。  
  
    > [!NOTE]
    >  当您更改.odx 文件的名称时，可能还想要更改 orchestration 类型的名称通过单击设计图面，以打开属性窗口上，并将更改的值**Typename**属性业务流程。  
  
### <a name="to-save-an-orchestration"></a>保存业务流程  
  
-   上**文件**菜单上，单击**保存\<orchestration 名称 >**。  
  
    > [!NOTE]
    >  业务流程文件保存为 utf-8。  架构、 映射和管道将保存为 utf-16。  
  
### <a name="to-remove-an-orchestration-from-a-project"></a>从项目中删除业务流程  
  
-   在解决方案资源管理器，右键单击你想要删除，，然后单击的文件**从项目中排除**。  
  
    > [!NOTE]
    >  若要从项目移除业务流程和永久删除此文件，请单击**删除**相反。  
  
### <a name="to-include-an-excluded-orchestration-in-a-project"></a>在项目中包括已排除的业务流程  
  
-   在解决方案资源管理器，单击**全部显示**工具栏按钮，右键单击你想，.odx 文件并选择**包括在项目**。  
  
### <a name="to-set-orchestration-properties"></a>设置业务流程属性  
  
1.  通过双击项目中的 .odx 文件，或者通过在流程区域中选择包含业务流程的选项卡，打开业务流程。  
  
2.  在业务流程视图窗口中，选择**业务流程属性**。  
  
     -或者-  
  
     单击**过程区域**背景的业务流程设计图面。  
  
3.  在“属性”窗口中，指定以下属性。 请注意，某些属性仅在某些情况下出现。  
  
    > [!NOTE]
    >  业务流程的名称、端口类型和多部分消息类型在模块的作用域内必须唯一。  
  
    |属性|Description|  
    |--------------|-----------------|  
    |批处理|确定作为原子事务的业务流程是否可与其他实例一起执行批处理。|  
    |补偿|指定要对业务流程执行的补偿类型。|  
    |隔离级别|对于事务性业务流程，确定并发事务中数据可访问的程度。|  
    |可导出模块|确定模块是否可导出到 BPEL4WS。|  
    |模块 XML 目标命名空间|将类型导出到 BPEL4WS 时使用的 XML 目标命名空间。|  
    |命名空间|确定包括业务流程和业务流程类型的包含模块的名称。|  
    |可导出的业务流程|指示此业务流程是否可导出到 BPEL4WS。|  
    |业务流程 XML 目标命名空间|将此业务流程导出到 BPEL4WS 时使用的 XML 目标命名空间。|  
    |重试|指定事务性业务流程失败后是否重试该业务流程。|  
    |超时|事务性业务流程失败之前处于非活动状态的时间（以秒计）。|  
    |事务标识符|用于事务性业务流程的唯一标识符。|  
    |事务类型|确定业务流程是原子事务、长期事务还是业务流程未进行事务处理。|  
    |类型修饰符|确定业务流程级别变量的作用域：<br /><br /> 私有-与此业务流程的访问仅限于包含模块。<br /><br /> 公共-与此业务流程的访问不受限制。<br /><br /> 内部 — 与此业务流程的访问仅限于同一项目中的模块。|  
    |类型名称|确定此业务流程在包含模块内的名称。 **注意：**如果你使用与根级命名空间中，相同的类型名称定义消息并基于 e，尝试执行变量将在其上的操作时，可能会从 Orchestration 设计器收到错误。 例如，如果您指定某一系统类型名称，然后定义 System.String 之类的消息和变量，则可能会收到错误消息。|  
  
## <a name="see-also"></a>另请参阅  
 [业务流程形状](../core/orchestration-shapes.md)   
 [如何将形状添加到业务流程](../core/how-to-add-shapes-to-orchestrations.md)   
 [如何将参数添加到业务流程](../core/how-to-add-parameters-to-orchestrations.md)   
 [如何使用选择项目类型对话框](../core/how-to-use-the-select-artifact-type-dialog-box.md)