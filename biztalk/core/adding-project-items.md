---
title: "添加项目项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects, orchestrations
- projects, schemas
- projects, files
- projects, pipelines
- projects, maps
ms.assetid: d1b922d5-8ece-4e1a-a390-e6ae1222665a
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfb6aaa0a00488c1181d440e0ce7e5777ef4477d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adding-project-items"></a>添加项目项
在 BizTalk 项目系统的上下文中，项目项是指配置项，例如映射或架构。 BizTalk 应用程序可能包含一个或多个业务流程、架构、映射和管道。  
  
> [!NOTE]
>  向项目添加项时，请不要在名称中使用句点 (.)，因为句点是 .NET 命名空间的分隔符。 如果在项名称中使用句点，则项的“类型名”将包含下划线 (_) 而不是句点。  
  
> [!NOTE]
>  当向一个文件夹中，添加架构、 映射或管道**完全限定名称**属性自动生成，并且包括命名空间和类型。  
  
## <a name="orchestrations"></a>业务流程  
 业务流程是以 XLANG/s 语言表示的业务程序的一种表示形式。 XLANG/秒是基于 XML 的语言 (XLANG) 在 Microsoft 中引入的更新变体[!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]。 XLANG/s 可用于补充现有过程语言，如 Microsoft [!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)] 和 Microsoft [!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)]。  
  
 您可以使用业务流程设计器创建要在 BizTalk 项目中包括的业务流程。 在业务流程设计器中创建的所有业务流程均具有 .odx 文件扩展名。  
  
## <a name="schemas"></a>架构  
 架构是文档或消息结构的定义。 由于架构与结构中的记录和字段有关，因此它包含属性信息。 如果需要，架构可以包含多个子架构。  
  
 可以使用 BizTalk 编辑器导入、编辑或创建架构。 然后，可以在 BizTalk 映射器中使用所创建的架构生成映射。 通过使用 BizTalk 编辑器保存的所有架构均具有 .xsd 文件扩展名。  
  
 有关架构和 BizTalk 编辑器的详细信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。  
  
## <a name="maps"></a>地图  
 映射是定义一个架构中的记录和字段与另一个架构中的记录和字段之间的对应关系的 XML 文件。 可以根据行业标准、非行业标准（如内部标准或行业惯例）或现有文件创建映射。 当希望将接收或发送的数据从一种格式转换成另一种格式时，可以创建映射。 可以使用 BizTalk 映射器创建包含在 BizTalk 项目中的映射。 在 BizTalk 映射器中保存的所有映射均具有 .btm 文件扩展名。 BizTalk 映射程序有关的详细信息，请参阅[创建地图使用 BizTalk 映射程序](../core/creating-maps-using-biztalk-mapper.md)。  
  
## <a name="pipelines"></a>管道  
 可以使用管道设计器来创建接收管道和发送管道。 管道是一个软件基础结构，用于定义并链接一个或多个阶段，处理消息接收或发送[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 管道以特定的顺序实现各个阶段，并包含多种功能，如编码或解码、组装或拆装以及加密或解密。  
  
 BizTalk 项目中包含的默认管道引用只能处理 XML 文档。 若要处理平面文件、EDI 文档或其他文件类型，必须根据需要创建新的管道。 使用管道设计器创建的所有管道均具有 .btp 扩展名。 有关管道和管道设计器的详细信息，请参阅[创建管道使用管道设计器](../core/creating-pipelines-using-pipeline-designer.md)。  
  
## <a name="valid-files-for-biztalk-projects"></a>BizTalk 项目的有效文件  
 在使用 BizTalk 项目时，可以包含多种不同的文件，例如 HTML 文件、XML 文件、接收管道文件和架构文件。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 发行版之前，当您将 BizTalk 项目内置于程序集中时，将只在程序集中包括以下文件类型：业务流程、架构、映射和管道。 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 发行版时，程序集可以包含受 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 构建系统支持的任何对象。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk 项目](../core/working-with-biztalk-projects.md)