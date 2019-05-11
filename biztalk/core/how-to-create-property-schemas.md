---
title: 如何创建属性架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24086dea-62b8-4ef6-8af8-eb4ab7c3c018
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fcab4ad4370fe68558fe1ca47de13f9a896c5a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339376"
---
# <a name="how-to-create-property-schemas"></a>如何创建属性架构
如果选择将字段升级为属性字段，您需要首先定义属性架构。 此属性架构指定从定义与属性架构相关联的架构的实例消息中的字段可以升级到这些字段的非结构化的的集合。  
  
> [!IMPORTANT]
>  不要复制或编辑现有属性架构来创建新的架构。 属性架构包含特定于架构的内部数据。  
  
> [!NOTE]
>  不需要创建用于升级可分辨的字段的属性架构。  
  
### <a name="to-create-a-property-schema"></a>若要创建属性架构  
  
1.  在中**解决方案资源管理器**，右键单击 BizTalk 项目，依次指向**添加**，然后单击**新项**。  
  
2.  在中**添加新项**对话框中**模板**部分中，单击**属性架构**。  
  
3.  在中**名称**框中，键入架构的名称，然后单击**添加**。  
  
     此时会打开新的属性架构，并且其中已包含**Field 元素**名为 Property1 节点。  
  
4.  在架构树中，右键单击**Field 元素**节点中，单击**重命名**，在架构中，键入第一个属性的描述性名称，然后按 ENTER。  
  
5.  设置**数据类型**和其他相关属性，根据需要，为**Field 元素**属性窗口中的节点。  
  
6.  如果你想要插入**Field 元素**节点的其他属性，右键单击\<架构\>节点中，单击**插入 Schema 节点**，然后单击**子字段元素**，然后重复步骤 4 和 5。 根据需要创建组所需的重复**Field 元素**节点到你想要升级实例消息中的值。  
  
## <a name="see-also"></a>请参阅  
 [管理项目中的架构](../core/managing-schemas-within-projects.md)