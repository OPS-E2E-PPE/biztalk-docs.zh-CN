---
title: 使用 Visual Studio |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio
ms.assetid: 1ef68df2-5205-4d96-9e0f-0ae78800a121
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05bf1d9d186037f709ec51ad5b63d54db5635880
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970158"
---
# <a name="using-visual-studio"></a>使用 Visual Studio
在 BizTalk 项目系统中，可以使用 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中提供的许多工具，还可以使用为创建在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上运行的应用程序而专门设计的工具。 本主题介绍了一些可用来创建在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上运行的应用程序的通用过程。  

 在使用 BizTalk 项目系统创建应用程序时，将用到许多相同的用户界面 (UI) 组件，例如解决方案资源管理器和“属性”窗口。 此外，还有一些组件（例如 BizTalk 编辑器）仅当您安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 之后才可用。 虽然可以在任何项目系统中使用这些特定的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] UI 组件，但它们主要是用于构建在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上运行的应用程序。  

 虽然 BizTalk 项目系统使用的许多菜单和菜单命令与其他 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目系统中的相同，但在使用 BizTalk 项目系统时，还会有一些新的、不可用的、扩展的或受限制的命令。 本主题介绍了在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中可用的各种菜单，以及它们与 BizTalk 项目系统进行交互的方式。  

> [!NOTE]
>  以下主题重点介绍了与 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中操作不同的菜单和菜单项。  

## <a name="file-menu"></a>“文件”菜单  
 大部分**文件**菜单命令的工作方式与针对其他 BizTalk 项目的相同[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目。 但某些命令在使用 BizTalk 项目时不受支持或不可用。 例如，**打印**使用管道时不支持命令。  

## <a name="view-menu"></a>“视图”菜单  
 下表列出了 BizTalk 项目系统窗口、 工具栏和工具箱可从**视图**菜单。  


|   子菜单名称    |  子菜单名称（如果适用）   |                                                                                                                                                                               Description                                                                                                                                                                               |
|-------------------|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                   |                                 |                                                                                                                                                                                                                                                                                                                                                                         |
| **其他 Windows** |     **业务流程视图**      | 通过“业务流程视图”窗口，可以添加、删除和检查业务流程参数、端口及端口类型、消息及多部分消息类型、相关集及相关类型、角色链接及角色链接类型、作用域以及业务流程属性。 **注意：** 此窗口都仅可在打开的业务流程。 |
| **其他 Windows** |      **表达式编辑器**      |                                                                             “表达式编辑器”窗口是带有 IntelliSense 功能的标准 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 文本编辑器，通过该窗口，可以输入复杂的表达式。                                                                             |
|    **工具箱**    | **BizTalk 管道组件** |                                                                                             列出了可拖至管道设计图面上的管道组件。 只能向可用的活动管道添加管道组件。                                                                                              |
|    **工具箱**    |   **BizTalk 业务流程**    |                                                                                                                                   列出了可拖至业务流程设计图面上的业务流程形状。                                                                                                                                   |
|    **工具箱**    |       **BizTalk 映射器**        |                                                                                                                           列出了可拖至映射网格图面上的 functoid。 这些 functoid 按功能进行分组。                                                                                                                           |
|   **工具栏**    |       **BizTalk 编辑器**        |                                                                                                 一种可视工具，用于简化创建 XML 格式和非 XML 格式的结构化文档架构的过程，此类架构使用 XML 架构定义语言 (XSD) 指定。                                                                                                 |
|   **工具栏**    |       **BizTalk 映射器**        |                                                     一种图形化用户界面工具，用于简化指定 XML 文档转换的过程，该过程基于 BizTalk 编辑器所创建的两个架构，生成可扩展样式表语言转换 (XSLT) 样式表作为编译输出。                                                     |

## <a name="project-menu"></a>“项目”菜单  
 下表列出了一些命令上**项目**菜单。  


|           子菜单名称            |                                                                                                                                                           Description                                                                                                                                                           |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         **添加引用**         |                                                                                                                      使用此菜单项可以引用其他项目、其他 .NET 项目或 COM 项目。                                                                                                                      |
|     **添加服务引用**     |                                                                              使用此菜单项可以添加 WCF 服务引用。 此外使用此项可以通过单击添加 Web 引用**高级**上**添加服务引用**对话框。                                                                               |
|      **添加生成的项**      |                                                                                                                    可以使用此菜单项来添加产生的适配器或计划文件，或使用 WCF 服务。                                                                                                                    |
| **添加适配器服务引用** | 使用此菜单项可浏览（和搜索）元数据并使用所选操作和/或类型生成 .NET CLR 代理类。 **注意：** 该项显示在 BizTalk 菜单仅当至少一个适配器 (随[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]) 在计算机上安装。 |
| **添加使用适配器引用** |       使用此菜单项可浏览（和搜索）来自适配器的元数据，然后为所选操作生成 XML 架构。 **注意：** 该项显示在 BizTalk 菜单仅当至少一个适配器 (随[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]) 在计算机上安装。       |

 有关添加 Web 引用为 BizTalk Web services 的信息，请参阅[添加 Web 引用](../core/adding-web-references.md)。  

## <a name="build-menu"></a>“生成”菜单  
 **生成**菜单包含生成命令。 它还包含要运行的命令**Configuration Manager**设置生成和部署配置选项。 若要部署的项目，右键单击解决方案资源管理器中的项目，然后单击**部署**命令。 只有在您开发应用程序或具有简单方案时，才应当使用此部署方法。 此方法部署执行**不**跟踪版本，因此可以很容易地覆盖以前版本的程序集。 在开发阶段或测试阶段重用相同的版本很有用，但在生产环境中却并非如此。 有关部署的信息，请参阅[了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)。  

 若要向 BizTalk 管理数据库添加 BizTalk 项目，请运行程序集部署向导。 有关程序集部署向导的详细信息，请参阅[如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。  

> [!NOTE]
>  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 包含 Dotfuscator 将采用编译的程序集并将它模糊处理，在以尽力保护知识产权中重命名符号和其他标识符的版本。 不能部署通过此工具运行的程序集。  

## <a name="debug-menu"></a>“调试”菜单  
 BizTalk 项目系统支持**调试**菜单命令。 有关中的调试信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[调试业务流程](../core/debugging-orchestrations.md)。  

## <a name="biztalk-menu"></a>“BizTalk”菜单  
 在处理项目时**BizTalk**打开 BizTalk 编辑器或 BizTalk 映射器或 BizTalk 业务流程设计器时显示菜单。 换句话说，就是当您尝试编辑计划或映射或业务流程时，会出现 BizTalk 菜单。  

> [!NOTE]
>  尽管您可以从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的其他项目系统中访问业务流程设计器、BizTalk 编辑器和 BizTalk 映射器，但这些 BizTalk 工具的行为可能无法预测。 您应在 BizTalk 项目的上下文中使用业务流程设计器、BizTalk 编辑器和 BizTalk 映射器。  

## <a name="help-menu"></a>“帮助”菜单  
 下表列出了一些命令上**帮助**菜单上的相关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  


|            菜单命令            |                                                                                                                                                                             Description                                                                                                                                                                             |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          **动态帮助**          |                                                                                                                                此菜单命令可以打开**动态帮助**根据任务动态生成主题的选项卡。                                                                                                                                |
|            **目录**            | 此菜单命令可以打开**内容**选项卡上，并显示所有已安装的帮助集合。 若要查看目录，必须已安装了 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 产品文档和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 产品文档。 |
| **有关 Microsoft BizTalk Server** |                                                                           此菜单命令可以打开**有关 Microsoft BizTalk Server**对话框。 此对话框显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]产品信息。                                                                           |
|             **Index**              |                                                                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助文档不能通过在此版本中的索引访问。                                                                                                    |
|             **搜索**             |   有关没有筛选器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助在此版本中，但如果您选择的文档 **（无筛选器）** 中**筛选**下拉列表中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助文档可供搜索。    |

## <a name="property-pages"></a>属性页  
 使用项目设计器中的属性页可以配置 BizTalk 项目的程序集项目属性和部署属性。  

### <a name="procedures"></a>过程  

##### <a name="to-configure-assembly-project-properties"></a>配置程序集项目属性  

1. 在解决方案资源管理器中，选择项目。  

2. 上**项目**菜单上，单击**属性**激活项目设计器。  

3. 单击**应用程序**选项卡。  

4. 单击**程序集信息**并更新所需的程序集属性。  

   > [!NOTE]
   >  使用**签名**选项卡来指定程序集密钥文件位置，如果将证书用于上运行的应用程序在项目设计器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

##### <a name="to-configure-deployment-properties"></a>配置部署属性  

1.  选择要为其配置部署属性的项目。  

2.  上**项目**菜单上，单击**属性**激活项目设计器。  

3.  单击**部署**选项卡，然后更新部署属性。  

## <a name="see-also"></a>请参阅  
 [开发人员工具](../core/developer-tools.md)