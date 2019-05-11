---
title: 如何复制 XPath |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 404599d4-0fb3-4c7c-91e6-1295d9d0965e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bf9a8da90f264abb0953592abf16dc0e157fcb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385603"
---
# <a name="how-to-copy-xpath"></a>如何复制 XPath
XML 架构定义 (XSD) 语言提供了 BizTalk Server 中定义的消息架构的基本语法。 尽管 BizTalk 映射器中的树视图使用特定于 BizTalk 的图形化层次结构的记录和字段节点 （在其他类型的节点），每个都具有其自己的属性集，此类层次结构构造和保存为 XSD。  
  
 在映射很复杂并且跨越多个网格页的情况下，很难找到架构节点的父节点。 此处使用的是将 XSD 路径。 可以使用 XSD 路径获取信息架构节点的深度。 此外，您可以重复使用此路径在另一个网格页中以标识此关系。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-copy-the-xsd-path-xpath"></a>复制 XSD 路径 (XPath)  
  
1.  右键单击架构节点为其希望的 XSD 路径，然后依次**复制 XPath**。  
  
2.  打开文本编辑器。 在“编辑” 菜单上，单击“粘贴”。 现在可以看到 XSD 路径。  
  
    > [!NOTE]
    >  此外，您可以按 CTRL + V 将路径粘贴到文本编辑器中。  
  
     下面的代码显示了所选的架构节点的 XSD 路径。  
  
    ```  
    /*[local-name()='<Schema>']/*[local-name()='Shipment']/*[local-name()='DataCollection']  
    ```  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射器中的增强的功能](../core/using-enhanced-features-in-biztalk-mapper.md)   
 [如何替换架构](../core/how-to-replace-schemas.md)   
 [如何展开和折叠架构树](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)