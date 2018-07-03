---
title: 如何为平面文件消息创建架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48f2747b-7f26-4fb2-a855-523e093f3813
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4459012155ca95166b6345ddad4390e78fce60c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984462"
---
# <a name="create-schemas-for-flat-file-messages"></a><span data-ttu-id="6d451-102">为平面文件消息创建架构</span><span class="sxs-lookup"><span data-stu-id="6d451-102">Create Schemas for Flat File Messages</span></span>

## <a name="overview"></a><span data-ttu-id="6d451-103">概述</span><span class="sxs-lookup"><span data-stu-id="6d451-103">Overview</span></span>
<span data-ttu-id="6d451-104">在创建 XML 消息架构中所述[的 XML 消息创建架构](../core/how-to-create-schemas-for-xml-messages.md)，使用**架构编辑器扩展**属性**架构**节点以启用平面文件扩展。</span><span class="sxs-lookup"><span data-stu-id="6d451-104">After creating an XML message schema as described in [Creating Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md), use the **Schema Editor Extensions** property of the **Schema** node to enable the flat file extension.</span></span> <span data-ttu-id="6d451-105">启用平面文件扩展将向架构中的许多节点类型添加大量属性。</span><span class="sxs-lookup"><span data-stu-id="6d451-105">Enabling the flat file extension adds a considerable number of properties to many of the node types within a schema.</span></span> <span data-ttu-id="6d451-106">这些属性通常用于控制平面文件业务文档和其等效 XML 业务文档之间如何相互转换，它们的值在架构文件中存储为 XML 架构定义语言 (XSD) 批注。</span><span class="sxs-lookup"><span data-stu-id="6d451-106">These properties are generally used to control how a flat file business document is translated to and from its equivalent XML business document, and their values are stored as XML Schema definition language (XSD ) annotations within the schema file.</span></span> <span data-ttu-id="6d451-107">要想正确使用这些属性，需要一些练习并且完全了解每个属性控制平面文件格式的哪些方面。</span><span class="sxs-lookup"><span data-stu-id="6d451-107">Using these properties properly takes some practice and a thorough understanding of which aspects of the flat file format they each govern.</span></span> 

<span data-ttu-id="6d451-108">有关概念和参考有关该平面文件属性的信息，请参阅[注意事项时创建平面文件消息架构](../core/considerations-when-creating-flat-file-message-schemas.md)并**平面文件架构的补充节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="6d451-108">For conceptual and reference information about the flat file properties, see [Considerations When Creating Flat File Message Schemas](../core/considerations-when-creating-flat-file-message-schemas.md) and **Supplemental Node Properties for Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  

## <a name="see-also"></a><span data-ttu-id="6d451-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d451-109">See Also</span></span>  
- [<span data-ttu-id="6d451-110">管理项目中的架构</span><span class="sxs-lookup"><span data-stu-id="6d451-110">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)
- <span data-ttu-id="6d451-111">这些属性的更多详细信息 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6d451-111">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
