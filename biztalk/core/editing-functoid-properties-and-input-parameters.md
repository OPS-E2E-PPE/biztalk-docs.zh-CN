---
title: 编辑 Functoid 属性和输入的参数 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 257f92d7-8196-4c7c-98de-819996270e43
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3d87396713b7fa8f7874b921e6ee9097399d1c6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968611"
---
# <a name="editing-functoid-properties-and-input-parameters"></a><span data-ttu-id="aaa03-102">编辑 Functoid 属性和输入参数</span><span class="sxs-lookup"><span data-stu-id="aaa03-102">Editing Functoid Properties and Input Parameters</span></span>
<span data-ttu-id="aaa03-103">Functoid 属性可按如下所述分类：</span><span class="sxs-lookup"><span data-stu-id="aaa03-103">Functoid properties can be categorized as follows:</span></span>  
  
-   <span data-ttu-id="aaa03-104">**标签**和**输入参数**。</span><span class="sxs-lookup"><span data-stu-id="aaa03-104">**Label** and **Input parameters**.</span></span> <span data-ttu-id="aaa03-105">这两个属性是可读/写的，对所有 functoid 可用。</span><span class="sxs-lookup"><span data-stu-id="aaa03-105">These two properties are read/write and are available for all functoids.</span></span> <span data-ttu-id="aaa03-106">**标签**属性提供一种机制，用于提供 functoid，这可以帮助维护地图中的特定实例的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="aaa03-106">The **Label** property provides a mechanism for providing a descriptive name for a particular instance of a functoid, which may help in maintaining maps.</span></span> <span data-ttu-id="aaa03-107">**输入参数**属性提供访问权限**配置\<Functoid\> Functoid**对话框中，在 functoid 配置中扮演着重要作用。</span><span class="sxs-lookup"><span data-stu-id="aaa03-107">The **Input parameters** property provides access to the **Configure \<Functoid\> Functoid** dialog box, which plays a central role in functoid configuration.</span></span>  
  
-   <span data-ttu-id="aaa03-108">**脚本**和**表循环网格**。</span><span class="sxs-lookup"><span data-stu-id="aaa03-108">**Script** and **Table Looping Grid**.</span></span> <span data-ttu-id="aaa03-109">这两个属性提供访问是只适用于的对话框**脚本**和**表循环**functoid，分别。</span><span class="sxs-lookup"><span data-stu-id="aaa03-109">These two properties provide access to dialog boxes that are only applicable to the **Scripting** and **Table Looping** functoids, respectively.</span></span> <span data-ttu-id="aaa03-110">这些对话框**配置脚本 Functoid**对话框中和**配置表循环 Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="aaa03-110">These dialog boxes are the **Configure Scripting Functoid** dialog box and the **Configure Table Looping Functoid** dialog box.</span></span>  
  
-   <span data-ttu-id="aaa03-111">**名称**，**帮助**，**最多输入参数**，和**最小输入参数**。</span><span class="sxs-lookup"><span data-stu-id="aaa03-111">**Name**, **Help**, **Maximum Input Parameters**, and **Minimum Input Parameters**.</span></span> <span data-ttu-id="aaa03-112">这四个属性是信息性的，并且始终是只读的。</span><span class="sxs-lookup"><span data-stu-id="aaa03-112">These four are informational and always read-only.</span></span>  
  
 <span data-ttu-id="aaa03-113">有关这些 functoid 属性的概念信息，请参阅[Functoid 属性](../core/functoid-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="aaa03-113">For conceptual information about these functoid properties, see [Functoid Properties](../core/functoid-properties.md).</span></span>  
  
 <span data-ttu-id="aaa03-114">本部分提供有关使用，以及专门修改 functoid，包括配置 functoid，配置的脚本的输入的参数的常规说明的属性的分步说明**脚本** functoid，并配置表网格**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="aaa03-114">This section provides step-by-step instructions for working with, and specifically modifying, the properties of functoids, including general instructions for configuring input parameters for functoids, configuring script for the **Scripting** functoid, and configuring table grid for the **Table Looping** functoid.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aaa03-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="aaa03-115">In This Section</span></span>  
  
-   [<span data-ttu-id="aaa03-116">如何配置 Functoid 输入参数</span><span class="sxs-lookup"><span data-stu-id="aaa03-116">How to Configure Functoid Input Parameters</span></span>](../core/how-to-configure-functoid-input-parameters.md)  
  
-   [<span data-ttu-id="aaa03-117">如何配置脚本 Functoid</span><span class="sxs-lookup"><span data-stu-id="aaa03-117">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)  
  
-   [<span data-ttu-id="aaa03-118">如何配置表循环和表提取程序 Functoid</span><span class="sxs-lookup"><span data-stu-id="aaa03-118">How to Configure the Table Looping and Table Extractor Functoids</span></span>](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)  
  
-   [<span data-ttu-id="aaa03-119">如何标签和注释 Functoid</span><span class="sxs-lookup"><span data-stu-id="aaa03-119">How to Label and Comment a Functoid</span></span>](../core/how-to-label-and-comment-a-functoid.md)