---
title: 有关地图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper
- maps, file type
- maps, about maps
- BizTalk Mapper, about BizTalk Mapper
- maps
ms.assetid: 512ef2b7-3d01-4fcf-bb38-de68ec608b07
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64b7a2e7f89e927b4759ea814f341684195273e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362339"
---
# <a name="about-maps"></a><span data-ttu-id="501e0-102">有关地图</span><span class="sxs-lookup"><span data-stu-id="501e0-102">About Maps</span></span>
<span data-ttu-id="501e0-103">使用 BizTalk 映射器，通过使用链接和 functoid 定义输入和输出架构之间的关系。</span><span class="sxs-lookup"><span data-stu-id="501e0-103">Using BizTalk Mapper, you define the relationship between an input and an output schema by using links and functoids.</span></span> <span data-ttu-id="501e0-104">链接定义记录或字段的直接数据的复制。</span><span class="sxs-lookup"><span data-stu-id="501e0-104">A link defines a direct data copy of a record or field.</span></span> <span data-ttu-id="501e0-105">链接可以直接连接到其他架构中的项或也可以构成指向 functoid 的连接。</span><span class="sxs-lookup"><span data-stu-id="501e0-105">Links may directly connect to items in the other schema, or they may form connections to functoids.</span></span> <span data-ttu-id="501e0-106">Functoid 可以执行更复杂的数据操作，如：</span><span class="sxs-lookup"><span data-stu-id="501e0-106">Functoids perform more complex data manipulations, such as:</span></span>  
  
- <span data-ttu-id="501e0-107">在源架构并将结果复制到目标架构中添加两个字段的值。</span><span class="sxs-lookup"><span data-stu-id="501e0-107">Adding the value of two fields in the source schema and copying the result to the destination schema.</span></span>  
  
- <span data-ttu-id="501e0-108">将字符转换为 ASCII 格式。</span><span class="sxs-lookup"><span data-stu-id="501e0-108">Converting a character to its ASCII format.</span></span>  
  
- <span data-ttu-id="501e0-109">在重复记录并将结果复制到目标架构中的字段中返回字段的平均值。</span><span class="sxs-lookup"><span data-stu-id="501e0-109">Returning the average of a field in a repeating record and copying the result to a field in the destination schema.</span></span>  
  
  <span data-ttu-id="501e0-110">BizTalk 映射器将映射存储在扩展名为.btm 的文件中。</span><span class="sxs-lookup"><span data-stu-id="501e0-110">BizTalk Mapper stores maps in a file with a .btm extension.</span></span> <span data-ttu-id="501e0-111">该文件将保存该映射的有关设计信息 — 的图标表示 functoid、 架构项和 functoid 之间的链接的位置和该映射的有关其他信息。</span><span class="sxs-lookup"><span data-stu-id="501e0-111">The file saves design information about the map—the locations of icons representing functoids, the links between schema items and functoids, and other information about the map.</span></span> <span data-ttu-id="501e0-112">当生成或编译映射时，BizTalk 映射器将相应的可扩展语言样式表转换 (XSLT) 样式表转换为该映射的有关信息。</span><span class="sxs-lookup"><span data-stu-id="501e0-112">When you build or compile the map, BizTalk Mapper converts the information about the map into the corresponding Extensible Language Stylesheet Transformations (XSLT) stylesheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="501e0-113">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编译器中的单个项目的所有字符串的总大小具有 16 兆字节的限制。</span><span class="sxs-lookup"><span data-stu-id="501e0-113">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler has a 16-megabyte limitation on the total size of all strings in a single project.</span></span> <span data-ttu-id="501e0-114">而编译 BizTalk 项目，编译器将序列化架构、 映射和业务流程创建程序集，而这会增大可能会超出此限制的所有字符串的总大小。</span><span class="sxs-lookup"><span data-stu-id="501e0-114">While compiling BizTalk projects, the compiler serializes schemas, maps, and orchestrations for creating the assemblies, and this increases the total size of all strings, which may exceed the limitation.</span></span> <span data-ttu-id="501e0-115">若要解决此问题，您可以通过重新组织你的项目将架构和/或映射放入不同的 Biztalk 项目 （通常情况下，相同的解决方案） 下,，每个项目中的所有字符串的总大小小于 16 MB。</span><span class="sxs-lookup"><span data-stu-id="501e0-115">To resolve this issue, you can reorganize your project by putting schemas and/or maps into different Biztalk projects (Typically, under the same solution), such that  the total size of all strings in each project is less than 16 MB.</span></span>  
  
 <span data-ttu-id="501e0-116">您创建的映射可以转换或翻译数据，并且它们可以是特定于单个贸易合作伙伴也可以用于多个贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="501e0-116">The maps that you create can transform or translate data, and they can be specific to a single trading partner or be used with many trading partners.</span></span> <span data-ttu-id="501e0-117">在本部分中的主题提供针对映射架构中所涉及的概念的介绍。</span><span class="sxs-lookup"><span data-stu-id="501e0-117">The topics in this section provide an introduction to the concepts involved in mapping schemas.</span></span> <span data-ttu-id="501e0-118">有关地图的背景信息，请参阅[映射](../core/maps.md)。</span><span class="sxs-lookup"><span data-stu-id="501e0-118">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="501e0-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="501e0-119">In This Section</span></span>  
  
-   [<span data-ttu-id="501e0-120">映射中的链接</span><span class="sxs-lookup"><span data-stu-id="501e0-120">Links in Maps</span></span>](../core/links-in-maps.md)  
  
-   [<span data-ttu-id="501e0-121">映射中的 Functoid</span><span class="sxs-lookup"><span data-stu-id="501e0-121">Functoids in Maps</span></span>](../core/functoids-in-maps.md)  
  
-   [<span data-ttu-id="501e0-122">映射编译和测试</span><span class="sxs-lookup"><span data-stu-id="501e0-122">Map Compilation and Testing</span></span>](../core/map-compilation-and-testing.md)