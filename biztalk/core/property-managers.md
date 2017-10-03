---
title: "属性管理器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 823352a0-e397-464a-a163-1dbf8feea8d7
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aff8fc39612ed79e6e9602ed39874d014bb4a11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="property-managers"></a>属性管理器
属性管理器允许扩展向架构的 XSD 表示形式中的元素和特性添加自定义属性（通常为 XSD 批注），以及扩展“属性”窗口以包括与扩展关联的自定义属性。  
  
 属性管理器是一个对象，实现**IPropertyManager**接口，通过调用获取对其的引用**IExtension.GetPropertyManager**，并传递**ITreeNode**对象作为输入参数。 通常扩展提供了一个**IPropertyManager**每个对象**ITreeNode**对象。 属性管理器负责该自定义属性的集合**ITreeNode**对象。  
  
 自定义属性都由**System.ComponentModel.PropertyDescriptor**对象，可以从返回的集合中获取**IPropertyManager.GetProperties**方法。  
  
 使用**PropertyDescriptor**对象来表示与扩展相关联的自定义属性便于与 Microsoft 集成[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口。 当**PropertyDescriptor**使用对象，可以很容易 BizTalk 编辑器将扩展的自定义属性集成到的已集成到属性窗口的标准节点属性集的。 从获取自定义属性的信息，例如显示名称、 显示值、 属性控制的类型、 属性说明和属性类别**PropertyDescriptor**对象。  
  
 自定义属性存储在架构的 XSD 表示形式中，在与架构树中的相关节点对应的元素中，作为批注元素中的元素特性存储。 架构树节点的每个自定义属性都可以是常规元素的特性，此外，每个自定义属性也可以具有自己的关联元素。  
  
## <a name="see-also"></a>另请参阅  
 [扩展 BizTalk 编辑器](../core/extending-biztalk-editor.md)