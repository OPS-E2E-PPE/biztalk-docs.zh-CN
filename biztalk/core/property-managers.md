---
title: 属性管理器 |Microsoft 文档
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
ms.openlocfilehash: 6aff8fc39612ed79e6e9602ed39874d014bb4a11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269101"
---
# <a name="property-managers"></a><span data-ttu-id="f296d-102">属性管理器</span><span class="sxs-lookup"><span data-stu-id="f296d-102">Property Managers</span></span>
<span data-ttu-id="f296d-103">属性管理器允许扩展向架构的 XSD 表示形式中的元素和特性添加自定义属性（通常为 XSD 批注），以及扩展“属性”窗口以包括与扩展关联的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="f296d-103">Property Managers allow an extension to add custom properties (generally as XSD annotations) to elements and attributes in the XSD representation of the schema, as well as extending the Properties window to include the custom properties associated with the extension.</span></span>  
  
 <span data-ttu-id="f296d-104">属性管理器是一个对象，实现**IPropertyManager**接口，通过调用获取对其的引用**IExtension.GetPropertyManager**，并传递**ITreeNode**对象作为输入参数。</span><span class="sxs-lookup"><span data-stu-id="f296d-104">A Property Manager is an object that implements the **IPropertyManager** interface, a reference to which is obtained by calling **IExtension.GetPropertyManager**, and passing an **ITreeNode** object as the input parameter.</span></span> <span data-ttu-id="f296d-105">通常扩展提供了一个**IPropertyManager**每个对象**ITreeNode**对象。</span><span class="sxs-lookup"><span data-stu-id="f296d-105">Typically the extension provides one **IPropertyManager** object for each **ITreeNode** object.</span></span> <span data-ttu-id="f296d-106">属性管理器负责该自定义属性的集合**ITreeNode**对象。</span><span class="sxs-lookup"><span data-stu-id="f296d-106">The Property Manager is responsible for the collection of custom properties for that **ITreeNode** object.</span></span>  
  
 <span data-ttu-id="f296d-107">自定义属性都由**System.ComponentModel.PropertyDescriptor**对象，可以从返回的集合中获取**IPropertyManager.GetProperties**方法。</span><span class="sxs-lookup"><span data-stu-id="f296d-107">A custom property is represented by a **System.ComponentModel.PropertyDescriptor** object, which can be obtained from the collection returned by the **IPropertyManager.GetProperties** method.</span></span>  
  
 <span data-ttu-id="f296d-108">使用**PropertyDescriptor**对象来表示与扩展相关联的自定义属性便于与 Microsoft 集成[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口。</span><span class="sxs-lookup"><span data-stu-id="f296d-108">Using **PropertyDescriptor** objects to represent the custom properties associated with the extension facilitates integration with the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span> <span data-ttu-id="f296d-109">当**PropertyDescriptor**使用对象，可以很容易 BizTalk 编辑器将扩展的自定义属性集成到的已集成到属性窗口的标准节点属性集的。</span><span class="sxs-lookup"><span data-stu-id="f296d-109">When **PropertyDescriptor** objects are used, it is easy for BizTalk Editor to integrate the custom properties of the extension into the set of standard node properties already being integrated into the Properties window.</span></span> <span data-ttu-id="f296d-110">从获取自定义属性的信息，例如显示名称、 显示值、 属性控制的类型、 属性说明和属性类别**PropertyDescriptor**对象。</span><span class="sxs-lookup"><span data-stu-id="f296d-110">Custom property information such as the display name, the display value, the type of property control, the property description, and the property category is obtained from the **PropertyDescriptor** object.</span></span>  
  
 <span data-ttu-id="f296d-111">自定义属性存储在架构的 XSD 表示形式中，在与架构树中的相关节点对应的元素中，作为批注元素中的元素特性存储。</span><span class="sxs-lookup"><span data-stu-id="f296d-111">Custom properties are stored in the XSD representation of the schema as attributes of an element within the annotation element within the element corresponding to the relevant node in the schema tree.</span></span> <span data-ttu-id="f296d-112">架构树节点的每个自定义属性都可以是常规元素的特性，此外，每个自定义属性也可以具有自己的关联元素。</span><span class="sxs-lookup"><span data-stu-id="f296d-112">Each custom property of a schema tree node can be an attribute of a common element, or alternatively, each can have its own associated element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f296d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f296d-113">See Also</span></span>  
 [<span data-ttu-id="f296d-114">扩展 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="f296d-114">Extending BizTalk Editor</span></span>](../core/extending-biztalk-editor.md)