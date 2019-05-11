---
title: 关于 BizTalk 项目系统 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, about projects
- applications, creating
- creating, applications
- creating, business solutions
- business solutions, creating
ms.assetid: 69807e57-356e-451d-b803-4253b891b617
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd431f6b1033f5bb7b51b3dfb690a578b694b3aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362251"
---
# <a name="about-the-biztalk-project-system"></a>关于 BizTalk 项目系统
使用 BizTalk 项目系统可创建部分或全部 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序或业务解决方案。 任何此类解决方案的核心元素是 BizTalk 项目，项，如架构、 业务流程、 Web 消息类型、 类、 管道、 映射和可以构建并生成到部署之前的程序集的引用的集合。  
  
 相对简单的业务解决方案可能包含单个 BizTalk 项目生成到单个程序集。 如果您的业务解决方案比较复杂 — 例如，有许多不同系统和流程集成的解决方案-可能的 BizTalk 解决方案可能具有多个程序集从多个 BizTalk 项目生成并部署到多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。  
  
> [!IMPORTANT]
>  中的程序集名称，不能使用逗号。  
  
 当你创建 BizTalk 项目时，通常可以包含一个或多个文件类型在以下列表中。 这些文件类型扮演特定角色中创建你的解决方案，并且 BizTalk 项目系统提供使用相应的图形设计工具为每个。  
  
- **业务流程。** 业务流程表示业务流程的工作流。 设计业务流程使用业务流程设计器。 有关业务流程设计器的详细信息，请参阅[业务流程使用业务流程设计器创建](../core/creating-orchestrations-using-orchestration-designer.md)。  
  
- **架构。** 架构描述 XML 文档的结构。 架构 exchange 组织内的应用程序之间或贸易合作伙伴之间的信息。 BizTalk 编辑器简化了定义架构的过程。 有关 BizTalk 编辑器的详细信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。  
  
- **映射。** 映射将数据从一种格式之间转换。 BizTalk 映射器展示源架构和目标架构的并排方案，并可以定义不同消息的数据元素之间的转换。 有关 BizTalk 映射器的详细信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。  
  
- **管道。** 管道执行各种操作，准备进行进一步处理传入或传出消息。 管道设计器，可实现诸如加密和解密、 压缩、 重新格式化和验证等操作。 有关管道设计器的详细信息，请参阅[管道使用管道设计器创建](../core/creating-pipelines-using-pipeline-designer.md)。  
  
  BizTalk 项目都 Team Foundation Server (TFS) 兼容。 有关设计的详细信息，开发和部署 BizTalk Server 解决方案结合 TFS，请参阅[开发集成解决方案使用 BizTalk Server 和 Team Foundation Server](http://www.microsoft.com/downloads/details.aspx?FamilyID=ed7bd0ee-1385-4041-8f2a-354594ee88f3&DisplayLang=en)。  
  
> [!IMPORTANT]
>  TFS Build 公布了一个名为"MSBuild Platform"可以具有 3 个值 –"Auto"、"x86"和"x64"的属性。 若要确保成功的生成，上述属性的值必须设置为 x86。  
  
 BizTalk 项目可以与其他项目在 Visual Studio 中共存。 与 Visual Studio 中的所有项目系统的 BizTalk 项目可以包含其他文件，例如 ASP.NET 页，并可以引用其他项目和已创建的程序集。 有关 BizTalk 项目模板的详细信息，请参阅[BizTalk Server 项目模板](../core/biztalk-server-project-templates.md)。 有关创建 BizTalk 项目的详细信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。  
  
> [!WARNING]
>  您可能能够从在 Visual Studio 中，可以使用其他项目系统访问 BizTalk 设计工具，但其行为不可预测。 只在 BizTalk 项目的上下文中使用业务流程设计器、 管道设计器、 BizTalk 编辑器和 BizTalk 映射器。  
  
## <a name="see-also"></a>请参阅  
 [创建业务流程使用业务流程设计器](../core/creating-orchestrations-using-orchestration-designer.md)   
 [使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)   
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)   
 [使用管道设计器创建管道](../core/creating-pipelines-using-pipeline-designer.md)   
 [开发人员工具](../core/developer-tools.md)