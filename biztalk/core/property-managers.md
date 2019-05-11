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
# <a name="property-managers"></a><span data-ttu-id="ddb61-102">属性管理器</span><span class="sxs-lookup"><span data-stu-id="ddb61-102">Property Managers</span></span>
<span data-ttu-id="ddb61-103">属性管理器允许元素扩展，以自定义属性 （通常为 XSD 批注），并与关联架构，以及扩展属性窗口以包括自定义属性的 XSD 表示形式中的属性扩展插件。</span><span class="sxs-lookup"><span data-stu-id="ddb61-103">Property Managers allow an extension to add custom properties (generally as XSD annotations) to elements and attributes in the XSD representation of the schema, as well as extending the Properties window to include the custom properties associated with the extension.</span></span>  
  
 <span data-ttu-id="ddb61-104">属性管理器是一个对象，实现**IPropertyManager**接口，通过调用获取对其的引用**IExtension.GetPropertyManager**，并传递**ITreeNode**对象作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="ddb61-104">A Property Manager is an object that implements the **IPropertyManager** interface, a reference to which is obtained by calling **IExtension.GetPropertyManager**, and passing an **ITreeNode** object as the input parameter.</span></span> <span data-ttu-id="ddb61-105">该扩展通常提供一个**IPropertyManager**每个对象**ITreeNode**对象。</span><span class="sxs-lookup"><span data-stu-id="ddb61-105">Typically the extension provides one **IPropertyManager** object for each **ITreeNode** object.</span></span> <span data-ttu-id="ddb61-106">属性管理器负责为此，自定义属性的集合**ITreeNode**对象。</span><span class="sxs-lookup"><span data-stu-id="ddb61-106">The Property Manager is responsible for the collection of custom properties for that **ITreeNode** object.</span></span>  
  
 <span data-ttu-id="ddb61-107">自定义属性由**System.ComponentModel.PropertyDescriptor**对象，可以从返回的集合中获取**IPropertyManager.GetProperties**方法。</span><span class="sxs-lookup"><span data-stu-id="ddb61-107">A custom property is represented by a **System.ComponentModel.PropertyDescriptor** object, which can be obtained from the collection returned by the **IPropertyManager.GetProperties** method.</span></span>  
  
 <span data-ttu-id="ddb61-108">使用**PropertyDescriptor**对象表示与扩展关联的自定义属性有利于与 Microsoft 集成[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口。</span><span class="sxs-lookup"><span data-stu-id="ddb61-108">Using **PropertyDescriptor** objects to represent the custom properties associated with the extension facilitates integration with the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span> <span data-ttu-id="ddb61-109">当**PropertyDescriptor**对象，可以很容易为 BizTalk 编辑器将扩展的自定义属性集成到已集成到属性窗口的标准节点属性集。</span><span class="sxs-lookup"><span data-stu-id="ddb61-109">When **PropertyDescriptor** objects are used, it is easy for BizTalk Editor to integrate the custom properties of the extension into the set of standard node properties already being integrated into the Properties window.</span></span> <span data-ttu-id="ddb61-110">从获取自定义属性信息，例如显示名称、 显示值、 属性控件的类型、 属性说明和属性类别**PropertyDescriptor**对象。</span><span class="sxs-lookup"><span data-stu-id="ddb61-110">Custom property information such as the display name, the display value, the type of property control, the property description, and the property category is obtained from the **PropertyDescriptor** object.</span></span>  
  
 <span data-ttu-id="ddb61-111">自定义属性存储的架构的 XSD 表示形式作为批注元素中与架构树中的相关节点对应的元素中的某个元素的属性。</span><span class="sxs-lookup"><span data-stu-id="ddb61-111">Custom properties are stored in the XSD representation of the schema as attributes of an element within the annotation element within the element corresponding to the relevant node in the schema tree.</span></span> <span data-ttu-id="ddb61-112">架构树节点的每个自定义属性可以是常规元素的属性或或者，都可以具有其自身关联的元素。</span><span class="sxs-lookup"><span data-stu-id="ddb61-112">Each custom property of a schema tree node can be an attribute of a common element, or alternatively, each can have its own associated element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb61-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddb61-113">See Also</span></span>  
 [<span data-ttu-id="ddb61-114">扩展 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="ddb61-114">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)