---
title: 实例消息的生成和验证 |Microsoft Docs
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
ms.openlocfilehash: 7e9a79a589dcedd9169de8d753922632cff2acb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331915"
---
# <a name="instance-message-generation-and-validation"></a><span data-ttu-id="95915-102">实例消息的生成和验证</span><span class="sxs-lookup"><span data-stu-id="95915-102">Instance Message Generation and Validation</span></span>
<span data-ttu-id="95915-103">验证架构后，可用于生成示例实例消息。</span><span class="sxs-lookup"><span data-stu-id="95915-103">After you have validated a schema, you can use it to generate a sample instance message.</span></span> <span data-ttu-id="95915-104">生成的示例实例消息包含的元素和属性架构中，指定的结构并生成模拟数据需要。</span><span class="sxs-lookup"><span data-stu-id="95915-104">The sample instance message that is generated contains the element and attribute structure specified by the schema, and generate fake data where required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95915-105">使用生成实例消息不太完善，若要生成数据根据指定的多个属性值的数据生成机制。</span><span class="sxs-lookup"><span data-stu-id="95915-105">The data-generation mechanism used when generating instance messages is not sufficiently sophisticated to generate data according to values specified for several properties.</span></span> <span data-ttu-id="95915-106">例如，如果架构包含的任何值**模式**属性，现已推出**限制**类别**字段元素**节点和**字段属性**节点时其**Derived By**属性设置为**限制**，不能使用生成的实例消息，条件是，作为输入**验证实例**操作。</span><span class="sxs-lookup"><span data-stu-id="95915-106">For example, if the schema contains any values for the **Pattern** property, which is available in the **Restrictions** category for **Field Element** nodes and **Field Attribute** nodes when their **Derived By** property is set to **Restriction**, the generated instance message cannot be used as is, as input to the **Validate Instance** operation.</span></span>  
  
 <span data-ttu-id="95915-107">若要从架构生成实例消息示例，请使用**生成实例**命令在解决方案资源管理器中与该架构关联的快捷菜单上。</span><span class="sxs-lookup"><span data-stu-id="95915-107">To generate a sample instance message from a schema, use the **Generate Instance** command on the shortcut menu associated with the schema in Solution Explorer.</span></span> <span data-ttu-id="95915-108">实例消息生成操作将结果报告在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]输出窗口。</span><span class="sxs-lookup"><span data-stu-id="95915-108">The results of the instance message generation operation are reported in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Output window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95915-109">**生成实例**操作包括**验证架构**操作。</span><span class="sxs-lookup"><span data-stu-id="95915-109">The **Generate Instance** operation includes the **Validate Schema** operation.</span></span> <span data-ttu-id="95915-110">如果验证失败，将不生成任何示例实例消息。</span><span class="sxs-lookup"><span data-stu-id="95915-110">If validation fails, no sample instance message will be generated.</span></span>  
  
 <span data-ttu-id="95915-111">有关逐步说明如何从架构，包括如何配置要包含生成的实例消息的输出文件中生成的实例消息，请参阅[生成实例消息](../core/how-to-generate-instance-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="95915-111">For detailed step-by-step instructions regarding how to generate an instance message from a schema, including how to configure an output file to contain the generated instance message, see [Generating Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95915-112">如果未指定的值**根引用**的属性**架构**节点，BizTalk 编辑器生成实例消息的第一个根节点在架构中。</span><span class="sxs-lookup"><span data-stu-id="95915-112">If you do not specify a value for the **Root Reference** property of the **Schema** node, BizTalk Editor generates an instance message for the first root node in the schema.</span></span> <span data-ttu-id="95915-113">如果指定的值**根引用**属性，BizTalk 编辑器生成实例消息为指定的根。</span><span class="sxs-lookup"><span data-stu-id="95915-113">If you specify a value for the **Root Reference** property, BizTalk Editor generates an instance message for the specified root.</span></span>  
  
 <span data-ttu-id="95915-114">如果验证了您的架构，可以使用 BizTalk 编辑器来确定实例消息是否符合该架构。</span><span class="sxs-lookup"><span data-stu-id="95915-114">If you have validated your schema, you can use BizTalk Editor to determine whether an instance message conforms to that schema.</span></span>  
  
 <span data-ttu-id="95915-115">若要验证针对架构的实例消息，请使用**验证实例**命令在解决方案资源管理器中与该架构关联的快捷菜单上。</span><span class="sxs-lookup"><span data-stu-id="95915-115">To validate an instance message against a schema, use the **Validate Instance** command on the shortcut menu associated with the schema in Solution Explorer.</span></span> <span data-ttu-id="95915-116">验证的结果中报告[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]输出窗口。</span><span class="sxs-lookup"><span data-stu-id="95915-116">The results of the validation are reported in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Output window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95915-117">有些情况下在其中生成的实例消息将通过根据从其生成相同的架构验证。</span><span class="sxs-lookup"><span data-stu-id="95915-117">There are cases in which a generated instance message will not pass validation against the same schema from which it was generated.</span></span> <span data-ttu-id="95915-118">例如，如果你尝试验证使用生成的实例消息**生成实例**BizTalk 编辑器和相关架构中的命令包含任何**Field 元素**节点或**字段属性**拥有的节点及其**Derived By**属性设置为**限制**和使用该技术**模式**属性来指定相应的数据必须符合的模式，则验证将失败。</span><span class="sxs-lookup"><span data-stu-id="95915-118">For example, if you attempt to validate an instance message that was generated by using the **Generate Instance** command in BizTalk Editor, and the relevant schema includes any **Field Element** nodes or **Field Attribute** nodes that have their **Derived By** property set to **Restriction** and which use the **Pattern** property to specify a pattern to which the corresponding data must conform, the validation will fail.</span></span> <span data-ttu-id="95915-119">这是因为生成实例消息时使用的数据生成机制不太完善，若要生成数据根据指定的值**模式**属性。</span><span class="sxs-lookup"><span data-stu-id="95915-119">This is because the data-generation mechanism used when generating instance messages is not sufficiently sophisticated to generate data according to values specified for the **Pattern** property.</span></span> <span data-ttu-id="95915-120">此外存在其他情况。</span><span class="sxs-lookup"><span data-stu-id="95915-120">Other cases also exist.</span></span>  
  
 <span data-ttu-id="95915-121">有关逐步说明如何验证实例消息，包括如何指定实例消息进行验证，请参阅[验证架构](../core/how-to-validate-schemas-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="95915-121">For detailed step-by-step instructions regarding how to validate an instance message, including how to specify the instance message to be validated, see [Validating Schemas](../core/how-to-validate-schemas-in-visual-studio.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95915-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="95915-122">See Also</span></span>  
 <span data-ttu-id="95915-123">[有关架构](../core/about-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="95915-123">[About Schemas](../core/about-schemas.md) </span></span>  
 [<span data-ttu-id="95915-124">测试架构</span><span class="sxs-lookup"><span data-stu-id="95915-124">Testing Schemas</span></span>](../core/testing-schemas.md)