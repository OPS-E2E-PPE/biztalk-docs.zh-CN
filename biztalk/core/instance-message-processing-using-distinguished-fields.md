---
title: 实例消息处理使用可分辨字段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b8f3f77-5385-4294-b441-bcb28bdc51b4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db91474677843963dc578ee617ac238df5f13368
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382104"
---
# <a name="instance-message-processing-using-distinguished-fields"></a>实例消息处理使用可分辨字段
将属性提升通过 **可分辨字段** 机制不需要的属性架构创建。 因为所有属性提升，与你使用 **升级属性** 对话框中，这是可访问通过使用 **升级属性** 属性 **架构** 节点在消息架构中，或通过使用 **Promote &#124;显示升级** 命令 **BizTalk** 或快捷菜单。  
  
 在 **升级属性** 对话框框中，确保 **可分辨字段** 在对话框中的右侧选择选项卡。 然后，展开对话框中查找并选择左侧的架构树中节点**Field 元素**节点或**字段属性**你想要将升级为可分辨字段的节点，然后单击**添加**。 有关升级到属性的分步说明**可分辨字段**使用**升级属性**对话框中，请参阅[到 Distinguished 作为消息上下文复制数据字段](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)。  
  
> [!NOTE]
>  你还可以升级**记录**到属性架构，但是只有当中的字段元素节点的节点**内容类型**属性**记录**节点设置为**SimpleContent**。  
  
 若要升级为可分辨字段的属性集中删除节点，选择已升级的属性上**可分辨字段**选项卡，然后单击**删除**。  
  
 时通过使用可分辨的字段机制升级属性，XML 架构定义 (XSD) 语言片断将添加中的批注子元素的根元素。 在以下示例中，片段演示了通过使用可分辨的字段机制升级的两个属性。  
  
```  
<b:properties>  
    <b:property distinguished="true"  
        xpath="/*[local-name()='Record' and namespace-  
         uri()='http://BizTalk_Server_Project1.Schema11']/*[local-  
         name()='test']/*[local-name()='Field1']" />  
    <b:property distinguished="true"  
        xpath="/*[local-name()='Record' and namespace-  
         uri()='http://BizTalk_Server_Project1.Schema11']/*[local-  
         name()='test']/*[local-name()='Field5' and position()='1']" />  
</b:properties>  
```  
  
## <a name="see-also"></a>请参阅  
 [使用消息内容控制消息处理方法](../core/ways-to-use-message-content-to-control-message-processing.md)   
 [如何将数据复制到消息上下文作为可分辨字段](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)