---
title: 如何对节点名称字符进行编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6462856b-7a52-40c9-9aff-c0579130eec9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 387f80f54952b1f2bdae877c806b0a130c5bf1b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387458"
---
# <a name="how-node-name-characters-get-encoded"></a>如何对节点名称字符进行编码
如果使用节点名称中不允许的字符，BizTalk 编辑器会发出提示，询问您是否要继续不允许的字符或编码字符 (**确定**或**取消**)。 如果继续，每个不允许的字符编码，如下所示：  
  
- 不允许的字符编码为"*xDDDD\\*"其中"DDDD"是 4 位十六进制 Unicode 字符的表示形式。 例如，空格字符 (0x0020) 编码为"*x0020\\*"。  
  
- 如果两个或多个相邻不允许的字符进行编码，则它们之间使用单个下划线字符。 例如，将三个空格编码为"*x0020_x0020_x0020\\*"而非"*x0020\__x0020\__x0020\\*"。  
  
> [!NOTE]
>  您可以禁用提示输入节点名称编码通过设置**显示编码警告对话框**属性设置为**False**中的 BizTalk 编辑器文件夹**选项**对话框中，可在上找到**工具**菜单中，或通过选择**不再显示此对话框，在将来**节点名称编码对话框中的复选框。 有关此对话框中选项的详细信息，请参阅[管理架构树视图](../core/how-to-manage-the-schema-tree-view.md)。  
  
 在架构树视图在 BizTalk 编辑器中显示通过使用您键入的字符的节点名称。 BizTalk 映射器还显示你键入而不是编码版本的字符。 在 XSD 视图的 BizTalk 编辑器中，和 XSD 文件本身中，则使用编码的节点名称。 例如，如果将名称节点采购订单，它将显示为采购订单在 BizTalk 编辑器和 BizTalk 映射器中的架构树中。 在 XSD 视图的 BizTalk 编辑器中，对应的元素节点，第一次插入时，将按如下所示。  
  
```  
<element name="Purchase_x0020_Order" type="xs:string />  
  
```  
  
## <a name="see-also"></a>请参阅  
 [节点名称属性](../core/node-name-property.md)   
 [已编码的节点名称字符](../core/which-node-name-characters-get-encoded.md)