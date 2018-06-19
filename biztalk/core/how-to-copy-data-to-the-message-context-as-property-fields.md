---
title: 如何将数据复制到作为属性字段的消息上下文 |Microsoft 文档
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
ms.openlocfilehash: 18242f30f32974cc32ab5d39a4a9c63650f27ffa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249981"
---
# <a name="how-to-copy-data-to-the-message-context-as-property-fields"></a>如何将数据复制到作为属性字段的消息上下文
你可以将提升属性作为**属性字段**方式与将提升属性作为得多相同**可分辨字段**，，也可以使用**快速升级**到功能优化过程。  
  
 你可以选择**属性字段**通过升级**可分辨字段**出于以下原因升级：  
  
-   想要提升的值是短于适用于的 255 个字符限制**属性字段**。  
  
-   需要可以在业务流程之外访问升级的值，例如在管道或端口中。  
  
 本主题提供有关将提升为属性的分步说明**属性字段**在这两个通过以下方式。  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-promote-properties-dialog-box"></a>使用“升级属性”对话框将属性升级为属性字段  
  
1.  如果需要，创建相应的属性架构，以便将属性升级到该架构中。 用于创建属性架构的分步说明，请参阅[创建属性架构](../core/how-to-create-property-schemas.md)。  
  
    > [!NOTE]
    >  此步骤可能不是必要如果你已经创建属性架构并插入相应**Field 元素**作为的子节点的节点**架构**节点。  
  
2.  在 BizTalk 编辑器中，打开你想要升级一个或多个属性的架构，然后选择 （第一个） **Field 元素**，**字段特性**，或**记录**节点你想要将提升为**属性字段**。  
  
    > [!NOTE]
    >  你可以仅将提升**记录**节点如果它们配置为简单内容仅包含通过让其**内容类型**属性设置为**SimpleContent**。  
  
3.  右键单击所选的节点，单击**Promote**，然后单击**显示提升**。  
  
     **升级属性**对话框随即打开与所选的节点显示的所选对话框左侧的架构树中。  
  
4.  在**升级属性**对话框中，选择**属性字段**选项卡。  
  
5.  确认要以升级属性的属性架构中存在**属性架构列表**属性字段选项卡中。如果存在，请跳到步骤 8。  
  
6.  在**属性架构列表**部分中，单击**文件夹**图标。 **BizTalk 类型选取器**对话框随即出现。  
  
7.  在**BizTalk 类型选取器**对话框框中，导航到相应的属性架构 （即你可能已在步骤 1 中创建的），选择该架构，然后单击**确定**。  
  
    > [!NOTE]
    >  （可选） 可以更改通过更改在相应的字符串属性架构与关联的命名空间前缀**前缀**列字段。  
  
8.  与节点可升级的左侧的架构树中仍选定**升级属性**对话框中，单击**添加**。  
  
     如果允许，所选的节点添加到末尾**属性字段列表**上**属性字段**选项卡。如果不允许，消息框将提供说明。 如果不允许，**添加**按钮未启用。  
  
9. 双击**属性**刚刚添加到的行的列单元格**属性字段列表**，然后在下拉列表中，选择**属性架构**和对应**Field 元素**到想要提升所选的节点的节点。 下拉列表值具有窗体 X:Y，其中 X 是中的属性架构的命名空间前缀**属性架构列表**，Y 是节点名称和**Field 元素**该属性架构中的节点。  
  
     下拉列表中的默认值是第一个属性架构 **（Field 元素）** 尚未升级，节点按字母顺序在所有相关属性架构。 此节点一般不会是要将给定架构节点升级到的属性架构节点。  
  
10. 你可以在对话框中，单击左侧架构树中选择更多节点升级**添加**和每个所选内容后再执行步骤 9。  
  
11. 完成后，单击**确定**。  
  
     选择进行升级的节点现**属性字段**并关联与特定**Field 元素**属性架构中的节点。  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-quick-promotion-command"></a>使用“快速升级”命令将属性升级为属性字段  
  
1.  在 BizTalk 编辑器中，打开你想要升级一个或多个属性的架构，然后选择 （第一个） **Field 元素**，**字段特性**，或**记录**节点你想要将提升为**属性字段**。  
  
    > [!NOTE]
    >  你可以仅将提升**记录**节点如果它们配置为简单内容仅包含通过让其**内容类型**属性设置为**SimpleContent**。  
  
2.  右键单击所选的节点，单击**Promote**，然后单击**快速升级**。  
  
     如果默认属性定义的架构，通过**默认属性架构名称**属性**属性页**对于相关的架构，不存在，必须单击**确定**在确认对话框中创建的默认属性架构并将其配置与相应**Field 元素**节点以适应属性提升。  
  
> [!NOTE]
>  你可以查看和管理使用升级属性**快速提升**功能通过打开**升级属性**对话框中，然后单击**属性字段**选项卡。有关分步说明打开**升级属性**对话框中，请参阅[打开提升的属性对话框中](../core/how-to-open-the-promote-properties-dialog-box.md)。  
  
## <a name="see-also"></a>另请参阅  
 [提升属性](../core/promoting-properties.md)   
 [如何创建属性架构](../core/how-to-create-property-schemas.md)   
 [使用与控件消息处理的消息内容的方法](../core/ways-to-use-message-content-to-control-message-processing.md)