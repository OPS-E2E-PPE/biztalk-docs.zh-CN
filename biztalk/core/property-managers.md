---
title: 属性管理器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 823352a0-e397-464a-a163-1dbf8feea8d7
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a8a96ce643c7b7268ea01f5f0313ab9225eeb63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398469"
---
# <a name="property-managers"></a>属性管理器
属性管理器允许元素扩展，以自定义属性 （通常为 XSD 批注），并与关联架构，以及扩展属性窗口以包括自定义属性的 XSD 表示形式中的属性扩展插件。  
  
 属性管理器是一个对象，实现**IPropertyManager**接口，通过调用获取对其的引用**IExtension.GetPropertyManager**，并传递**ITreeNode**对象作为输入参数。 该扩展通常提供一个**IPropertyManager**每个对象**ITreeNode**对象。 属性管理器负责为此，自定义属性的集合**ITreeNode**对象。  
  
 自定义属性由**System.ComponentModel.PropertyDescriptor**对象，可以从返回的集合中获取**IPropertyManager.GetProperties**方法。  
  
 使用**PropertyDescriptor**对象表示与扩展关联的自定义属性有利于与 Microsoft 集成[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口。 当**PropertyDescriptor**对象，可以很容易为 BizTalk 编辑器将扩展的自定义属性集成到已集成到属性窗口的标准节点属性集。 从获取自定义属性信息，例如显示名称、 显示值、 属性控件的类型、 属性说明和属性类别**PropertyDescriptor**对象。  
  
 自定义属性存储的架构的 XSD 表示形式作为批注元素中与架构树中的相关节点对应的元素中的某个元素的属性。 架构树节点的每个自定义属性可以是常规元素的属性或或者，都可以具有其自身关联的元素。  
  
## <a name="see-also"></a>请参阅  
 [扩展 BizTalk 编辑器](../core/extending-biztalk-editor.md)