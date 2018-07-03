---
title: 如何插入任何元素或任何属性节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cbfdc04-6c83-4639-82de-169b6f009a2e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bce55126fe800841aef325f22de0afe62e03cec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021072"
---
# <a name="how-to-insert-an-any-element-or-any-attribute-node"></a><span data-ttu-id="6c0ae-102">如何插入任何元素或任何属性节点</span><span class="sxs-lookup"><span data-stu-id="6c0ae-102">How to Insert an Any Element or Any Attribute Node</span></span>
<span data-ttu-id="6c0ae-103">BizTalk 编辑器支持两种类型的任何节点： **Any 元素**并**任何属性**。</span><span class="sxs-lookup"><span data-stu-id="6c0ae-103">BizTalk Editor supports two types of any nodes: **Any Element** and **Any Attribute**.</span></span> <span data-ttu-id="6c0ae-104">使用这些节点，您可以在架构中创建与相应实例消息中的位置对应的位置，您不知道哪些元素或属性会出现在这些位置。</span><span class="sxs-lookup"><span data-stu-id="6c0ae-104">These nodes allow you to create locations within your schema that correspond to locations within the corresponding instance messages where you do not know what elements or attributes will appear.</span></span> <span data-ttu-id="6c0ae-105">有关如何在处理实例消息时解释这些节点的详细信息，请直接参阅 Web 上有关 XML 架构定义 (XSD) 语言的信息。</span><span class="sxs-lookup"><span data-stu-id="6c0ae-105">For detailed information about how these nodes are interpreted when processing instance messages, refer directly to information about the XML Schema definition (XSD) language on the Web.</span></span> <span data-ttu-id="6c0ae-106">此信息的链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="6c0ae-106">For links to this information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  

## <a name="insert-an-any-element-node-or-an-any-attribute-node"></a><span data-ttu-id="6c0ae-107">插入任何元素或任何属性节点</span><span class="sxs-lookup"><span data-stu-id="6c0ae-107">Insert an Any Element node or an Any Attribute node</span></span>  

1.  <span data-ttu-id="6c0ae-108">在架构树视图中，选择**记录**要在其中插入的节点**Any 元素**节点或**任何属性**节点。</span><span class="sxs-lookup"><span data-stu-id="6c0ae-108">In the schema tree view, select the **Record** node into which you want to insert the **Any Element** node or the **Any Attribute** node.</span></span>  

2.  <span data-ttu-id="6c0ae-109">上**BizTalk**菜单，依次指向**插入 Schema 节点**，然后单击**Any 元素**或**任何属性**根据。</span><span class="sxs-lookup"><span data-stu-id="6c0ae-109">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Any Element** or **Any Attribute**, as appropriate.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="6c0ae-110">设置**Process Contents**属性设置为**Lax**有关**Any 元素**或者**任何属性**节点可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="6c0ae-110">Setting the **Process Contents** property to **Lax** for **Any Element** or **Any Attribute** nodes may not work correctly.</span></span> <span data-ttu-id="6c0ae-111">若要通过验证**Any 元素**或**任何属性**节点，将属性设置为**跳过**。</span><span class="sxs-lookup"><span data-stu-id="6c0ae-111">To pass validation on **Any Element** or **Any Attribute** nodes, set the property to **Skip**.</span></span>  <span data-ttu-id="6c0ae-112">此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="6c0ae-112">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
> 
>  <span data-ttu-id="6c0ae-113">若要创建包含的地图**Any 元素**或**任何属性**节点，则必须使用[批量复制](mass-copy-functoid.md)functoid 或[脚本](scripting-functoid.md)functoid （使用内联 XSLT 或内联 XSLT 调用模板） 执行映射，使此类节点，或仅仅不映射这些节点。</span><span class="sxs-lookup"><span data-stu-id="6c0ae-113">To create a map that contains **Any Element** or **Any Attribute** nodes, you must use either the [Mass Copy](mass-copy-functoid.md) functoid or the [Scripting](scripting-functoid.md) functoid (with Inline XSLT or Inline XSLT Call Template) to perform the mapping for such nodes, or simply not map those nodes.</span></span>  

## <a name="see-also"></a><span data-ttu-id="6c0ae-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c0ae-114">See Also</span></span>  
- [<span data-ttu-id="6c0ae-115">向架构插入节点</span><span class="sxs-lookup"><span data-stu-id="6c0ae-115">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)
- <span data-ttu-id="6c0ae-116">**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6c0ae-116">**Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
