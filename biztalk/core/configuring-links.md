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
ms.openlocfilehash: 9926a7bdd890f75935014a79ff3994230c2378c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015694"
---
# <a name="configuring-links"></a>配置链接

## <a name="overview"></a>概述
在显示的网格页中选择链接后，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口中将显示链接具有的属性。 有关与链接关联的属性的参考信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 

## <a name="source-target-and-label"></a>源、 目标和标签  
 以下属性配置映射中的链接：  
  
- **源链接**。 您使用**源链接**属性可以配置将用于构造输出实例消息的输入的实例消息中的数据的性质。 默认并且最常用的选择是使用输入实例消息中的元素或属性的值。 也可能进行其他选择，包括使用输入实例消息中的元素或属性的名称。 有关此属性及其可用选项的详细信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
- **目标链接**。 您使用**目标链接**属性可以配置 BizTalk 映射器匹配节点层次结构级别的方式。 默认情况下，创建输出实例消息时将平展源架构层次。 也可以选择保留这些层次，并且从上到下或从下到上匹配链接。 有关此属性及其可用选项的详细信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
- **标签**。 您使用**标签**属性来创建比默认情况下使用的 XPath 值更具可读性的链接名称。 在将链接用作表驱动循环的输入时，配置此属性尤其有帮助。 有关此属性及其可用选项，以及表驱动循环的详细信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 另请参阅[表循环和表提取程序 Functoid](../core/table-looping-and-table-extractor-functoids.md)分别。  
  
## <a name="see-also"></a>请参阅  
  [如何编辑链接属性](../core/how-to-edit-link-properties.md)