---
title: "有关映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper
- maps, file type
- maps, about maps
- BizTalk Mapper, about BizTalk Mapper
- maps
ms.assetid: 512ef2b7-3d01-4fcf-bb38-de68ec608b07
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3d15f37dc0ff0112906a449e1b1d84704b21727
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="about-maps"></a><span data-ttu-id="ed56e-102">有关映射</span><span class="sxs-lookup"><span data-stu-id="ed56e-102">About Maps</span></span>
<span data-ttu-id="ed56e-103">通过 BizTalk 映射器，可以使用链接和 functoid 在输入架构和输出架构之间定义关系。</span><span class="sxs-lookup"><span data-stu-id="ed56e-103">Using BizTalk Mapper, you define the relationship between an input and an output schema by using links and functoids.</span></span> <span data-ttu-id="ed56e-104">链接定义了记录或字段的直接数据复制。</span><span class="sxs-lookup"><span data-stu-id="ed56e-104">A link defines a direct data copy of a record or field.</span></span> <span data-ttu-id="ed56e-105">链接可以直接连接到另一架构中的项，也可以构成指向 functoid 的连接。</span><span class="sxs-lookup"><span data-stu-id="ed56e-105">Links may directly connect to items in the other schema, or they may form connections to functoids.</span></span> <span data-ttu-id="ed56e-106">functoid 可以执行更加复杂的数据操作，例如：</span><span class="sxs-lookup"><span data-stu-id="ed56e-106">Functoids perform more complex data manipulations, such as:</span></span>  
  
-   <span data-ttu-id="ed56e-107">将源架构中的两个字段的值相加，然后将结果复制到目标架构。</span><span class="sxs-lookup"><span data-stu-id="ed56e-107">Adding the value of two fields in the source schema and copying the result to the destination schema.</span></span>  
  
-   <span data-ttu-id="ed56e-108">将字符转换为 ASCII 格式。</span><span class="sxs-lookup"><span data-stu-id="ed56e-108">Converting a character to its ASCII format.</span></span>  
  
-   <span data-ttu-id="ed56e-109">返回重复记录中某个字段的平均值，然后将结果复制到目标架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="ed56e-109">Returning the average of a field in a repeating record and copying the result to a field in the destination schema.</span></span>  
  
 <span data-ttu-id="ed56e-110">BizTalk 映射器使用扩展名为 .btm 的文件存储映射。</span><span class="sxs-lookup"><span data-stu-id="ed56e-110">BizTalk Mapper stores maps in a file with a .btm extension.</span></span> <span data-ttu-id="ed56e-111">该文件保存了映射的有关设计信息：表示 functoid 的图标的位置、架构项和 functoid 之间的链接以及有关该映射的其他信息。</span><span class="sxs-lookup"><span data-stu-id="ed56e-111">The file saves design information about the map—the locations of icons representing functoids, the links between schema items and functoids, and other information about the map.</span></span> <span data-ttu-id="ed56e-112">在构建或编译映射时，BizTalk 映射器可以将该映射的有关信息转换为相应的可扩展样式表转换 (XSLT) 样式表。</span><span class="sxs-lookup"><span data-stu-id="ed56e-112">When you build or compile the map, BizTalk Mapper converts the information about the map into the corresponding Extensible Language Stylesheet Transformations (XSLT) stylesheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed56e-113">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编译器具有 16 兆字节限制单个项目中的所有字符串的总大小。</span><span class="sxs-lookup"><span data-stu-id="ed56e-113">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] compiler has a 16-megabyte limitation on the total size of all strings in a single project.</span></span> <span data-ttu-id="ed56e-114">虽然编译 BizTalk 项目，编译器将序列化架构、 映射和业务流程创建程序集，并且这会增加可能超出限制的所有字符串的总大小。</span><span class="sxs-lookup"><span data-stu-id="ed56e-114">While compiling BizTalk projects, the compiler serializes schemas, maps, and orchestrations for creating the assemblies, and this increases the total size of all strings, which may exceed the limitation.</span></span> <span data-ttu-id="ed56e-115">若要解决此问题，您可以通过将架构和/或映射放入不同的 Biztalk 项目（通常在同一个解决方案下）以对您的项目进行重新组织，以便使每个项目中的所有字符串的总大小小于 16 MB。</span><span class="sxs-lookup"><span data-stu-id="ed56e-115">To resolve this issue, you can reorganize your project by putting schemas and/or maps into different Biztalk projects (Typically, under the same solution), such that  the total size of all strings in each project is less than 16 MB.</span></span>  
  
 <span data-ttu-id="ed56e-116">所创建的映射可以用于转换或翻译数据，这些映射可以特定于单个贸易合作伙伴，也可以用于多个贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="ed56e-116">The maps that you create can transform or translate data, and they can be specific to a single trading partner or be used with many trading partners.</span></span> <span data-ttu-id="ed56e-117">本部分中的主题介绍了映射架构中所涉及的概念。</span><span class="sxs-lookup"><span data-stu-id="ed56e-117">The topics in this section provide an introduction to the concepts involved in mapping schemas.</span></span> <span data-ttu-id="ed56e-118">有关地图背景信息，请参阅[映射](../core/maps.md)。</span><span class="sxs-lookup"><span data-stu-id="ed56e-118">For background information about maps, see [Maps](../core/maps.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed56e-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="ed56e-119">In This Section</span></span>  
  
-   [<span data-ttu-id="ed56e-120">在映射中的链接</span><span class="sxs-lookup"><span data-stu-id="ed56e-120">Links in Maps</span></span>](../core/links-in-maps.md)  
  
-   [<span data-ttu-id="ed56e-121">在映射中的 Functoid</span><span class="sxs-lookup"><span data-stu-id="ed56e-121">Functoids in Maps</span></span>](../core/functoids-in-maps.md)  
  
-   [<span data-ttu-id="ed56e-122">映射编译和测试</span><span class="sxs-lookup"><span data-stu-id="ed56e-122">Map Compilation and Testing</span></span>](../core/map-compilation-and-testing.md)