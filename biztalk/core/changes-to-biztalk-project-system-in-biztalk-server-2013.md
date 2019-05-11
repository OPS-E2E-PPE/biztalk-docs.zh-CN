---
title: 将更改为 BizTalk Server 2013 中 BizTalk 项目系统 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82f0dd18-073c-4cba-aa0d-48076c58f874
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db58dd7bde1162e9d266201a92422be887bb03d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357540"
---
# <a name="changes-to-biztalk-project-system-in-biztalk-server-2013"></a>在 BizTalk Server 2013 中 BizTalk 项目系统的更改
本主题提供您的更改的高级概述到 BizTalk Server 中的 BizTalk 项目系统。  
  
## <a name="project-properties-are-displayed-in-project-designer-window"></a>项目设计器窗口中显示项目属性  
 BizTalk Server 项目的属性现在显示在项目设计器的 Visual Studio 而不是在属性对话框。 项目设计器提供集中管理项目属性、 设置和资源。 项目设计器为单个窗口在 Visual Studio IDE 中，类似于其他设计器，例如窗体或类设计器，其中包含通过在左侧选项卡访问的页面数。 有关详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=190417 ](http://go.microsoft.com/fwlink/?LinkId=190417)。  
  
## <a name="properties-for-schema-and-map-files-are-displayed-in-properties-window"></a>在属性窗口中将显示属性架构和映射文件  
 属性架构和映射文件，如**输入实例文件名**并**测试映射输入实例**将显示在属性窗口使用而不是在单独**属性**对话框。  
  
## <a name="add-web-reference-option-on-projects"></a>添加 Web 引用的项目选项  
 **添加 Web 引用**右键单击项目名称时，选项不可用或**引用**在解决方案资源管理器。 可以使用以下步骤来添加对 Web 服务 (.asmx) 的 Web 引用：  
  
1. 右键单击**引用**在项目中，然后单击**添加服务引用**。  
  
2. 在中**添加服务引用**对话框中，单击**高级**。  
  
3. 在中**服务引用设置**对话框中，单击**添加 Web 引用**。  
  
4. 键入的 URL，然后依次**转**。  
  
5. 单击**添加引用**添加 Web 引用。  
  
   > [!TIP]
   >  添加对 BizTalk 项目的 Web 引用后**添加 Web 引用**菜单选项才可用引用、 Web 引用和项目节点上。  
  
   有关添加服务和 Web 引用的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=131577 ](http://go.microsoft.com/fwlink/?LinkId=131577)。  
  
## <a name="msbuild-integration"></a>MSBUILD 集成  
 Visual Studio 使用 MSBUILD 项目文件格式来存储有关托管项目包括 BizTalk 项目的生成信息。 有关详细信息，请参阅[与 Visual Studio 的 MSBUILD 集成](../core/msbuild-integration-with-visual-studio.md)。  
  
## <a name="team-foundation-server-integration"></a>Team Foundation Server 集成  
 对于 BizTalk 项目，可以作为源控制系统中使用 Team Foundation Server。 你可以从解决方案资源管理器窗口本身执行操作，如签入和签出。  
  
## <a name="support-for-unit-testing"></a>对单元测试的支持  
 此功能可以对单元测试架构、 映射和管道。 有关详细信息，请参阅[Unit Testing 与 BizTalk Server 项目](../core/unit-testing-with-biztalk-server-projects.md)。  
  
## <a name="debug-map-feature"></a>调试映射功能  
 **调试映射功能**。 您可以通过使用在中的使用内联 XSLT 调试程序调试映射 (XSLT) [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 有关详细信息，请参阅[如何调试映射](../core/how-to-debug-maps.md)。  
  
## <a name="migrating-biztalk-server-projects"></a>迁移 BizTalk Server 项目  
 早期版本开发的 visual Studio 项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将迁移到 BizTalk Server 环境中，通过使用 Visual Studio 转换向导。 有关详细信息，请参阅[迁移 BizTalk Server 项目](../core/migrating-a-biztalk-server-project.md)。  
  
## <a name="release-and-debug-build-types"></a>发布和调试版本类型  
 现在，BizTalk 项目有两种生成类型：**发行**并**调试**，它取代了**开发**并**部署**的早期版本。 但是，您仍然可以看到**开发**并**部署**从迁移的项目配置[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]。  
  
## <a name="embedding-tracking-and-debugging-information"></a>嵌入跟踪和调试信息  
 **嵌入跟踪信息**并**生成调试信息**输出配置属性替换为**定义 TRACE 常量**和**定义 DEBUG 常量**生成选项**生成**项目设计器选项卡。 **BPEL 兼容代码生成**配置属性替换为**BPEL 兼容代码生成**项目属性窗口中的属性。  
  
> [!IMPORTANT]
>  Visual Studio 转换向导已经自动将前面提到的设置迁移到新环境。  
  
## <a name="user-access-control"></a>用户访问控制  
 Visual Studio 不允许您使用的用户访问控制 (UAC) 功能，除非使用管理权限运行 Visual Studio 部署 BizTalk 项目的计算机上。 若要使用管理权限运行 Visual Studio，请单击**启动**，依次指向**所有程序**，指向**Microsoft Visual Studio**，右键单击**Microsoft Visual Studio\<版本\>**，然后单击**以管理员身份运行**。  
  
## <a name="c-files-in-a-biztalk-project"></a>C#BizTalk 项目中的文件  
 BizTalk Server，可将帮助程序类与 BizTalk 项目仅满足灵活包装需求相结合。  但是，不能直接通过添加新的 C# 文件**添加新项**或**添加新的类**菜单选项。  
  
## <a name="generatecsfiles-registry-key-is-obsolete"></a>GenerateCSFiles 注册表项已过时  
 **GenerateCSFiles**注册表项现已过时。 所有生成的.cs 文件将显示在解决方案资源管理器窗口。 可能需要单击**显示所有文件**在解决方案资源管理器窗口以查看与某些 BizTalk 项相关联的.cs 文件中的工具栏项。