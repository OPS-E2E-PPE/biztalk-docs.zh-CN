---
title: 配置链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10050c28-0944-4073-afd2-54cd6c8d79a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb50ad367a8e1f72de0f567aaeb46ea07a933f22
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355317"
---
# <a name="configuring-links"></a>配置链接

## <a name="overview"></a>概述
链接具有的属性中显示的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]时显示的网格页中选择链接属性窗口。 有关与链接关联的属性的参考信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 

## <a name="source-target-and-label"></a>源、 目标和标签  
 以下属性配置映射中的链接：  
  
- **源链接**。 您使用**源链接**属性可以配置将用于构造输出实例消息的输入的实例消息中的数据的性质。 默认值，并且最常用的选择是使用输入的实例消息中的元素或属性值。 其他选择是名称的有可能，包括使用输入的实例消息中的属性的元素。 有关此属性及其可用选项的详细信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
- **目标链接**。 您使用**目标链接**属性可以配置 BizTalk 映射器匹配节点层次结构级别的方式。 默认情况下，创建输出实例消息将平展源架构层次结构。 您还可以选择保留，这些层次匹配链接向下顶部或从下到上。 有关此属性及其可用选项的详细信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
- **标签**。 您使用**标签**属性来创建比默认情况下使用的 XPath 值更具可读性的链接名称。 当作为输入的表驱动循环使用该链接时，配置此属性将非常有用。 有关此属性及其可用选项，以及表驱动循环的详细信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 另请参阅[表循环和表提取程序 Functoid](../core/table-looping-and-table-extractor-functoids.md)分别。  
  
## <a name="see-also"></a>请参阅  
  [如何编辑链接属性](../core/how-to-edit-link-properties.md)