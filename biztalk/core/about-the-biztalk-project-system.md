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
ms.openlocfilehash: 43bfc47725defe70c11d0d839fb7985b91403c91
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019884"
---
# <a name="about-the-biztalk-project-system"></a>关于 BizTalk 项目系统
使用 BizTalk 项目系统可创建部分或全部 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序或业务解决方案。 这些解决方案的核心元素是 BizTalk 项目，它是可在部署程序集之前构建并生成到该程序集中的项（例如架构、业务流程、Web 消息类型、类、管道、映射和引用）的集合。  
  
 相对简单的业务解决方案可能包括生成到单个程序集中的单个 BizTalk 项目。 如果业务解决方案比较复杂（例如，你的业务解决方案集成了许多不同的系统和进程），则适当的 BizTalk 解决方案可能具有许多根据多个 BizTalk 项目生成并部署到多个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机的程序集。  
  
> [!IMPORTANT]
>  不能在程序集名称中使用逗号。  
  
 在创建 BizTalk 项目时，通常包括以下列表中的一个或多个文件类型。 在创建解决方案时，这些文件类型扮演着特定的角色，并且 BizTalk 项目系统还为每个文件类型提供了相应的图形设计工具。  
  
- **业务流程。** 业务流程表示业务程序的工作流。 使用业务流程设计器可设计业务流程。 有关业务流程设计器的详细信息，请参阅[业务流程使用业务流程设计器创建](../core/creating-orchestrations-using-orchestration-designer.md)。  
  
- **架构。** 架构描述了 XML 文档的结构。 架构在组织内的应用程序之间或贸易合作伙伴之间交换信息。 BizTalk 编辑器简化了定义架构的过程。 有关 BizTalk 编辑器的详细信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。  
  
- **映射。** 映射可将数据从一种格式转换为另一种格式。 使用 BizTalk 映射器，可并排展示源架构和目标架构，你还可以定义不同消息的数据元素之间的转换。 有关 BizTalk 映射器的详细信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。  
  
- **管道。** 管道执行各种操作，以便为进一步处理传入或传出消息作好准备。 使用管道设计器，你可以实施诸如加密、解密、压缩、重新格式化和验证之类的操作。 有关管道设计器的详细信息，请参阅[管道使用管道设计器创建](../core/creating-pipelines-using-pipeline-designer.md)。  
  
  BizTalk 项目与 Team Foundation Server (TFS) 兼容。 有关设计的详细信息，开发和部署 BizTalk Server 解决方案结合 TFS，请参阅[开发集成解决方案使用 BizTalk Server 和 Team Foundation Server](http://www.microsoft.com/downloads/details.aspx?FamilyID=ed7bd0ee-1385-4041-8f2a-354594ee88f3&DisplayLang=en)。  
  
> [!IMPORTANT]
>  TFS Build 公布了一个名为“MSBuild Platform”的属性，该属性可以有 3 个值 –“Auto”、“x86”和“x64”。 若要确保成功生成，必须将以上属性的值设置为 x86。  
  
 BizTalk 项目可以与 Visual Studio 中的其他项目同时存在。 与 Visual Studio 中的所有项目系统一样，BizTalk 项目也可以包括其他文件（例如 ASP.NET 页），并且可以引用已创建的其他项目和程序集。 有关 BizTalk 项目模板的详细信息，请参阅[BizTalk Server 项目模板](../core/biztalk-server-project-templates.md)。 有关创建 BizTalk 项目的详细信息，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。  
  
> [!WARNING]
>  你或许能够从可在 Visual Studio 中使用的其他项目系统访问 BizTalk 设计工具，但这些工具的行为可能无法预测。 应只在 BizTalk 项目的上下文中使用业务流程设计器、管道设计器、BizTalk 编辑器以及 BizTalk 映射器。  
  
## <a name="see-also"></a>请参阅  
 [创建业务流程使用业务流程设计器](../core/creating-orchestrations-using-orchestration-designer.md)   
 [使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)   
 [使用 BizTalk 映射器创建映射](../core/creating-maps-using-biztalk-mapper.md)   
 [使用管道设计器创建管道](../core/creating-pipelines-using-pipeline-designer.md)   
 [开发人员工具](../core/developer-tools.md)