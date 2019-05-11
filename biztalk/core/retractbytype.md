---
title: RetractByType | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RetractByType function [Business Rules Engine], TypedXMLDocument
- RetractByType function [Business Rules Engine]
- RetractByType function [Business Rules Engine], .NET objects
- RetractByType function [Business Rules Engine], TypedData table
- RetractByType function [Business Rules Engine], DataConnection
- .NET objects
ms.assetid: e8867553-ee3c-46be-84cd-d5373eaf3337
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 460684c52f00df531eb73f397fdc187829522be2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309510"
---
# <a name="retractbytype"></a>RetractByType
**RetractByType**函数可以取消工作内存中指定类型的所有实例而**Retract**函数可以都取消某一类型的仅对特定项目。 以下各段介绍如何**RetractByType**函数适用于不同类型的实体。  
  
## <a name="net-objects"></a>.NET 对象  
 从工作内存中取消给定的类类型的所有对象。 从.NET 类事实窗格到只需将该类**RetractByType**函数。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 取消所有实例。 这意味着，所有**TypedXmlDocument**具有相同的 s **DocumentType.Selector**中取消。 应将相应的节点从到的 XML 架构事实窗格拖**RetractByType**函数。 与一致**Retract**函数，如果您执行**RetractByType**对文档根节点，不仅将所有**TypedXmlDocuments**添加与该**DocumentType**收回，但所有子**TypedXmlDocuments** (**XmlNode**树层次结构中) 与这些父关联**TypedXmlDocuments**还将取消。  
  
## <a name="typeddatatable-and-dataconnection"></a>TypedDataTable 和 DataConnection  
 **收回**并**RetractByType**是两个等效**TypedDataTable**并**DataConnection**。 因为**DataSetName.DataTableName**是唯一的标识符的两种类型，只有一个实例引擎中任何位置中没有时间。 如同**Retract**，将拖到表**RetractByType**函数。  
  
## <a name="see-also"></a>请参阅  
 [引擎控制函数](../core/engine-control-functions.md)