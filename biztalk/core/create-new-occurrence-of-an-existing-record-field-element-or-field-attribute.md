---
title: 如何创建现有记录、 Field 元素或字段属性节点的新实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02380f68-056c-47c4-a0d6-61d599a4685d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64f8974de22b7ee99a02d551553cb5e36f31a0d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238173"
---
# <a name="how-to-create-a-new-occurrence-of-an-existing-record-field-element-or-field-attribute-node"></a><span data-ttu-id="20135-102">如何创建现有记录、 Field 元素或字段属性节点的一个新事件</span><span class="sxs-lookup"><span data-stu-id="20135-102">How to Create a New Occurrence of an Existing Record, Field Element, or Field Attribute Node</span></span>
<span data-ttu-id="20135-103">你可以创建现有的新实例**记录**， **Field 元素**，或**字段特性**节点以便到任何实例的后续修改反映到所有实例。</span><span class="sxs-lookup"><span data-stu-id="20135-103">You can create new instances of an existing **Record**, **Field Element**, or **Field Attribute** node such that subsequent modifications to any instance are reflected in all instances.</span></span>  
  
### <a name="to-create-a-new-instance-of-an-existing-record-field-element-or-field-attribute-node"></a><span data-ttu-id="20135-104">创建现有“记录”、“字段元素”或“字段属性”节点的新实例</span><span class="sxs-lookup"><span data-stu-id="20135-104">To create a new instance of an existing Record, Field Element, or Field Attribute node</span></span>  
  
1.  <span data-ttu-id="20135-105">选择原始**记录**， **Field 元素**，或**字段特性**节点，请确保其**基数据类型**属性设置正确，然后在其**数据结构类型**(**记录**节点) 或其**数据类型**(**Field 元素**和**字段特性**节点) 属性，键入一个自定义数据类型名称。</span><span class="sxs-lookup"><span data-stu-id="20135-105">Select the original **Record**, **Field Element**, or **Field Attribute** node, make sure its **Base Data Type** property is set correctly, and then in its **Data Structure Type** (**Record** nodes) or its **Data Type** (**Field Element** and **Field Attribute** nodes) property, type a custom data type name.</span></span>  
  
2.  <span data-ttu-id="20135-106">插入新**记录**， **Field 元素**，或**字段特性**节点和组的自定义数据的以下属性之一键入你在步骤 1 中键入的名称。</span><span class="sxs-lookup"><span data-stu-id="20135-106">Insert the new **Record**, **Field Element**, or **Field Attribute** node and set one of the following properties to the custom data type name you typed in step 1.</span></span>  
  
    -   <span data-ttu-id="20135-107">数据结构类型 (**记录**节点)</span><span class="sxs-lookup"><span data-stu-id="20135-107">Data Structure Type (**Record** nodes)</span></span>  
  
    -   <span data-ttu-id="20135-108">数据类型 (**Field 元素**和**字段特性**节点)</span><span class="sxs-lookup"><span data-stu-id="20135-108">Data Type (**Field Element** and **Field Attribute** nodes)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20135-109">如果新**记录**或**Field 元素**节点是同级的原始节点，和你为新的节点作为原始节点相同的名称，您将看到一个消息框，询问有关重复相同的作用域中的节点具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="20135-109">If a new **Record** or **Field Element** node is a sibling of the original node, and you give the new node the same name as the original node, you will see a message box asking about duplicate nodes in the same scope with the same name.</span></span> <span data-ttu-id="20135-110">单击**是**执行与在步骤 2 中选择的自定义数据类型名称相同的操作。</span><span class="sxs-lookup"><span data-stu-id="20135-110">Clicking **Yes** performs the same action as choosing the custom data type name in step 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20135-111">创建现有的新实例**记录**， **Field 元素**，或**字段特性**节点。</span><span class="sxs-lookup"><span data-stu-id="20135-111">You have created a new instance of the existing **Record**, **Field Element**, or **Field Attribute** node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20135-112">某些属性**记录**， **Field 元素**，或**字段特性**节点实例保持相同 （一个实例的更改是对所有实例的更改），和其他属性可以单独设置每个实例。</span><span class="sxs-lookup"><span data-stu-id="20135-112">Some properties of **Record**, **Field Element**, or **Field Attribute** node instances remain identical (a change to one instance is a change to all instances), and other properties can be set independently for each instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20135-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20135-113">See Also</span></span>  
 [<span data-ttu-id="20135-114">将节点插入到架构</span><span class="sxs-lookup"><span data-stu-id="20135-114">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)