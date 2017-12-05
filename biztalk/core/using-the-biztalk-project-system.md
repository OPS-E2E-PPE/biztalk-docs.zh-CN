---
title: "使用 BizTalk 项目系统 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Editor, opening
- BizTalk Mapper, opening
- Orchestration Designer, opening
- Pipeline Designer, opening
ms.assetid: a28c715e-128c-463a-b421-9b3efe76a530
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5b8c3a83d75219b9e52fd2ab13124480d772832
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="using-the-biztalk-project-system"></a>使用 BizTalk 项目系统
使用 BizTalk 项目系统可以在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 环境下创建、组织和配置 BizTalk 解决方案。 主题和此部分中的过程介绍如何使用 BizTalk 项目系统执行各种任务。  
  
 BizTalk Server 项目系统使用的相同项目管理原则和与其他 Microsoft Build Engine (MSBuild) 项目中使用的过程[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 本部分详细介绍了在创建运行于 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上的应用程序时可能使用的通用步骤。  
  
 有关 MSBuild 的详细信息，请参阅中的 MSBuild 参考部分[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]结合使用集合中位置[http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)。  
  
 有关使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]环境，请参阅中的"管理解决方案、 项目和文件"[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]结合使用集合中位置[http://msdn.microsoft.com/library/wbzbtw81.aspx](http://msdn.microsoft.com/library/wbzbtw81.aspx)。  
  
 下图显示了 BizTalk 项目系统设计环境与**新项目**对话框中打开。  
  
 ![项目系统](../core/media/bts-biztalk2009-projectsystems.gif "bts_BizTalk2009_ProjectSystems")  
描述了项目系统设计环境  
  
### <a name="to-open-biztalk-editor"></a>若要打开 BizTalk 编辑器  
  
1.  在解决方案资源管理器，单击架构。  
  
    > [!NOTE]
    >  若要打开 BizTalk 编辑器，必须首先创建架构，或打开以前创建的架构。 有关创建架构的信息，请参阅[如何创建 XML 消息的架构](../core/how-to-create-schemas-for-xml-messages.md)。 另请参阅[添加项目项](../core/adding-project-items.md)。  
  
2.  上**视图**菜单上，单击**打开**。  
  
     -或者-  
  
     右键单击的架构，然后单击**打开**。  
  
     -或者-  
  
     双击架构。  
  
     在 BizTalk 编辑器中打开所选的架构。  
  
    > [!NOTE]
    >  若要创建架构，你必须打开一个项目。 有关如何创建项目的信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。 有关将项添加到项目的信息，请参阅[如何创建 XML 消息的架构](../core/how-to-create-schemas-for-xml-messages.md)。 另请参阅[添加项目项](../core/adding-project-items.md)。  
  
### <a name="to-open-biztalk-mapper"></a>若要打开 BizTalk 映射程序  
  
1.  在解决方案资源管理器，单击映射。  
  
    > [!NOTE]
    >  若要打开 BizTalk 映射程序，必须首先创建一个映射中，或打开以前创建的映射。 有关创建地图的信息，请参阅[如何创建新映射](../core/how-to-create-new-maps.md)。 另请参阅[添加项目项](../core/adding-project-items.md)。  
  
2.  上**视图**菜单上，单击**打开**。  
  
     -或者-  
  
     右键单击图，并依次**打开**。  
  
     -或者-  
  
     双击一个映射。  
  
     在 BizTalk 映射程序中打开所选的映射。  
  
    > [!NOTE]
    >  若要创建映射时，你必须打开一个项目。 有关如何创建项目的信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。 有关将项添加到项目的信息，请参阅[添加项目项](../core/adding-project-items.md)。 另请参阅[如何创建新映射](../core/how-to-create-new-maps.md)。  
  
### <a name="to-open-orchestration-designer"></a>若要打开业务流程设计器  
  
1.  在解决方案资源管理器，单击业务流程 (.odx)。  
  
    > [!NOTE]
    >  若要打开业务流程设计器，必须首先创建一个业务流程中，或打开以前创建的业务流程。 有关如何创建业务流程的信息，请参阅[在业务流程设计器中工作](../core/working-in-orchestration-designer.md)。  
  
2.  上**视图**菜单上，单击**打开**。  
  
     -或者-  
  
     右键单击业务流程，并依次**打开**。  
  
     -或者-  
  
     双击业务流程。  
  
     此时，将打开业务流程设计器。  
  
    > [!NOTE]
    >  若要创建业务流程，你必须打开一个项目。 有关如何创建项目的信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。 有关将项添加到项目的信息，请参阅[添加项目项](../core/adding-project-items.md)。 另请参阅[在业务流程设计器中工作](../core/working-in-orchestration-designer.md)。  
  
### <a name="to-open-pipeline-designer"></a>若要打开管道设计器  
  
1.  在解决方案资源管理器，单击管道。  
  
    > [!NOTE]
    >  若要打开管道设计器，则必须首先创建一个管道，或打开一个先前创建的管道。 有关如何创建管道的信息，请参阅[如何创建一条新管道](../core/how-to-create-a-new-pipeline.md)。  
  
2.  上**视图**菜单上，单击**打开**。  
  
     -或者-  
  
     右击管道，，然后单击**打开**。  
  
     -或者-  
  
     双击该管道。  
  
     此时，将打开管道设计器。  
  
    > [!NOTE]
    >  若要创建管道，则必须打开项目。 有关如何创建项目的信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。 有关将项添加到项目的信息，请参阅[添加项目项](../core/adding-project-items.md)。 另请参阅[在业务流程设计器中工作](../core/working-in-orchestration-designer.md)。  
  
## <a name="see-also"></a>另请参阅  
 [创建使用业务流程设计器的业务流程](../core/creating-orchestrations-using-orchestration-designer.md)   
 [使用管道设计器](../core/using-pipeline-designer.md)   
 [业务规则编辑器的窗口](../core/windows-of-the-business-rule-composer.md)   
 [使用 BizTalk 编辑器](../core/using-biztalk-editor.md)   
 [使用 BizTalk 映射程序](../core/using-biztalk-mapper.md)   
 [开发人员工具](../core/developer-tools.md)