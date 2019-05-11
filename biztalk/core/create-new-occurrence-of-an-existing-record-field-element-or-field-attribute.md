---
title: 如何创建现有记录、 字段元素或字段属性节点的新实例 |Microsoft Docs
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
ms.openlocfilehash: c7a4e1992bf10ccd51feb69919ecc17a3c5db323
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390135"
---
# <a name="how-to-create-a-new-occurrence-of-an-existing-record-field-element-or-field-attribute-node"></a><span data-ttu-id="37277-102">如何创建现有记录、 字段元素或字段属性节点的新实例</span><span class="sxs-lookup"><span data-stu-id="37277-102">How to Create a New Occurrence of an Existing Record, Field Element, or Field Attribute Node</span></span>
<span data-ttu-id="37277-103">您可以创建新实例的现有**记录**， **Field 元素**，或**字段属性**节点，这样的任何实例的后续修改反映在所有实例。</span><span class="sxs-lookup"><span data-stu-id="37277-103">You can create new instances of an existing **Record**, **Field Element**, or **Field Attribute** node such that subsequent modifications to any instance are reflected in all instances.</span></span>  
  
### <a name="to-create-a-new-instance-of-an-existing-record-field-element-or-field-attribute-node"></a><span data-ttu-id="37277-104">若要创建的现有记录、 字段元素或字段属性节点的新实例</span><span class="sxs-lookup"><span data-stu-id="37277-104">To create a new instance of an existing Record, Field Element, or Field Attribute node</span></span>  
  
1.  <span data-ttu-id="37277-105">选择原始**记录**， **Field 元素**，或**字段属性**节点，请确保其**Base Data Type**属性设置正确，然后在其**Data Structure Type** (**记录**节点) 或其**数据类型**(**字段元素**和**字段属性**节点) 属性中，键入自定义数据类型名称。</span><span class="sxs-lookup"><span data-stu-id="37277-105">Select the original **Record**, **Field Element**, or **Field Attribute** node, make sure its **Base Data Type** property is set correctly, and then in its **Data Structure Type** (**Record** nodes) or its **Data Type** (**Field Element** and **Field Attribute** nodes) property, type a custom data type name.</span></span>  
  
2.  <span data-ttu-id="37277-106">插入新**记录**， **Field 元素**，或**字段属性**节点和组的自定义数据的以下属性之一键入你在步骤 1 中键入的名称。</span><span class="sxs-lookup"><span data-stu-id="37277-106">Insert the new **Record**, **Field Element**, or **Field Attribute** node and set one of the following properties to the custom data type name you typed in step 1.</span></span>  
  
    -   <span data-ttu-id="37277-107">数据结构类型 (**记录**节点)</span><span class="sxs-lookup"><span data-stu-id="37277-107">Data Structure Type (**Record** nodes)</span></span>  
  
    -   <span data-ttu-id="37277-108">数据类型 (**Field 元素**并**字段属性**节点)</span><span class="sxs-lookup"><span data-stu-id="37277-108">Data Type (**Field Element** and **Field Attribute** nodes)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="37277-109">如果新**记录**或**Field 元素**节点是原始节点的同级并为新节点指定与原始节点相同的名称，会看到一个消息框询问有关同一作用域中的重复节点具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="37277-109">If a new **Record** or **Field Element** node is a sibling of the original node, and you give the new node the same name as the original node, you will see a message box asking about duplicate nodes in the same scope with the same name.</span></span> <span data-ttu-id="37277-110">单击**是**执行相同的操作与在步骤 2 中选择的自定义数据类型名称。</span><span class="sxs-lookup"><span data-stu-id="37277-110">Clicking **Yes** performs the same action as choosing the custom data type name in step 2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37277-111">已创建的新实例的现有**记录**， **Field 元素**，或**字段属性**节点。</span><span class="sxs-lookup"><span data-stu-id="37277-111">You have created a new instance of the existing **Record**, **Field Element**, or **Field Attribute** node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37277-112">某些属性**记录**， **Field 元素**，或**字段属性**节点实例保持相同 （对一个实例的更改是对所有实例的更改），和其他每个实例可以单独设置属性。</span><span class="sxs-lookup"><span data-stu-id="37277-112">Some properties of **Record**, **Field Element**, or **Field Attribute** node instances remain identical (a change to one instance is a change to all instances), and other properties can be set independently for each instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37277-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="37277-113">See Also</span></span>  
 [<span data-ttu-id="37277-114">向架构插入节点</span><span class="sxs-lookup"><span data-stu-id="37277-114">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)