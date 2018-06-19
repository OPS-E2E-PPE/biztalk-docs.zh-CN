---
title: 在映射中的链接 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- functoid types, Looping
- Looping functoids
- maps, links
- BizTalk Mapper, links
ms.assetid: 3db77b8d-7b86-4c00-99a0-0513aff9b56b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a32d2a9ef07cf2d79037d7983e49b26c6cfe5e81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262085"
---
# <a name="links-in-maps"></a><span data-ttu-id="a19b0-102">在映射中的链接</span><span class="sxs-lookup"><span data-stu-id="a19b0-102">Links in Maps</span></span>
<span data-ttu-id="a19b0-103">链接指定将数据从输入实例消息中的元素或属性复制到输出实例中的元素或属性的基本功能。</span><span class="sxs-lookup"><span data-stu-id="a19b0-103">Links specify the basic function of copying data from an element or attribute in an input instance message to an element or attribute in an output instance.</span></span> <span data-ttu-id="a19b0-104">设计时在源架构和目标架构中的记录和字段之间创建链接。</span><span class="sxs-lookup"><span data-stu-id="a19b0-104">You create links between records and fields in the source and destination schemas at design time.</span></span> <span data-ttu-id="a19b0-105">这样可以在运行时从符合源架构的输入实例消息创建符合目标架构的输出实例消息。</span><span class="sxs-lookup"><span data-stu-id="a19b0-105">This drives the creation, at run time, of an output instance message conforming to the destination schema from an input instance message conforming to the source schema.</span></span>  
  
 <span data-ttu-id="a19b0-106">BizTalk 映射器支持一对一链接和一对多链接。</span><span class="sxs-lookup"><span data-stu-id="a19b0-106">BizTalk Mapper supports one-to-one links and one-to-many links.</span></span> <span data-ttu-id="a19b0-107">例如，通过链接可以将源架构中的单个记录或字段连接到目标架构中的单个记录或字段。</span><span class="sxs-lookup"><span data-stu-id="a19b0-107">For example, a link can connect a single record or field from the source schema to a single record or field in the destination schema.</span></span> <span data-ttu-id="a19b0-108">通过链接还可以将源架构中的单个记录或字段连接到目标架构中的多个记录或字段。</span><span class="sxs-lookup"><span data-stu-id="a19b0-108">A link can also connect a single record or field from the source schema to multiple records or fields in the destination schema.</span></span>  
  
 <span data-ttu-id="a19b0-109">链接还可以连接多个记录或字段源架构中到 functoid，然后连接到单个 （或多个） 记录和/或目标架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="a19b0-109">Links can also connect multiple records or fields from the source schema to a functoid, which then connects to a single (or multiple) record(s) and/or field(s) in the destination schema.</span></span> <span data-ttu-id="a19b0-110">通常，从多个源记录或字段到单个目标记录或字段的直接链接是无效的，并会产生警告。</span><span class="sxs-lookup"><span data-stu-id="a19b0-110">In general, direct links from multiple source records or fields to a single destination record or field are not valid and produce a warning.</span></span> <span data-ttu-id="a19b0-111">一个例外是**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="a19b0-111">One exception to this is the **Looping** functoid.</span></span> <span data-ttu-id="a19b0-112">有关详细信息**循环**functoid，请参阅[循环 Functoid](../core/looping-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="a19b0-112">For more information about the **Looping** functoid, see [Looping Functoid](../core/looping-functoid.md).</span></span>  
  
 <span data-ttu-id="a19b0-113">本部分中的主题介绍在 BizTalk 映射器中创建和使用链接的相关概念。</span><span class="sxs-lookup"><span data-stu-id="a19b0-113">The topics in this section describe concepts related to creating and working with links in BizTalk Mapper.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a19b0-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="a19b0-114">In This Section</span></span>  
  
-   [<span data-ttu-id="a19b0-115">类型的链接</span><span class="sxs-lookup"><span data-stu-id="a19b0-115">Types of Links</span></span>](../core/types-of-links.md)  
  
-   [<span data-ttu-id="a19b0-116">创建链接</span><span class="sxs-lookup"><span data-stu-id="a19b0-116">Creating Links</span></span>](../core/creating-links.md)  
  
-   [<span data-ttu-id="a19b0-117">配置链接</span><span class="sxs-lookup"><span data-stu-id="a19b0-117">Configuring Links</span></span>](../core/configuring-links.md)  
  
-   [<span data-ttu-id="a19b0-118">到记录链接</span><span class="sxs-lookup"><span data-stu-id="a19b0-118">Record-to-Record Linking</span></span>](../core/record-to-record-linking.md)  
  
-   [<span data-ttu-id="a19b0-119">链接到和从任何元素和 anyAttribute 节点</span><span class="sxs-lookup"><span data-stu-id="a19b0-119">Links To and From the Any Element and anyAttribute Nodes</span></span>](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)  
  
-   [<span data-ttu-id="a19b0-120">编译器指令和链接</span><span class="sxs-lookup"><span data-stu-id="a19b0-120">Compiler Directives and Links</span></span>](../core/compiler-directives-and-links.md)