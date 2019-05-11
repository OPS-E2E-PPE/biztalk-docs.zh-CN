---
title: 添加项目项 |Microsoft Docs
description: 添加到 BizTalk Server 项目在 Visual Studio 中的业务流程、 架构、 映射和管道
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1b922d5-8ece-4e1a-a390-e6ae1222665a
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b0fc88bcf2f843e7d22b47a69ccae1b7b3fcd66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360911"
---
# <a name="add-project-items"></a>添加项目项
在 BizTalk 项目系统的上下文中，项目项是指配置的项，例如映射或架构。 BizTalk 应用程序可能包含一个或多个业务流程、 架构、 映射和管道。  
  
> [!NOTE]
>  当将某个项添加到项目中时，不句点 （.） 在名称中使用因为句点是.NET 命名空间的分隔符。 如果项名称中使用句点，则项的类型名称将包含下划线 (_) 而不是一段。  
  
> [!NOTE]
>  将架构、 映射或管道添加到一个文件夹中，当**完全限定的名称**属性自动生成并包含命名空间和类型。  
  
## <a name="orchestrations"></a>业务流程  
 业务流程是以 XLANG/s 语言表示的业务流程的表示形式。 XLANG/s 可用于补充现有过程语言，如 Microsoft[!INCLUDE[btsVCSharp](../includes/btsvcsharp-md.md)]和 Microsoft [!INCLUDE[btsVBNet](../includes/btsvbnet-md.md)]。  
  
 业务流程设计器可用于创建你想要在 BizTalk 项目中包含的业务流程。 在业务流程设计器中创建的所有业务流程具有.odx 文件扩展名。  
  
## <a name="schemas"></a>架构  
 架构是文档或消息结构的定义。 因为它涉及到的记录和结构中的字段，它包含属性信息。 如果适用，架构可以包含多个子架构。  
  
 可以使用 BizTalk 编辑器导入、 编辑或创建架构。 然后，可以使用创建 BizTalk 映射器中生成映射的架构。 使用 BizTalk 编辑器中保存的所有架构都具有.xsd 文件扩展名。  
  
 有关架构和 BizTalk 编辑器的详细信息，请参阅[使用 BizTalk 编辑器创建架构](../core/creating-schemas-using-biztalk-editor.md)。  
  
## <a name="maps"></a>地图  
 地图是另一个架构中定义的记录和一个架构中的字段和记录和字段之间的对应关系的 XML 文件。 创建基于行业标准、 非行业标准 （如内部标准或遗留问题） 或现有文件的映射。 当你想要将数据接收或发送从一种格式之间转换时，您可以创建映射。 BizTalk 映射器可用于创建 BizTalk 项目中包含的映射。 在 BizTalk 映射器中保存的所有映射都具有.btm 文件扩展名。 有关 BizTalk 映射器的详细信息，请参阅[创建映射使用 BizTalk 映射器](../core/creating-maps-using-biztalk-mapper.md)。  
  
## <a name="pipelines"></a>管道  
 可以使用管道设计器创建接收和发送管道。 管道是软件基础结构，用于定义和链接来处理消息接收或发送的 BizTalk Server 的一个或多个阶段。 管道按特定顺序实现各个阶段，并包括诸如编码或解码、 组装或拆装以及加密或解密。  
  
 在 BizTalk 项目中包含的默认管道引用可以只能处理 XML 文档。 如果你想要处理平面文件、 EDI 文档或其他文件类型，则必须创建新的管道，根据需要。 使用管道设计器创建的所有管道均都具有.btp 扩展名。 有关管道和管道设计器的详细信息，请参阅[管道使用管道设计器创建](../core/creating-pipelines-using-pipeline-designer.md)。  
  
## <a name="valid-files-for-biztalk-projects"></a>BizTalk 项目的有效文件  
 与 BizTalk 项目时，可以包含许多不同的文件，例如 HTML 文件、 XML 文件、 接收管道文件和架构文件。 与 BizTalk Server 程序集可以包含由 Visual Studio 生成系统支持的任何对象。  
  
## <a name="see-also"></a>请参阅  
 [处理 BizTalk 项目](../core/working-with-biztalk-projects.md)