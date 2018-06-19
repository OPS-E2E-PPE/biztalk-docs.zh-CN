---
title: RetractByType |Microsoft 文档
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
ms.openlocfilehash: da8cd4581007ad2bd93ed66ebce4f5de6378280c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268733"
---
# <a name="retractbytype"></a>RetractByType
**RetractByType**函数将收回在工作内存中，指定类型的所有实例，而**收回**函数将都收回仅对特定类型的特定项目。 以下各段介绍如何**RetractByType**函数适用于不同类型的实体。  
  
## <a name="net-objects"></a>.NET 对象  
 从工作内存中取消给定类类型的所有对象。 你只需类将从.NET 类事实窗格拖到**RetractByType**函数。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 取消所有实例。 这意味着所有**TypedXmlDocument**具有相同的 s **DocumentType.Selector**收回。 你应将相应的节点从 XML 架构事实窗格到**RetractByType**函数。 与一致**收回**函数，如果你执行**RetractByType**的文档根节点上，不只将所有**TypedXmlDocuments**与该断言**DocumentType**收回，但所有子**TypedXmlDocuments** (**XmlNode**树层次结构中的 s) 与这些父**TypedXmlDocuments**也将被取消。  
  
## <a name="typeddatatable-and-dataconnection"></a>TypedDataTable 和 DataConnection  
 **收回**和**RetractByType**相等，则两个**TypedDataTable**和**该组**。 因为**DataSetName.DataTableName**是唯一的标识符对于这两种类型，只有一个实例在引擎中的任何时刻中没有时间。 与**收回**，拖动到表**RetractByType**函数。  
  
## <a name="see-also"></a>另请参阅  
 [引擎控制功能](../core/engine-control-functions.md)