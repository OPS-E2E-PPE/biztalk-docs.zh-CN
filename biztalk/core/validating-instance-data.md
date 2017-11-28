---
title: "验证实例数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19c3ca83-0abf-42ba-8e29-653ff12d5e20
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86cde9d6133959e34ec09880be8a6beca5c37191
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validate-instance-data"></a><span data-ttu-id="74ba2-102">验证实例数据</span><span class="sxs-lookup"><span data-stu-id="74ba2-102">Validate Instance Data</span></span>

## <a name="overview"></a><span data-ttu-id="74ba2-103">概述</span><span class="sxs-lookup"><span data-stu-id="74ba2-103">Overview</span></span>
<span data-ttu-id="74ba2-104">测试映射过程，你可能想要验证针对要验证实例数据符合架构结构的源和目标架构的实例数据。</span><span class="sxs-lookup"><span data-stu-id="74ba2-104">During the process of testing a map, you may want to validate instance data against the source and destination schemas to verify that the instance data adheres to the schema structure.</span></span> <span data-ttu-id="74ba2-105">要验证实例消息针对源或目标架构，请右键单击解决方案资源管理器中的架构，然后单击**验证实例**。</span><span class="sxs-lookup"><span data-stu-id="74ba2-105">To validate an instance message against the source or destination schema, right-click the schema in the Solution Explorer, and then click **Validate Instance**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="74ba2-106">如果在输出中使用自定义数据或常量，则必须验证你的源的数据类型测试数据和目标常量值是有效的。</span><span class="sxs-lookup"><span data-stu-id="74ba2-106">If you use custom data or constants in your output, you must verify that the data types of your source test data and target constant values are valid.</span></span> <span data-ttu-id="74ba2-107">在验证映射时，BizTalk 映射程序不会检查实例数据违反了定义架构的任何数据类型。</span><span class="sxs-lookup"><span data-stu-id="74ba2-107">When you validate a map, BizTalk Mapper does not check whether or not the instance data violates any data types defined by the schemas.</span></span> <span data-ttu-id="74ba2-108">在测试映射或验证实例数据时，会进行此检查。</span><span class="sxs-lookup"><span data-stu-id="74ba2-108">This is done when you test the map or validate the instance data.</span></span>  
  
 <span data-ttu-id="74ba2-109">有关如何生成和使用 BizTalk 编辑器验证实例数据的详细信息，请参阅[实例消息生成和验证](../core/instance-message-generation-and-validation.md)和[实例验证](../core/instance-validation.md)。</span><span class="sxs-lookup"><span data-stu-id="74ba2-109">For more information about how to generate and validate instance data by using BizTalk Editor, see [Instance Message Generation and Validation](../core/instance-message-generation-and-validation.md) and [Instance Validation](../core/instance-validation.md).</span></span> <span data-ttu-id="74ba2-110">实例时都提供 SQL Server 登录名。</span><span class="sxs-lookup"><span data-stu-id="74ba2-110">.</span></span> <span data-ttu-id="74ba2-111">**值**架构的节点的属性还会影响如何 BizTalk 生成实例数据。</span><span class="sxs-lookup"><span data-stu-id="74ba2-111">The **Value** property of the node of a schema also affects how BizTalk generates instance data.</span></span> <span data-ttu-id="74ba2-112">有关详细信息，请参阅**架构节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="74ba2-112">For more information, see the **Schema Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="74ba2-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74ba2-113">See Also</span></span>  
-  [<span data-ttu-id="74ba2-114">实例消息生成和验证</span><span class="sxs-lookup"><span data-stu-id="74ba2-114">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)   
-  [<span data-ttu-id="74ba2-115">如何验证在 Visual Studio 中的架构</span><span class="sxs-lookup"><span data-stu-id="74ba2-115">How to Validate Schemas in Visual Studio</span></span>](../core/how-to-validate-schemas-in-visual-studio.md)   
-  <span data-ttu-id="74ba2-116">**映射属性引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="74ba2-116">**Map Property Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
-  [<span data-ttu-id="74ba2-117">测试映射</span><span class="sxs-lookup"><span data-stu-id="74ba2-117">Testing Maps</span></span>](../core/testing-maps.md)