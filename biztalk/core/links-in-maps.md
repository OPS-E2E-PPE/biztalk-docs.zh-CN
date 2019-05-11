---
title: 映射中的链接 |Microsoft Docs
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
ms.openlocfilehash: ba3da2b4bebcb559616aa583fd24fd183fd085c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329655"
---
# <a name="links-in-maps"></a><span data-ttu-id="3c75f-102">映射中的链接</span><span class="sxs-lookup"><span data-stu-id="3c75f-102">Links in Maps</span></span>
<span data-ttu-id="3c75f-103">链接指定将数据从复制的元素或属性的输入的实例消息中的元素或属性在输出实例中的基本功能。</span><span class="sxs-lookup"><span data-stu-id="3c75f-103">Links specify the basic function of copying data from an element or attribute in an input instance message to an element or attribute in an output instance.</span></span> <span data-ttu-id="3c75f-104">您在设计时在源和目标架构中创建记录和字段之间的链接。</span><span class="sxs-lookup"><span data-stu-id="3c75f-104">You create links between records and fields in the source and destination schemas at design time.</span></span> <span data-ttu-id="3c75f-105">这样可以创建在运行时，输出实例消息从符合源架构的输入的实例消息符合目标架构。</span><span class="sxs-lookup"><span data-stu-id="3c75f-105">This drives the creation, at run time, of an output instance message conforming to the destination schema from an input instance message conforming to the source schema.</span></span>  
  
 <span data-ttu-id="3c75f-106">BizTalk 映射器支持一对一链接和一个多链接。</span><span class="sxs-lookup"><span data-stu-id="3c75f-106">BizTalk Mapper supports one-to-one links and one-to-many links.</span></span> <span data-ttu-id="3c75f-107">例如，链接可以连接的单个记录或字段从源架构到单个记录或目标架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="3c75f-107">For example, a link can connect a single record or field from the source schema to a single record or field in the destination schema.</span></span> <span data-ttu-id="3c75f-108">链接可以还连接的单个记录或字段从源架构到多个记录或目标架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="3c75f-108">A link can also connect a single record or field from the source schema to multiple records or fields in the destination schema.</span></span>  
  
 <span data-ttu-id="3c75f-109">链接还可以连接多个记录或字段从源架构到 functoid，然后连接到单个 （或多个） 记录和/或目标架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="3c75f-109">Links can also connect multiple records or fields from the source schema to a functoid, which then connects to a single (or multiple) record(s) and/or field(s) in the destination schema.</span></span> <span data-ttu-id="3c75f-110">一般情况下，直接从多个源记录的链接或者到单个目标记录或字段的字段不是有效并生成一条警告。</span><span class="sxs-lookup"><span data-stu-id="3c75f-110">In general, direct links from multiple source records or fields to a single destination record or field are not valid and produce a warning.</span></span> <span data-ttu-id="3c75f-111">是一个例外**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="3c75f-111">One exception to this is the **Looping** functoid.</span></span> <span data-ttu-id="3c75f-112">有关详细信息**循环**functoid，请参阅[循环 Functoid](../core/looping-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="3c75f-112">For more information about the **Looping** functoid, see [Looping Functoid](../core/looping-functoid.md).</span></span>  
  
 <span data-ttu-id="3c75f-113">在本部分中的主题介绍与创建和使用 BizTalk 映射器中的链接相关的概念。</span><span class="sxs-lookup"><span data-stu-id="3c75f-113">The topics in this section describe concepts related to creating and working with links in BizTalk Mapper.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c75f-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="3c75f-114">In This Section</span></span>  
  
-   [<span data-ttu-id="3c75f-115">链接类型</span><span class="sxs-lookup"><span data-stu-id="3c75f-115">Types of Links</span></span>](../core/types-of-links.md)  
  
-   [<span data-ttu-id="3c75f-116">创建链接</span><span class="sxs-lookup"><span data-stu-id="3c75f-116">Creating Links</span></span>](../core/creating-links.md)  
  
-   [<span data-ttu-id="3c75f-117">配置链接</span><span class="sxs-lookup"><span data-stu-id="3c75f-117">Configuring Links</span></span>](../core/configuring-links.md)  
  
-   [<span data-ttu-id="3c75f-118">记录到记录链接</span><span class="sxs-lookup"><span data-stu-id="3c75f-118">Record-to-Record Linking</span></span>](../core/record-to-record-linking.md)  
  
-   [<span data-ttu-id="3c75f-119">与“任何元素”和“任何属性”节点相关的链接</span><span class="sxs-lookup"><span data-stu-id="3c75f-119">Links To and From the Any Element and anyAttribute Nodes</span></span>](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)  
  
-   [<span data-ttu-id="3c75f-120">编译器指令和链接</span><span class="sxs-lookup"><span data-stu-id="3c75f-120">Compiler Directives and Links</span></span>](../core/compiler-directives-and-links.md)