---
title: "如何创建属性架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24086dea-62b8-4ef6-8af8-eb4ab7c3c018
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 426e98e491ec71a7e430ff6886f5f9820c4b87fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-property-schemas"></a>如何创建属性架构
如果选择将字段升级为属性字段，则需要首先定义属性架构。 此属性架构指定了一个非结构化的字段集合，您可以将与属性架构相关联的架构所定义的实例消息中的字段升级到该字段集合中。  
  
> [!IMPORTANT]
>  不要复制或编辑现有属性架构来创建新的架构。 属性架构包含特定于架构的内部数据。  
  
> [!NOTE]
>  无需创建属性架构即可升级可分辨字段。  
  
### <a name="to-create-a-property-schema"></a>创建属性架构  
  
1.  在**解决方案资源管理器**，右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。  
  
2.  在**添加新项**对话框中，在**模板**部分中，单击**属性架构**。  
  
3.  在**名称**框中，为架构中，键入一个名称，然后单击**添加**。  
  
     新的属性架构将打开，并且它已包含**Field 元素**名为 Property1 节点。  
  
4.  在架构树中，右键单击**Field 元素**节点，单击**重命名**，在架构中，键入第一个属性的描述性名称，然后按 enter 键。  
  
5.  设置**数据类型**和其他相关的属性，根据需要为**Field 元素**属性窗口中的节点。  
  
6.  如果你想要插入**Field 元素**对于其他属性，节点右键单击\<架构 > 节点，单击**插入架构节点**，然后单击**子 Field 元素**，然后重复步骤 4 和 5。 根据需要创建组所需的重复**Field 元素**你想要从实例消息升级值到其中的节点。  
  
## <a name="see-also"></a>另请参阅  
 [管理架构在项目中](../core/managing-schemas-within-projects.md)