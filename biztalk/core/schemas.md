---
title: "架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, schema types
- deploying, schemas
- schemas
- schemas, about schemas
- property schemas
- envelope schemas
- schemas, deploying
- XML schemas
- flat file schemas
ms.assetid: aea772bd-e7ab-448e-ba82-e7c8f38087db
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 696c79a30bb58cd91536c19c97db54d6159762b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schemas"></a>架构
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 XML 架构定义 (XSD) 语言定义的所有消息处理，并作为消息结构的这些定义是指结构*架构*。 除少数情况外，结构化消息是所有应用程序的核心。 这些结构化消息可以采用任何形式（大型或小型），并面向一系列众多的后端系统和数据存储。 创建和使用结构化消息的系统通常使用不同的格式。 结构化消息的两种最常用的格式为 XML 和平面文件。  
  
 BizTalk Server 支持以下四种类型的架构：  
  
-   XML 架构。 XML 架构用于定义 XML 实例消息类的结构。 由于此类架构使用 XML 架构定义 (XSD) 语言来定义 XML 实例消息的结构，并且 XSD 也专门用于此目的，因此这类架构以一种简便方式使用 XSD。 有关 XML 架构的详细信息，请参阅[XML 架构](../core/xml-schemas.md)。  
  
-   平面文件架构。 平面文件架构用于定义使用平面文件格式的实例消息类的结构，可以是分隔格式或位置格式，或者是两种格式的组合。 因为 XSD 的本机语义功能不适应所有定义的平面文件实例消息结构的要求，如可能用于不同的记录和平面文件中的字段的分隔符的各种类型-BizTalk Server 使用 XSD 的批注功能来存储在 XSD 架构中的此额外信息。 BizTalk Server 定义了一组丰富的特定批注标记，可用于存储所需的所有其他信息。 有关平面文件架构的详细信息，请参阅[平面文件架构](../core/flat-file-schemas.md)。  
  
-   信封架构。 信封架构是一种 XML 架构类型。 信封架构用于定义 XML 信封的结构，以用于将一个或多个 XML 业务文档包装到单个 XML 实例消息中。 在将 XML 架构定义为信封架构时，根据是否在信封架构中定义了多个根记录，可能需要其他属性设置。 有关信封架构的详细信息，请参阅[信封架构](../core/envelope-schemas.md)。  
  
-   属性架构。 属性架构要结合 BizTalk Server 中存在的用于属性升级的两种机制之一来使用。 *属性提升*是将特定值从实例消息中的深层复制到的消息上下文的过程。 这样，各种 BizTalk Server 组件可以更容易地从消息上下文访问这些值。 这些组件使用这些值来执行诸如消息路由之类的各种操作。 您也可以按其他方向复制升级的属性值，例如，在实例消息发送到其目标之前，将其从更易于访问的消息上下文复制回实例消息的深层。 属性架构，即 BizTalk 架构的简单版本发挥着作用过程中复制的实例消息和消息上下文之间的来回提升的属性。 有关属性架构的详细信息，请参阅[属性架构](../core/property-schemas.md)。  
  
## <a name="schema-deployment"></a>架构部署  
 所部署的架构有多种不同类型，例如消息架构、属性架构和信封架构。 由于每种架构都是不同的，因此，架构在部署后的处理方式也存在细微差异。 本部分介绍了所有架构的共同点，并对不同类型的架构之间的差异进行了说明。  
  
 在部署架构时，管理数据库将存储架构内容。 对于同一目标命名空间，可以部署多个架构。 BizTalk Server 显式指向管道设计器中在运行时使用的架构。 如果使用默认管道，或者未在管道设计器中指定架构，并且部署了同一架构的多个版本，则 BizTalk Server 将确定要使用的架构。 在这种情况下，它将与最新版本相关联的架构-具有最高的版本编号 — 程序集部署使用该架构。  
  
 如果删除部署架构的程序集的最新版本，则与该程序集的上一版本关联的架构将成为活动架构。  
  
 如果部署的架构具有相同的目标命名空间，则必须在自定义设计的用户管道中引用架构。 这样可以为消息引擎提供附加信息以便加载正确的架构。  
  
 例如，在创建 Web Services 架构的多个版本时，将会使用重复的目标命名空间。  
  
## <a name="see-also"></a>另请参阅  
 [创建使用 BizTalk 编辑器的架构](../core/creating-schemas-using-biztalk-editor.md)   
 [BizTalk 表示形式架构](../core/biztalk-representation-of-schemas.md)   
 [项目](../core/artifacts.md)