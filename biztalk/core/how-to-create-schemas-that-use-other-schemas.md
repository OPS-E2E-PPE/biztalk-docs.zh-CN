---
title: 如何创建使用其他架构的架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff0bcd9a-6c66-4c3b-bd41-64047a7c8392
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51fdc5e7601eebca7cc8193757cc909784ab828f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987806"
---
# <a name="how-to-create-schemas-that-use-other-schemas"></a><span data-ttu-id="6d9ab-102">如何创建使用其他架构的架构</span><span class="sxs-lookup"><span data-stu-id="6d9ab-102">How to Create Schemas That Use Other Schemas</span></span>
<span data-ttu-id="6d9ab-103">XML 架构定义 (XSD) 语言提供了三种不同但相关的机制，用于在一个架构中使用其他架构。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-103">XML Schema definition (XSD) language provides three different but related mechanisms for using one schema within another schema.</span></span> <span data-ttu-id="6d9ab-104">这些机制是导入架构、包括架构和重新定义架构。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-104">These mechanisms are importing a schema, including a schema, and redefining a schema.</span></span> <span data-ttu-id="6d9ab-105">有关这些机制以及它们之间的区别的简短摘要，请参阅[使用其他架构的](../core/schemas-that-use-other-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-105">For a brief summary of these mechanisms and how they differ, see [Schemas That Use Other Schemas](../core/schemas-that-use-other-schemas.md).</span></span> <span data-ttu-id="6d9ab-106">有关详细信息，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)有关指向 XSD 基本知识和规范。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-106">For detailed information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md) for links to the XSD primer and specifications.</span></span>  
  
 <span data-ttu-id="6d9ab-107">本主题将介绍在您要开发的架构中导入、包括和重新定义其他架构所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-107">This topic describes the steps required to import, include, and redefine other schemas within the schema you are developing.</span></span>  
  
### <a name="to-import-include-or-redefine-one-schema-within-another-schema"></a><span data-ttu-id="6d9ab-108">在一个架构中导入、包括或重新定义其他架构</span><span class="sxs-lookup"><span data-stu-id="6d9ab-108">To import, include, or redefine one schema within another schema</span></span>  
  
1. <span data-ttu-id="6d9ab-109">在 BizTalk 编辑器中，打开要在其中导入、包括或重新定义其他架构的架构。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-109">In BizTalk Editor, open the schema to which you want to import, include, or redefine another schema.</span></span> <span data-ttu-id="6d9ab-110">可以通过在解决方案资源管理器中双击来打开架构。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-110">You can open a schema by double-clicking it in Solution Explorer.</span></span>  
  
2. <span data-ttu-id="6d9ab-111">选择**架构**节点在架构树视图的顶部。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-111">Select the **Schema** node at the top of the schema tree view.</span></span>  
  
3. <span data-ttu-id="6d9ab-112">如有必要，可按 F4 打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-112">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
4. <span data-ttu-id="6d9ab-113">在属性窗口中**高级**类别中的值部分**导入**属性中，单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-113">In the Properties window, in the **Advanced** category, in the value portion of the **Imports** property, click the ellipsis (**...**) button.</span></span>  
  
5. <span data-ttu-id="6d9ab-114">在中**导入**对话框中**作为新架构导入**列表中，选择**XSD 导入**， **XSD Include**，或**XSD重新定义**，根据需要，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-114">In the **Imports** dialog box, in the **Import New Schema as** list, select **XSD Import**, **XSD Include**, or **XSD Redefine**, as appropriate, and then click **Add**.</span></span>  
  
6. <span data-ttu-id="6d9ab-115">在中**BizTalk 类型选取器**对话框框中，展开**架构**节点在项目树中，选择你想要导入、 包括或重新定义，，然后单击该架构**确定**。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-115">In the **BizTalk Type Picker** dialog box, expand the **Schema** node in the project tree, select the schema that you want to import, include, or redefine, and then click **OK**.</span></span>  
  
7. <span data-ttu-id="6d9ab-116">在中**导入**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-116">In the **Imports** dialog box, click **OK**.</span></span>  
  
    <span data-ttu-id="6d9ab-117">相应 XSD 指令来实现导入、 包括或重新定义操作添加到**架构**在 XSD 视图中，包括新的元素**导入**，**包括**，或**重新定义**元素中的，根据需要。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-117">The appropriate XSD directives to implement the import, include, or redefine operation are added to the **schema** element in the XSD view, including a new **import**, **include**, or **redefine** element, as appropriate.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6d9ab-118">确保您了解这三种机制的不同用途，例如它们在命名空间要求方面有何不同。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-118">Make sure you understand the different purposes of these three mechanisms, such as how they differ with respect to namespace requirements.</span></span> <span data-ttu-id="6d9ab-119">您始终可以删除以前导入、包括或重新定义的架构，然后使用另外两种机制之一。但根据您以前引用该架构的广泛程度，您可能需要相应地重做有关架构的工作。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-119">You can always delete a previously imported, included, or redefined schema and then use one of the other two mechanisms, but depending on how extensively you have referenced that schema, you may need to rework your schema accordingly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6d9ab-120">用于在一个架构中导入、包括和重新定义其他架构的 XSD 机制通过引用导入、包括或重新定义的架构来进行工作。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-120">The XSD mechanism for importing, including, and redefining one schema within another schema works by reference to the imported, included, or redefined schema.</span></span> <span data-ttu-id="6d9ab-121">这意味着如果您对导入、包括或重新定义的架构进行更改，则该更改将反映到包含导入、包括或重新定义引用的架构中。</span><span class="sxs-lookup"><span data-stu-id="6d9ab-121">This means that if you make a change to the imported, included, or redefined schema, that change will be reflected in the schema containing the import, include, or redefine reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d9ab-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d9ab-122">See Also</span></span>  
 <span data-ttu-id="6d9ab-123">[管理项目中的架构](../core/managing-schemas-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="6d9ab-123">[Managing Schemas Within Projects](../core/managing-schemas-within-projects.md) </span></span>  
 [<span data-ttu-id="6d9ab-124">如何创建对其他节点或类型的引用</span><span class="sxs-lookup"><span data-stu-id="6d9ab-124">How to Create References to Another Node or Type</span></span>](../core/how-to-create-references-to-another-node-or-type.md)