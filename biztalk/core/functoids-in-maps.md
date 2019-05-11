---
title: 映射中的 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoids
- functoids, about functoids
- functoid types, Record Count
- functoid types, Looping
- Looping functoids
- functoids, categories
- functoid types, Addition
- Record Count functoids
ms.assetid: 10ee8b62-cb20-4d26-9d86-b6564f30c297
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45e066b759db92db1f51db81dc98816c3f757654
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387822"
---
# <a name="functoids-in-maps"></a><span data-ttu-id="6f335-102">映射中的 Functoid</span><span class="sxs-lookup"><span data-stu-id="6f335-102">Functoids in Maps</span></span>
<span data-ttu-id="6f335-103">BizTalk 映射器支持从源架构到目标架构中的字段和记录中记录和字段的复杂结构性转换。</span><span class="sxs-lookup"><span data-stu-id="6f335-103">BizTalk Mapper supports complex structural transformations from records and fields in the source schema to records and fields in the destination schema.</span></span> <span data-ttu-id="6f335-104">Functoid 使用预定义的公式和特定值，称为参数执行计算。</span><span class="sxs-lookup"><span data-stu-id="6f335-104">Functoids perform calculations by using predefined formulas and specific values, called arguments.</span></span> <span data-ttu-id="6f335-105">根据指定的记录和字段的顺序执行这些计算。</span><span class="sxs-lookup"><span data-stu-id="6f335-105">These calculations are executed based on the designated order of the records and fields.</span></span>  
  
 <span data-ttu-id="6f335-106">通过从工具箱中选择 functoid、 将其拖到网格页上，并将其链接到源架构和目标架构中的节点，可以一起添加数据，可以修改日期或时间信息、 连接数据，或可以是其他操作执行。</span><span class="sxs-lookup"><span data-stu-id="6f335-106">By selecting a functoid from the Toolbox, dragging it to the grid page, and linking it to nodes in the source schema and destination schema, data can be added together, date or time information can be modified, data can be concatenated, or other operations can be performed.</span></span> <span data-ttu-id="6f335-107">例如，**加法**functoid 将值相加并**记录计数**functoid 将返回的实例消息中循环记录的总计数。</span><span class="sxs-lookup"><span data-stu-id="6f335-107">For example, the **Addition** functoid adds values and the **Record Count** functoid returns the total count of a looping record in an instance message.</span></span> <span data-ttu-id="6f335-108">您可以在工具箱中找到的 functoid 的类别包括：高级、 转换，累计、 数据库、 日期 / 时间、 逻辑、 数学、 科学计数法和字符串。</span><span class="sxs-lookup"><span data-stu-id="6f335-108">Categories of functoids that you can find in the Toolbox include: Advanced, Conversion, Cumulative, Database, Date/ Time, Logical, Mathematical, Scientific, and String.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f335-109">所有 functoid 都均为内联C#除数据库 functoid。</span><span class="sxs-lookup"><span data-stu-id="6f335-109">All functoids are inline C# except for the Database functoids.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f335-110">目标架构节点接受来自除 functoid 只能有一个输入**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="6f335-110">Destination schema nodes accept only one input from a functoid with the exception of the **Looping** functoid.</span></span>  
  
 <span data-ttu-id="6f335-111">在本部分中的主题介绍如何从早期版本的 BizTalk Server 迁移 functoid、 functoid 概述、 其功能和如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="6f335-111">The topics in this section describe how to migrate functoids from previous versions of BizTalk Server, what functoids are, what they do, and how to use them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f335-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="6f335-112">In This Section</span></span>  
  
-   [<span data-ttu-id="6f335-113">Functoid 类别</span><span class="sxs-lookup"><span data-stu-id="6f335-113">Functoid Categories</span></span>](../core/functoid-categories.md)  
  
-   [<span data-ttu-id="6f335-114">Functoid 输入参数</span><span class="sxs-lookup"><span data-stu-id="6f335-114">Functoid Input Parameters</span></span>](../core/functoid-input-parameters.md)  
  
-   [<span data-ttu-id="6f335-115">基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="6f335-115">Basic Functoids</span></span>](../core/basic-functoids.md)  
  
-   [<span data-ttu-id="6f335-116">高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="6f335-116">Advanced Functoids</span></span>](../core/advanced-functoids.md)  
  
-   [<span data-ttu-id="6f335-117">“级联”Functoid</span><span class="sxs-lookup"><span data-stu-id="6f335-117">Cascading Functoids</span></span>](../core/cascading-functoids.md)  
  
-   [<span data-ttu-id="6f335-118">Functoid 属性</span><span class="sxs-lookup"><span data-stu-id="6f335-118">Functoid Properties</span></span>](../core/functoid-properties.md)  
  
-   [<span data-ttu-id="6f335-119">“迁移”Functoid</span><span class="sxs-lookup"><span data-stu-id="6f335-119">Migrating Functoids</span></span>](../core/migrating-functoids.md)