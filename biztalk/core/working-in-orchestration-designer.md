---
title: 在业务流程设计器中工作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a239c3660fbd5559a6d504dc9f39d94df8a6c6d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240285"
---
# <a name="working-in-orchestration-designer"></a>在业务流程设计器中工作
启动 BizTalk 项目后，可以创建新的业务流程并向项目添加现有业务流程。 请参阅以下过程来创建和保存业务流程，以向项目添加现有的业务流程或删除其中一个从它，若要更改业务流程的名称以及设置业务流程属性。  
  
### <a name="to-create-an-orchestration"></a>若要创建一个业务流程  
  
1.  在解决方案资源管理器，右键单击项目名称，选择**外**，然后单击**新项**。  
  
2.  在中**添加新项**对话框中**类别**窗格中，单击**BizTalk 项目项**，然后在**模板**窗格中，单击**BizTalk 业务流程**。  
  
3.  在中**名称**框底部的对话框中，为业务流程中，提供一个名称，然后单击**添加**。  
  
     创建新的业务流程并将其显示在业务流程设计器中，并创建相应的.odx 文件并将其显示在解决方案资源管理器。  
  
### <a name="to-add-an-existing-orchestration-to-a-project"></a>若要向项目添加现有的业务流程  
  
1.  在解决方案资源管理器，右键单击项目名称，单击**外**，然后单击**现有项**。  
  
2.  在中**添加现有项**对话框中，导航到包含该业务流程的目录，选择的业务流程，然后单击**添加**。  
  
     业务流程添加到项目。  
  
    > [!NOTE]
    >  时添加现有文件，该文件复制到你的项目。 （该文件不会只需添加引用。）如果在项目中更改的文件，原始文件仍保持不变。  
  
### <a name="to-change-the-name-of-an-orchestration"></a>若要更改业务流程的名称  
  
1.  在解决方案资源管理器中右键单击你想要更改，并单击该.odx 文件**重命名**。  
  
2.  键入新的文件名称，然后按 ENTER。  
  
    > [!NOTE]
    >  当您更改.odx 文件的名称时，您可能还需要单击设计图面以显示属性窗口上，更改的值更改业务流程类型的名称**Typename**属性业务流程。  
  
### <a name="to-save-an-orchestration"></a>若要保存业务流程  
  
-   上**文件**菜单上，单击**保存\<业务流程名称\>**。  
  
    > [!NOTE]
    >  业务流程文件将保存为 utf-8。  架构、 映射和管道都另存为 utf-16。  
  
### <a name="to-remove-an-orchestration-from-a-project"></a>若要从项目中删除业务流程  
  
-   在解决方案资源管理器中右键单击你想要删除，然后单击的文件**从项目中排除**。  
  
    > [!NOTE]
    >  若要从项目中删除该业务流程并永久删除该文件，请单击**删除**相反。  
  
### <a name="to-include-an-excluded-orchestration-in-a-project"></a>若要包括在项目中排除的业务流程  
  
-   在解决方案资源管理器，单击**全部显示**工具栏按钮，右键单击所需的.odx 文件并选择**包括在项目**。  
  
### <a name="to-set-orchestration-properties"></a>若要设置业务流程属性  
  
1.  打开该业务流程的.odx 文件在项目中，双击或通过选择包含在流程区域中的业务流程选项卡。  
  
2.  在业务流程视图窗口中，选择**业务流程属性**。  
  
     -或-  
  
     单击**流程区域**业务流程设计图面背景。  
  
3.  在属性窗口中，指定以下属性。 请注意，某些属性仅在某些情况下将显示。  
  
    > [!NOTE]
    >  业务流程、 端口类型和多部分消息类型的名称必须是模块的作用域内唯一。  
  
    |属性|Description|  
    |--------------|-----------------|  
    |批处理|确定是否可以与其他实例批处理是原子事务的业务流程。|  
    |补偿|指定哪种类型的补偿业务流程上执行。|  
    |隔离级别|对于事务性业务流程，确定并发事务中可访问数据的程度。|  
    |可导出模块|确定该模块可导出到 BPEL4WS。|  
    |模块 XML 目标 Namespace|将类型导出到 BPEL4WS 时使用的 XML 目标命名空间。|  
    |命名空间|确定包括业务流程和业务流程类型的包含模块的名称。|  
    |可导出的业务流程|指示是否适用此业务流程可导出到 BPEL4WS。|  
    |业务流程 XML 目标 Namespace|将此业务流程导出到 BPEL4WS 时使用的 XML 目标命名空间。|  
    |重试|指定是否失败后重试事务性业务流程。|  
    |超时|时间 （秒） 直到事务性业务流程因处于非活动状态。|  
    |事务标识符|事务性业务流程的唯一标识符。|  
    |事务类型|确定是否在业务流程是原子事务、 长时间运行的事务，或者未进行事务处理。|  
    |类型修饰符|确定业务流程级别变量的作用域：<br /><br /> 私有 — 对此业务流程的访问仅限于包含模块。<br /><br /> 公共 — 对此业务流程的访问没有限制。<br /><br /> 内部 — 对此业务流程的访问仅限于同一项目中的模块。|  
    |类型名称|确定此业务流程中包含的模块的名称。 **注意：** 如果你使用与根级别命名空间中，相同的类型名称定义消息和变量的类型名称和尝试执行分配操作在其上的时，可能会从业务流程设计器收到错误。 例如，如果指定一个系统类型名称，然后定义 System.String 之类的变量和消息，你可能会收到错误。|  
  
## <a name="see-also"></a>请参阅  
 [业务流程形状](../core/orchestration-shapes.md)   
 [如何向业务流程添加形状](../core/how-to-add-shapes-to-orchestrations.md)   
 [如何将参数添加到业务流程](../core/how-to-add-parameters-to-orchestrations.md)   
 [如何使用选择项目类型对话框](../core/how-to-use-the-select-artifact-type-dialog-box.md)