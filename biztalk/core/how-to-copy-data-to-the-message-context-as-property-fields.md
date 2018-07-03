---
title: 如何将数据复制到消息上下文为属性字段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fdfe475-d9b4-4cf9-898f-dbd7e719c27c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97c0440360a064eda7b6177967c2a48d992c1b9e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975878"
---
# <a name="how-to-copy-data-to-the-message-context-as-property-fields"></a>如何将数据复制到消息上下文为属性字段
您可以将升级属性作为**属性字段**方法与将属性升级为大致相同**可分辨字段**，并且还可以使用**快速升级**功能设为简化过程。  
  
 您可以选择**属性字段**通过升级**可分辨字段**出于以下原因升级：  
  
- 想要提升的值是小于 255 个字符限制，适用范围**属性字段**。  
  
- 需要可以在业务流程之外访问升级的值，例如在管道或端口中。  
  
  本主题提供有关将属性升级为的分步说明**属性字段**在这两种方式。  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-promote-properties-dialog-box"></a>使用“升级属性”对话框将属性升级为属性字段  
  
1.  如果需要，创建相应的属性架构，以便将属性升级到该架构中。 创建属性架构的分步说明，请参阅[创建属性架构](../core/how-to-create-property-schemas.md)。  
  
    > [!NOTE]
    >  此步骤可能不需要如果您已经创建属性架构并插入适当**Field 元素**为的子节点的节点**架构**节点。  
  
2.  在 BizTalk 编辑器中，打开你想要升级一个或多个属性的架构，然后选择 （第一个） **Field 元素**， **Field 特性**，或**记录**节点你想要将提升为**属性字段**。  
  
    > [!NOTE]
    >  仅可以升级**记录**节点，如果它们已配置为仅包含简单内容通过让其**内容类型**属性设置为**SimpleContent**。  
  
3.  右键单击所选的节点，单击**Promote**，然后单击**显示升级**。  
  
     **升级属性**对话框将打开与所选的节点显示为对话框的左侧的架构树中已选中。  
  
4.  在中**升级属性**对话框中，选择**属性字段**选项卡。  
  
5.  确认你想要将属性升级到其中的属性架构中存在**属性架构列表**属性字段选项卡中。如果存在，请跳到步骤 8。  
  
6.  在中**属性架构列表**部分中，单击**文件夹**图标。 **BizTalk 类型选取器**对话框随即出现。  
  
7.  在中**BizTalk 类型选取器**对话框框中，导航到相应的属性架构 （即您可能已在步骤 1 中创建的），选择该架构，然后单击**确定**。  
  
    > [!NOTE]
    >  （可选） 你可以通过更改在相应的字符串与属性架构关联的命名空间前缀**前缀**列字段。  
  
8.  与要升级在左侧和右侧的架构树中仍然处于选中状态的节点**升级属性**对话框中，单击**添加**。  
  
     如果允许，选定的节点添加到末尾**属性字段列表**上**属性字段**选项卡。如果不允许，消息框将提供说明。 如果不允许，**添加**按钮未启用。  
  
9. 双击**属性**刚添加到行的列单元格**属性字段列表**，然后在下拉列表中，选择**属性架构**和对应**Field 元素**要在其中升级所选的节点的节点。 下拉列表值具有窗体 X:Y，其中 X 是属性架构中的命名空间前缀**属性架构列表**，，Y 是节点名称**Field 元素**该属性架构中的节点。  
  
     下拉列表中的默认值是第一个属性架构 **（Field 元素）** 节点尚未升级，按字母顺序排列所有相关属性架构。 此节点一般不会是要将给定架构节点升级到的属性架构节点。  
  
10. 您可以选择升级的其他节点在架构树中的对话框中，单击左侧**添加**，然后执行每次选择后步骤 9。  
  
11. 完成后，单击**确定**。  
  
     现已选定要升级的节点**属性字段**并关联与特定**Field 元素**属性架构中的节点。  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-quick-promotion-command"></a>使用“快速升级”命令将属性升级为属性字段  
  
1.  在 BizTalk 编辑器中，打开你想要升级一个或多个属性的架构，然后选择 （第一个） **Field 元素**， **Field 特性**，或**记录**节点你想要将提升为**属性字段**。  
  
    > [!NOTE]
    >  仅可以升级**记录**节点，如果它们已配置为仅包含简单内容通过让其**内容类型**属性设置为**SimpleContent**。  
  
2.  右键单击所选的节点，单击**Promote**，然后单击**快速升级**。  
  
     如果默认属性定义的架构，通过**默认属性架构名**上的属性**属性页**相关架构不存在，则必须单击**确定**在确认对话框中创建的默认属性架构并将其配置相应**字段元素**节点以允许属性升级。  
  
> [!NOTE]
>  可以查看和管理使用升级的属性**快速升级**通过打开功能**升级属性**对话框中，然后单击**属性字段**选项卡。有关分步说明，用于打开**升级属性**对话框中，请参阅[打开升级属性对话框](../core/how-to-open-the-promote-properties-dialog-box.md)。  
  
## <a name="see-also"></a>请参阅  
 [升级属性](../core/promoting-properties.md)   
 [如何创建属性架构](../core/how-to-create-property-schemas.md)   
 [使用消息内容控制消息处理的方法](../core/ways-to-use-message-content-to-control-message-processing.md)