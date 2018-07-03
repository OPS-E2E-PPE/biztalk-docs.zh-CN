---
title: 如何添加常量值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f46bf66e-caf2-4352-930f-c3c43a5717c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48c6db99d656274f89ee5866f772db163de26c31
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976542"
---
# <a name="how-to-add-constant-values"></a><span data-ttu-id="c4a86-102">如何添加常量值</span><span class="sxs-lookup"><span data-stu-id="c4a86-102">How to Add Constant Values</span></span>
<span data-ttu-id="c4a86-103">在测试映射时，有时您会希望设置一些在测试期间使用的常数值。</span><span class="sxs-lookup"><span data-stu-id="c4a86-103">When testing maps, you will sometimes want to set constant values for use during the test.</span></span>  
  
## <a name="set-constant-values-for-nodes-in-the-source-or-destination-schema-trees"></a><span data-ttu-id="c4a86-104">设置常量节点中的源或目标架构树</span><span class="sxs-lookup"><span data-stu-id="c4a86-104">Set constant values for nodes in the source or destination schema trees</span></span>  
  
1. <span data-ttu-id="c4a86-105">在源架构树或目标架构树中选择记录或字段。</span><span class="sxs-lookup"><span data-stu-id="c4a86-105">Select a record or field in the source or destination schema trees.</span></span>  
  
2. <span data-ttu-id="c4a86-106">在属性窗口中**常规**类别中，使用**值**属性输入所选的记录或字段的值。</span><span class="sxs-lookup"><span data-stu-id="c4a86-106">In the Properties window, in the **General** category, use the **Value** property to enter a value for the selected record or field.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c4a86-107">只能将一个值关联的记录与及其**内容**属性设置为**纯文本**或**混合**。</span><span class="sxs-lookup"><span data-stu-id="c4a86-107">You can only associate a value with a record with its **Content** property set to **Text Only** or **Mixed**.</span></span>  
  
   <span data-ttu-id="c4a86-108">在源架构中，如果将节点**值**属性设置为**\<空\>**，源架构生成的实例消息包含为相应的空值节点。</span><span class="sxs-lookup"><span data-stu-id="c4a86-108">For a node in source schema, if you set the **Value** property to **\<empty\>**, the generated instance message for the source schema contains an empty value for the respective node.</span></span>  
  
   <span data-ttu-id="c4a86-109">有时，您并未使用目标架构中的全部字段，即，目标架构中的某些字段将不含有任何传入链接。</span><span class="sxs-lookup"><span data-stu-id="c4a86-109">Sometimes, you do not use all the fields in the target schema, i.e. some of the fields in the target schema do not have any incoming links.</span></span> <span data-ttu-id="c4a86-110">在这种情况下，测试映射操作将引发错误，则**验证测试映射输入**或**验证测试映射输出**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="c4a86-110">In such cases, the Test Map operation throws error, provided that the **Validate TestMap Input** or **Validate TestMap Output** properties are set to **True**.</span></span> <span data-ttu-id="c4a86-111">若要避免这种情况下的测试映射错误，请设置**值**为常量值节点的属性或**\<空\>**。</span><span class="sxs-lookup"><span data-stu-id="c4a86-111">To avoid Test Map errors in such cases, set the **Value** property of the node to either a constant value or **\<empty\>**.</span></span> <span data-ttu-id="c4a86-112">使用**\<空\>** 如果您不想要设置任意数据的未使用的目标架构字段。</span><span class="sxs-lookup"><span data-stu-id="c4a86-112">Use **\<empty\>** if you do not want to set arbitrary data for unused target schema fields.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4a86-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4a86-113">See Also</span></span>  
[<span data-ttu-id="c4a86-114">验证和测试映射</span><span class="sxs-lookup"><span data-stu-id="c4a86-114">Validate and test your maps</span></span>](../core/how-to-configure-map-validation-and-test-parameters.md)