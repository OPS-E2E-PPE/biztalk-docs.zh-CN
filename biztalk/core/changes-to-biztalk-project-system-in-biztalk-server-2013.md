---
title: "在 BizTalk Server 2013 中的 BizTalk 项目系统会变为 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82f0dd18-073c-4cba-aa0d-48076c58f874
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dff1f35955229306bc2f39e0af670f939dec82da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="changes-to-biztalk-project-system-in-biztalk-server-2013"></a>BizTalk Server 2013 中 BizTalk 项目系统的更改
本主题为你提供了对 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 中 BizTalk 项目系统的更改的高级概述。  
  
## <a name="project-properties-are-displayed-in-project-designer-window"></a>项目属性将显示在项目设计器窗口中  
 BizTalk Server 项目的属性现在显示在 Visual Studio 的项目设计器中，而不是“属性”对话框中。 项目设计器提供了一个集中的位置，用于管理项目属性、设置和资源。 项目设计器在 Visual Studio IDE 中显示为单个窗口，这一点与其他设计器（如窗体或类设计器）大致相同，并且包含许多可通过左侧标签访问的页面。 有关详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=190417](http://go.microsoft.com/fwlink/?LinkId=190417)。  
  
## <a name="properties-for-schema-and-map-files-are-displayed-in-properties-window"></a>架构和映射文件的属性显示在“属性”窗口中  
 架构和映射文件，如属性**输入实例 Filename**和**测试映射输入实例**将显示在属性窗口与而不是在单独**属性**对话框。  
  
## <a name="add-web-reference-option-on-projects"></a>在项目上添加“Web 引用”选项  
 **添加 Web 引用**选项不可用，右键单击项目名称时或**引用**在解决方案资源管理器。 你可以通过使用以下步骤将 Web 引用添加到 Web 服务 (.asmx) 中：  
  
1.  右键单击**引用**在项目中，然后单击**添加服务引用**。  
  
2.  在**添加服务引用**对话框中，单击**高级**。  
  
3.  在**服务引用设置**对话框中，单击**添加 Web 引用**。  
  
4.  键入 URL，，然后单击**转**。  
  
5.  单击**添加引用**添加 Web 引用。  
  
    > [!TIP]
    >  添加到 BizTalk 项目，Web 引用后**添加 Web 引用**菜单选项才可用引用、 Web 引用和项目节点上。  
  
 有关添加服务和 Web 引用的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=131577](http://go.microsoft.com/fwlink/?LinkId=131577)。  
  
## <a name="msbuild-integration"></a>MSBUILD 集成  
 Visual Studio 使用 MSBUILD 项目文件格式存储有关管理项目（包括 BizTalk 项目）的生成信息。 有关详细信息，请参阅[与 Visual Studio 的 MSBUILD 集成](../core/msbuild-integration-with-visual-studio.md)。  
  
## <a name="team-foundation-server-integration"></a>Team Foundation Server 集成  
 你可以将 Team Foundation Server 用作 BizTalk 项目的源控制系统。 你可以从解决方案资源管理器窗口本身执行操作，如签入和签出。  
  
## <a name="support-for-unit-testing"></a>对单元测试的支持  
 通过此功能，可以对架构、映射和管道进行单元测试。 有关详细信息，请参阅[使用 BizTalk 服务器项目进行单元测试](../core/unit-testing-with-biztalk-server-projects.md)。  
  
## <a name="debug-map-feature"></a>调试映射功能  
 **调试映射功能**。 你可以通过在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中使用内联 XSLT 调试程序调试映射 (XSLT)。 有关详细信息，请参阅[如何调试地图](../core/how-to-debug-maps.md)。  
  
## <a name="migrating-biztalk-server-projects"></a>迁移 BizTalk Server 项目  
 可以使用 Visual Studio 转换向导，将为早期版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 开发的 Visual Studio 项目迁移到 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 环境。 有关详细信息，请参阅[迁移 BizTalk 服务器项目](../core/migrating-a-biztalk-server-project.md)。  
  
## <a name="release-and-debug-build-types"></a>发布和调试版本类型  
 BizTalk 项目现在有两个生成类型：**版本**和**调试**，哪些替换**开发**和**部署**的更早版本版本。 但是，你仍然可以看到**开发**和**部署**从迁移的项目配置[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]。  
  
## <a name="embedding-tracking-and-debugging-information"></a>嵌入跟踪和调试信息  
 **嵌入跟踪信息**和**生成调试信息**输出配置属性已替换为**定义 TRACE 常量**和**定义 DEBUG 常量**生成选项**生成**项目设计器选项卡。 **BPEL 法规遵从性的代码生成**配置属性将替换为**BPEL 法规遵从性代码生成**项目属性窗口中的属性。  
  
> [!IMPORTANT]
>  Visual Studio 转换向导可以自动将前面提及的设置迁移到新环境中。  
  
## <a name="user-access-control"></a>用户访问控制  
 Visual Studio 不会让你在启了用户访问控制 (UAC) 功能的计算机上部署 BizTalk 项目，除非你使用管理权限运行 Visual Studio。 若要使用管理权限运行 Visual Studio，请单击**启动**，指向**所有程序**，指向**Microsoft Visual Studio**，右键单击**Microsoft Visual Studio\<版本 >**，然后单击**以管理员身份运行**。  
  
## <a name="c-files-in-a-biztalk-project"></a>BizTalk 项目中的 C# 文件  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]允许你与仅灵活打包需求的 BizTalk 项目组合的帮助器类。  但是，不能直接通过使用添加一个新的 C# 文件**添加新项**或**添加新类**菜单选项。  
  
## <a name="generatecsfiles-registry-key-is-obsolete"></a>GenerateCSFiles 注册表项已过时  
 **GenerateCSFiles**注册表项现在已废弃不用。 所有生成的 .cs 文件都显示在解决方案资源管理器窗口中。 你可能需要单击**显示所有文件**解决方案资源管理器窗口以查看与某些 BizTalk 项目关联的.cs 文件中的工具栏项。