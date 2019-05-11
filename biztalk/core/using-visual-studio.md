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
ms.openlocfilehash: 556cb515e77853a076e6ab9557b3fc68e21fbded
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396743"
---
# <a name="using-visual-studio"></a>使用 Visual Studio
在 BizTalk 项目系统中，您可以使用许多中 Microsoft 提供的工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，以及专门用于创建在 Microsoft 运行的应用程序的工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 本主题介绍了一些可用于创建运行的应用程序的通用过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

 使用 BizTalk 项目系统时，您使用许多相同的用户界面 (UI) 组件，如解决方案资源管理器和属性窗口来创建你的应用程序。 此外，还有一些组件，例如 BizTalk 编辑器中，仅在安装后可用的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 虽然您可以使用这些特定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]任何项目系统 UI 组件，它们特别是使您能够生成运行的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

 虽然 BizTalk 项目系统使用的许多相同的菜单和菜单命令与其他[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目系统，一些命令是新的、 不可用，扩展，或受限制时使用 BizTalk 项目系统。 本主题介绍中可用的各种菜单[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]以及它们与 BizTalk 项目系统的交互。  

> [!NOTE]
>  以下主题重点显示的菜单和菜单项的行为不同于[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  

## <a name="file-menu"></a>文件菜单  
 大部分**文件**菜单命令的工作方式与针对其他 BizTalk 项目的相同[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目。 使用 BizTalk 项目时，某些命令都是不受支持或不可用。 例如，**打印**使用管道时不支持命令。  

## <a name="view-menu"></a>“视图”菜单  
 下表列出了 BizTalk 项目系统窗口、 工具栏和工具箱可从**视图**菜单。  


|   子菜单名称    |  子菜单名称 （如果适用）   |                                                                                                                                                                               Description                                                                                                                                                                               |
|-------------------|---------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                   |                                 |                                                                                                                                                                                                                                                                                                                                                                         |
| **其他 Windows** |     **业务流程视图**      | 业务流程视图是可用的窗口，可用于添加、 删除和检查业务流程参数、 端口和端口类型、 消息和多部分消息类型、 相关集和相关类型、 角色链接和角色链接类型、 作用域和业务流程属性。 **注意：** 此窗口才可从打开的业务流程。 |
| **其他 Windows** |      **表达式编辑器**      |                                                                             表达式编辑器是窗口，是一种标准[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]具有 IntelliSense，可用于输入复杂的表达式的文本编辑器。                                                                             |
|    **Toolbox**    | **BizTalk 管道组件** |                                                                                             这是一系列可拖至管道设计图面上的管道组件。 只能向可用活动管道添加管道组件。                                                                                              |
|    **Toolbox**    |   **BizTalk 业务流程**    |                                                                                                                                   这是一系列可拖至业务流程设计图面上的业务流程形状。                                                                                                                                   |
|    **Toolbox**    |       **BizTalk Mapper**        |                                                                                                                           这是 functoid 的一系列可拖至映射网格图面上。 这些 functoid 按功能分组。                                                                                                                           |
|   **工具栏**    |       **BizTalk Editor**        |                                                                                                 一种可视化工具，可简化创建 XML 架构定义语言 (XSD) 中指定的结构化的文档架构对 XML 和非 XML 格式的过程。                                                                                                 |
|   **工具栏**    |       **BizTalk Mapper**        |                                                     一个图形用户界面工具，可简化指定 XML 文档转换，根据两个架构创建与 BizTalk 编辑器中，生成可扩展样式表语言转换 (XSLT) 样式表作为已编译输出的过程。                                                     |

## <a name="project-menu"></a>“项目”菜单  
 下表列出了一些命令上**项目**菜单。  


|           子菜单名称            |                                                                                                                                                           Description                                                                                                                                                           |
|-----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         **添加引用**         |                                                                                                                      使用此菜单项以引用其他项目、 其他.NET 项目或 COM 项目。                                                                                                                      |
|     **添加服务引用**     |                                                                              使用此菜单项可以添加 WCF 服务引用。 此外使用此项可以通过单击添加 Web 引用**高级**上**添加服务引用**对话框。                                                                               |
|      **添加生成的项**      |                                                                                                                    若要添加生成的适配器或架构文件或使用 WCF 服务，请使用此菜单项。                                                                                                                    |
| **添加适配器服务引用** | 使用此菜单项浏览 （和搜索） 元数据并生成使用所选的操作和/或类型的.NET CLR 代理类。 **注意：** 此项显示在 BizTalk 菜单仅当至少一个适配器 (随[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]) 在计算机上安装。 |
| **添加使用适配器引用** |       使用此菜单项浏览 （和搜索） 元数据从适配器，然后为所选操作生成的 XML 架构。 **注意：** 此项显示在 BizTalk 菜单仅当至少一个适配器 (随[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]) 在计算机上安装。       |

 有关添加 Web 引用为 BizTalk Web services 的信息，请参阅[添加 Web 引用](../core/adding-web-references.md)。  

## <a name="build-menu"></a>生成菜单  
 **生成**菜单包含生成命令。 它还包含要运行的命令**Configuration Manager**设置生成和部署配置选项。 若要部署的项目，右键单击解决方案资源管理器中的项目，然后单击**部署**命令。 仅在开发应用程序时，或者你有一个简单的方案，应使用这种部署方法。 此方法部署执行**不**跟踪版本，因此可以很容易地覆盖以前版本的程序集。 重用相同的版本可在开发或测试阶段，但不是在生产环境。 有关部署的信息，请参阅[了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)。  

 若要将 BizTalk 项目添加到 BizTalk 管理数据库，运行程序集部署向导。 有关程序集部署向导的详细信息，请参阅[如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。  

> [!NOTE]
>  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 包含 Dotfuscator 将采用编译的程序集并将它模糊处理，在以尽力保护知识产权中重命名符号和其他标识符的版本。 不能部署通过此工具运行的程序集。  

## <a name="debug-menu"></a>调试菜单  
 BizTalk 项目系统支持**调试**菜单命令。 有关中的调试信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[调试业务流程](../core/debugging-orchestrations.md)。  

## <a name="biztalk-menu"></a>BizTalk 菜单  
 在处理项目时**BizTalk**打开 BizTalk 编辑器或 BizTalk 映射器或 BizTalk 业务流程设计器时显示菜单。 换而言之，当你尝试编辑的架构或映射或业务流程时，会出现 BizTalk 菜单。  

> [!NOTE]
>  您可能能够从其他项目系统中访问业务流程设计器、 BizTalk 编辑器和 BizTalk 映射器[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]; 但是，这些 BizTalk 工具的行为可能无法预测。 BizTalk 项目的上下文中，应使用业务流程设计器、 BizTalk 编辑器和 BizTalk 映射器。  

## <a name="help-menu"></a>帮助菜单  
 下表列出了一些命令上**帮助**菜单上的相关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  


|            菜单命令            |                                                                                                                                                                             Description                                                                                                                                                                             |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          **动态帮助**          |                                                                                                                                此菜单命令可以打开**动态帮助**根据任务动态生成主题的选项卡。                                                                                                                                |
|            **目录**            | 此菜单命令可以打开**内容**选项卡上，并显示所有已安装的帮助集合。 必须安装 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]产品文档和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装查看内容的产品文档。 |
| **About Microsoft BizTalk Server** |                                                                           此菜单命令可以打开**有关 Microsoft BizTalk Server**对话框。 此对话框显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]产品信息。                                                                           |
|             **Index**              |                                                                                                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助文档不能通过在此版本中的索引访问。                                                                                                    |
|             **搜索**             |   有关没有筛选器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助在此版本中，但如果您选择的文档 **（无筛选器）** 中**筛选**下拉列表中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助文档可供搜索。    |

## <a name="property-pages"></a>属性页  
 在项目设计器中使用的属性页，为您的 BizTalk 项目配置程序集项目属性和部署属性。  

### <a name="procedures"></a>过程  

##### <a name="to-configure-assembly-project-properties"></a>若要配置程序集项目属性  

1. 在解决方案资源管理器中，选择项目。  

2. 上**项目**菜单上，单击**属性**激活项目设计器。  

3. 单击**应用程序**选项卡。  

4. 单击**程序集信息**并更新所需的程序集属性。  

   > [!NOTE]
   >  使用**签名**选项卡来指定程序集密钥文件位置，如果将证书用于上运行的应用程序在项目设计器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

##### <a name="to-configure-deployment-properties"></a>配置部署属性  

1.  选择你想要配置部署属性的项目。  

2.  上**项目**菜单上，单击**属性**激活项目设计器。  

3.  单击**部署**选项卡，然后更新部署属性。  

## <a name="see-also"></a>请参阅  
 [开发人员工具](../core/developer-tools.md)