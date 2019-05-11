---
title: 验证实例数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19c3ca83-0abf-42ba-8e29-653ff12d5e20
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 648e3e97a3a7173278256d109f362938c3176988
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398579"
---
# <a name="validate-instance-data"></a><span data-ttu-id="71583-102">验证实例数据</span><span class="sxs-lookup"><span data-stu-id="71583-102">Validate Instance Data</span></span>

## <a name="overview"></a><span data-ttu-id="71583-103">概述</span><span class="sxs-lookup"><span data-stu-id="71583-103">Overview</span></span>
<span data-ttu-id="71583-104">在测试映射的过程中，你可能想要根据要验证实例数据符合架构结构的源和目标架构验证实例数据。</span><span class="sxs-lookup"><span data-stu-id="71583-104">During the process of testing a map, you may want to validate instance data against the source and destination schemas to verify that the instance data adheres to the schema structure.</span></span> <span data-ttu-id="71583-105">要验证针对源或目标架构的实例消息，请右键单击解决方案资源管理器中的架构，然后单击**验证实例**。</span><span class="sxs-lookup"><span data-stu-id="71583-105">To validate an instance message against the source or destination schema, right-click the schema in the Solution Explorer, and then click **Validate Instance**.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="71583-106">如果在输出中使用自定义数据或常量，则必须验证您的源的数据类型的测试数据和目标的常量值有效。</span><span class="sxs-lookup"><span data-stu-id="71583-106">If you use custom data or constants in your output, you must verify that the data types of your source test data and target constant values are valid.</span></span> <span data-ttu-id="71583-107">验证映射时，BizTalk 映射器不会检查实例数据违反了定义架构的任何数据类型。</span><span class="sxs-lookup"><span data-stu-id="71583-107">When you validate a map, BizTalk Mapper does not check whether or not the instance data violates any data types defined by the schemas.</span></span> <span data-ttu-id="71583-108">这是测试映射或验证实例数据时。</span><span class="sxs-lookup"><span data-stu-id="71583-108">This is done when you test the map or validate the instance data.</span></span>  

 <span data-ttu-id="71583-109">有关如何生成和验证实例数据的使用 BizTalk 编辑器的详细信息，请参阅[实例消息的生成和验证](../core/instance-message-generation-and-validation.md)并[实例验证](../core/instance-validation.md)。</span><span class="sxs-lookup"><span data-stu-id="71583-109">For more information about how to generate and validate instance data by using BizTalk Editor, see [Instance Message Generation and Validation](../core/instance-message-generation-and-validation.md) and [Instance Validation](../core/instance-validation.md).</span></span> <span data-ttu-id="71583-110">.</span><span class="sxs-lookup"><span data-stu-id="71583-110">.</span></span> <span data-ttu-id="71583-111">**值**架构的节点的属性也会影响 BizTalk 生成实例数据的方式。</span><span class="sxs-lookup"><span data-stu-id="71583-111">The **Value** property of the node of a schema also affects how BizTalk generates instance data.</span></span> <span data-ttu-id="71583-112">有关详细信息，请参阅**Schema 节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="71583-112">For more information, see the **Schema Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="71583-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="71583-113">See Also</span></span>  
- [<span data-ttu-id="71583-114">实例消息的生成和验证</span><span class="sxs-lookup"><span data-stu-id="71583-114">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)   
- [<span data-ttu-id="71583-115">如何在 Visual Studio 中的架构验证</span><span class="sxs-lookup"><span data-stu-id="71583-115">How to Validate Schemas in Visual Studio</span></span>](../core/how-to-validate-schemas-in-visual-studio.md)   
- <span data-ttu-id="71583-116">**映射属性参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="71583-116">**Map Property Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
- [<span data-ttu-id="71583-117">测试映射</span><span class="sxs-lookup"><span data-stu-id="71583-117">Testing Maps</span></span>](../core/testing-maps.md)
