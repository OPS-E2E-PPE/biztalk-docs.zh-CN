---
title: 编辑 Functoid 属性和输入的参数 |Microsoft Docs
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
ms.openlocfilehash: 5e95e6d3c4c026038c8118bff3a00e6ddde824df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982374"
---
# <a name="editing-functoid-properties-and-input-parameters"></a><span data-ttu-id="13b0a-102">编辑 Functoid 属性和输入参数</span><span class="sxs-lookup"><span data-stu-id="13b0a-102">Editing Functoid Properties and Input Parameters</span></span>
<span data-ttu-id="13b0a-103">Functoid 属性可按如下所述分类：</span><span class="sxs-lookup"><span data-stu-id="13b0a-103">Functoid properties can be categorized as follows:</span></span>  
  
- <span data-ttu-id="13b0a-104">**标签**并**输入参数**。</span><span class="sxs-lookup"><span data-stu-id="13b0a-104">**Label** and **Input parameters**.</span></span> <span data-ttu-id="13b0a-105">这两个属性是可读/写的，对所有 functoid 可用。</span><span class="sxs-lookup"><span data-stu-id="13b0a-105">These two properties are read/write and are available for all functoids.</span></span> <span data-ttu-id="13b0a-106">**标签**属性提供了一种机制提供的 functoid，可帮助维护映射的特定实例的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="13b0a-106">The **Label** property provides a mechanism for providing a descriptive name for a particular instance of a functoid, which may help in maintaining maps.</span></span> <span data-ttu-id="13b0a-107">**输入参数**属性提供对访问**配置\<Functoid\> Functoid**对话框中，functoid 配置中扮演重要角色。</span><span class="sxs-lookup"><span data-stu-id="13b0a-107">The **Input parameters** property provides access to the **Configure \<Functoid\> Functoid** dialog box, which plays a central role in functoid configuration.</span></span>  
  
- <span data-ttu-id="13b0a-108">**脚本**并**表循环网格**。</span><span class="sxs-lookup"><span data-stu-id="13b0a-108">**Script** and **Table Looping Grid**.</span></span> <span data-ttu-id="13b0a-109">这两个属性提供对都只适用于访问对话框的访问**Scripting**并**表循环**functoid，分别。</span><span class="sxs-lookup"><span data-stu-id="13b0a-109">These two properties provide access to dialog boxes that are only applicable to the **Scripting** and **Table Looping** functoids, respectively.</span></span> <span data-ttu-id="13b0a-110">访问这些对话框**配置脚本 Functoid**对话框和**配置表循环 Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="13b0a-110">These dialog boxes are the **Configure Scripting Functoid** dialog box and the **Configure Table Looping Functoid** dialog box.</span></span>  
  
- <span data-ttu-id="13b0a-111">**名称**，**帮助**，**最大输入参数**，并且**最少输入参数**。</span><span class="sxs-lookup"><span data-stu-id="13b0a-111">**Name**, **Help**, **Maximum Input Parameters**, and **Minimum Input Parameters**.</span></span> <span data-ttu-id="13b0a-112">这四个属性是信息性的，并且始终是只读的。</span><span class="sxs-lookup"><span data-stu-id="13b0a-112">These four are informational and always read-only.</span></span>  
  
  <span data-ttu-id="13b0a-113">有关这些 functoid 属性的概念信息，请参阅[Functoid 属性](../core/functoid-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="13b0a-113">For conceptual information about these functoid properties, see [Functoid Properties](../core/functoid-properties.md).</span></span>  
  
  <span data-ttu-id="13b0a-114">本部分提供为使用，特别修改，functoid 配置输入的参数的 functoid，配置的脚本进行的一般说明的属性的分步说明**脚本** functoid，和的表网格**表循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="13b0a-114">This section provides step-by-step instructions for working with, and specifically modifying, the properties of functoids, including general instructions for configuring input parameters for functoids, configuring script for the **Scripting** functoid, and configuring table grid for the **Table Looping** functoid.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="13b0a-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="13b0a-115">In This Section</span></span>  
  
-   [<span data-ttu-id="13b0a-116">如何配置 Functoid 输入参数</span><span class="sxs-lookup"><span data-stu-id="13b0a-116">How to Configure Functoid Input Parameters</span></span>](../core/how-to-configure-functoid-input-parameters.md)  
  
-   [<span data-ttu-id="13b0a-117">如何配置脚本 Functoid</span><span class="sxs-lookup"><span data-stu-id="13b0a-117">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)  
  
-   [<span data-ttu-id="13b0a-118">如何配置表循环和表提取程序 Functoid</span><span class="sxs-lookup"><span data-stu-id="13b0a-118">How to Configure the Table Looping and Table Extractor Functoids</span></span>](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)  
  
-   [<span data-ttu-id="13b0a-119">如何标签和注释 Functoid</span><span class="sxs-lookup"><span data-stu-id="13b0a-119">How to Label and Comment a Functoid</span></span>](../core/how-to-label-and-comment-a-functoid.md)