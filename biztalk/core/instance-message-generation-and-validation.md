---
title: 实例消息生成和验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a306846-3942-4ba1-a74e-6ead8deb0322
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 964f9bd2ee2b8bb20872bc593723cea778b5ed81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257981"
---
# <a name="instance-message-generation-and-validation"></a><span data-ttu-id="6cefd-102">实例消息的生成和验证</span><span class="sxs-lookup"><span data-stu-id="6cefd-102">Instance Message Generation and Validation</span></span>
<span data-ttu-id="6cefd-103">在验证架构之后，可以使用该架构来生成示例实例消息。</span><span class="sxs-lookup"><span data-stu-id="6cefd-103">After you have validated a schema, you can use it to generate a sample instance message.</span></span> <span data-ttu-id="6cefd-104">生成的示例实例消息包含该架构指定的元素和属性结构，并生成必需的虚设数据。</span><span class="sxs-lookup"><span data-stu-id="6cefd-104">The sample instance message that is generated contains the element and attribute structure specified by the schema, and generate fake data where required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6cefd-105">生成实例消息所使用的数据生成机制还不太完善，不能根据为多个属性指定的值来生成数据。</span><span class="sxs-lookup"><span data-stu-id="6cefd-105">The data-generation mechanism used when generating instance messages is not sufficiently sophisticated to generate data according to values specified for several properties.</span></span> <span data-ttu-id="6cefd-106">例如，如果架构包含的任何值**模式**属性，它是位于**限制**类别**Field 元素**节点和**字段特性**节点时其**派生源**属性设置为**限制**，生成的实例消息不能用作是作为输入**验证实例**操作。</span><span class="sxs-lookup"><span data-stu-id="6cefd-106">For example, if the schema contains any values for the **Pattern** property, which is available in the **Restrictions** category for **Field Element** nodes and **Field Attribute** nodes when their **Derived By** property is set to **Restriction**, the generated instance message cannot be used as is, as input to the **Validate Instance** operation.</span></span>  
  
 <span data-ttu-id="6cefd-107">若要从架构生成的示例实例消息，请使用**生成实例**命令在解决方案资源管理器中的架构与关联的快捷菜单上。</span><span class="sxs-lookup"><span data-stu-id="6cefd-107">To generate a sample instance message from a schema, use the **Generate Instance** command on the shortcut menu associated with the schema in Solution Explorer.</span></span> <span data-ttu-id="6cefd-108">实例消息生成操作的结果将在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“输出”窗口中报告。</span><span class="sxs-lookup"><span data-stu-id="6cefd-108">The results of the instance message generation operation are reported in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Output window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6cefd-109">**生成实例**操作包括**验证架构**操作。</span><span class="sxs-lookup"><span data-stu-id="6cefd-109">The **Generate Instance** operation includes the **Validate Schema** operation.</span></span> <span data-ttu-id="6cefd-110">如果验证失败，将不会生成示例实例消息。</span><span class="sxs-lookup"><span data-stu-id="6cefd-110">If validation fails, no sample instance message will be generated.</span></span>  
  
 <span data-ttu-id="6cefd-111">有关详细的分步说明，有关如何从架构，包括如何配置输出文件包含生成的实例消息中，生成实例消息，请参阅[生成实例消息](../core/how-to-generate-instance-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="6cefd-111">For detailed step-by-step instructions regarding how to generate an instance message from a schema, including how to configure an output file to contain the generated instance message, see [Generating Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6cefd-112">如果未指定的值**根引用**属性**架构**BizTalk 编辑器节点在架构中生成的第一个根节点实例消息。</span><span class="sxs-lookup"><span data-stu-id="6cefd-112">If you do not specify a value for the **Root Reference** property of the **Schema** node, BizTalk Editor generates an instance message for the first root node in the schema.</span></span> <span data-ttu-id="6cefd-113">如果指定的值**根引用**属性，BizTalk 编辑器生成指定的根实例消息。</span><span class="sxs-lookup"><span data-stu-id="6cefd-113">If you specify a value for the **Root Reference** property, BizTalk Editor generates an instance message for the specified root.</span></span>  
  
 <span data-ttu-id="6cefd-114">如果已对架构进行了验证，即可使用 BizTalk 编辑器来确定实例消息是否符合该架构。</span><span class="sxs-lookup"><span data-stu-id="6cefd-114">If you have validated your schema, you can use BizTalk Editor to determine whether an instance message conforms to that schema.</span></span>  
  
 <span data-ttu-id="6cefd-115">若要验证针对架构的实例消息，使用**验证实例**命令在解决方案资源管理器中的架构与关联的快捷菜单上。</span><span class="sxs-lookup"><span data-stu-id="6cefd-115">To validate an instance message against a schema, use the **Validate Instance** command on the shortcut menu associated with the schema in Solution Explorer.</span></span> <span data-ttu-id="6cefd-116">验证的结果将在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“输出”窗口中报告。</span><span class="sxs-lookup"><span data-stu-id="6cefd-116">The results of the validation are reported in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Output window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6cefd-117">有时，生成的实例消息将不能通过根据生成该实例消息的同一架构所执行的验证。</span><span class="sxs-lookup"><span data-stu-id="6cefd-117">There are cases in which a generated instance message will not pass validation against the same schema from which it was generated.</span></span> <span data-ttu-id="6cefd-118">例如，如果你尝试验证实例消息生成了使用**生成实例**BizTalk 编辑器和相关的架构中的命令包含任何**Field 元素**节点或**字段特性**节点具有其**派生源**属性设置为**限制**和使用**模式**属性来指定相应的数据必须符合的模式，则验证将会失败。</span><span class="sxs-lookup"><span data-stu-id="6cefd-118">For example, if you attempt to validate an instance message that was generated by using the **Generate Instance** command in BizTalk Editor, and the relevant schema includes any **Field Element** nodes or **Field Attribute** nodes that have their **Derived By** property set to **Restriction** and which use the **Pattern** property to specify a pattern to which the corresponding data must conform, the validation will fail.</span></span> <span data-ttu-id="6cefd-119">这是因为生成实例消息时使用的数据生成机制不足够复杂以生成数据为指定的值根据**模式**属性。</span><span class="sxs-lookup"><span data-stu-id="6cefd-119">This is because the data-generation mechanism used when generating instance messages is not sufficiently sophisticated to generate data according to values specified for the **Pattern** property.</span></span> <span data-ttu-id="6cefd-120">此外，还存在其他情况。</span><span class="sxs-lookup"><span data-stu-id="6cefd-120">Other cases also exist.</span></span>  
  
 <span data-ttu-id="6cefd-121">有关详细的分步说明，有关如何验证消息实例，包括如何指定要验证的实例消息，请参阅[验证架构](../core/how-to-validate-schemas-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="6cefd-121">For detailed step-by-step instructions regarding how to validate an instance message, including how to specify the instance message to be validated, see [Validating Schemas](../core/how-to-validate-schemas-in-visual-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cefd-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cefd-122">See Also</span></span>  
 <span data-ttu-id="6cefd-123">[有关架构](../core/about-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="6cefd-123">[About Schemas](../core/about-schemas.md) </span></span>  
 [<span data-ttu-id="6cefd-124">测试架构</span><span class="sxs-lookup"><span data-stu-id="6cefd-124">Testing Schemas</span></span>](../core/testing-schemas.md)