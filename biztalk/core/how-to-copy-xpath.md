---
title: "如何复制 XPath |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 404599d4-0fb3-4c7c-91e6-1295d9d0965e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb282c5c32d8da62a9da6d7a9c900c798e44eee7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-copy-xpath"></a>如何复制 XPath
XML 架构定义 (XSD) 语言提供了在 BizTalk Server 中定义的消息架构的基本语法。 尽管 BizTalk 映射器中的树视图使用了特定于 BizTalk 的记录和字段节点（在其他节点类型中）的图形化层次结构，并且每个树视图都具有自己的属性集，但此类层次结构将作为 XSD 进行构造和保存。  
  
 在映射很复杂并且跨越多个网格页的情况下，可能很难找到架构节点的父节点。 此时可使用 XSD 路径。 您可以使用 XSD 路径获取有关架构节点的深度信息。 此外，可以在其他网格页中重新使用此路径来标识关系。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-copy-the-xsd-path-xpath"></a>复制 XSD 路径 (XPath) 的步骤  
  
1.  右键单击架构节点为其想 XSD 路径，并依次**复制 XPath**。  
  
2.  打开文本编辑器。 在“编辑” 菜单上，单击“粘贴”。 现在，您可以看到 XSD 路径。  
  
    > [!NOTE]
    >  或者，可以按 Ctrl + V 将路径粘贴到文本编辑器中。  
  
     以下代码显示了所选架构节点的 XSD 路径。  
  
    ```  
    /*[local-name()='<Schema>']/*[local-name()='Shipment']/*[local-name()='DataCollection']  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [在 BizTalk 映射程序中使用增强的功能](../core/using-enhanced-features-in-biztalk-mapper.md)   
 [如何替换架构](../core/how-to-replace-schemas.md)   
 [如何展开和折叠架构树](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)