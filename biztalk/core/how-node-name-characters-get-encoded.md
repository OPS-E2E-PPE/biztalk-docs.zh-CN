---
title: "节点名称字符获取编码方式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6462856b-7a52-40c9-9aff-c0579130eec9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d2c9410e56b2b50a32ec73ce5f49ae59909f59a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-node-name-characters-get-encoded"></a>如何对节点名称字符进行编码
如果使用节点名称中不允许的字符时，BizTalk 编辑器会发出提示，询问你是否要继续不允许的字符或编码的字符 (**确定**或**取消**)。 如果继续，每个不允许的字符编码，如下所示：  
  
-   不允许的字符编码为"_xDDDD\_""DDDD"所在 4 位十六进制 Unicode 字符的表示形式。 例如，空格字符 (0x0020) 编码为"_x0020\_"。  
  
-   如果两个或多个相邻不允许的字符进行编码，它们之间使用单个下划线字符。 例如，三个空格被编码为"_x0020_x0020_x0020\_"而非"_x0020\__x0020\__x0020\_"。  
  
> [!NOTE]
>  你可以禁用提示输入通过设置的节点名称编码**显示编码警告对话框**属性**False** BizTalk 编辑器文件夹中的**选项**对话框中，可在上找到**工具**菜单上，或通过选择**将来不显示此对话框**编码对话框中的节点名称中的复选框。 有关此对话框中选项的详细信息，请参阅[管理架构树视图](../core/how-to-manage-the-schema-tree-view.md)。  
  
 BizTalk 编辑器中的架构树视图显示通过使用您键入的字符的节点名称。 BizTalk 映射程序还会显示您键入而不是编码版本的字符。 在 XSD 视图的 BizTalk 编辑器中，以及 XSD 文件本身中，则使用编码的节点名称。 例如，如果名称节点采购订单时，它将显示为采购订单 BizTalk 编辑器和 BizTalk 映射程序中的架构树中。 在 XSD 视图的 BizTalk 编辑器中，相应的元素节点，首先插入时，将，如下所示。  
  
```  
<element name="Purchase_x0020_Order" type="xs:string />  
  
```  
  
## <a name="see-also"></a>另请参阅  
 [节点名称属性](../core/node-name-property.md)   
 [节点名称字符获取编码](../core/which-node-name-characters-get-encoded.md)