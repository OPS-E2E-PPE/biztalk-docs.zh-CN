---
title: 如何创建平面文件消息架构 |Microsoft 文档
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
ms.openlocfilehash: 58583037b8fae945dea07aa8af62e969b96e073f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249405"
---
# <a name="create-schemas-for-flat-file-messages"></a><span data-ttu-id="26cae-102">创建架构的平面文件消息</span><span class="sxs-lookup"><span data-stu-id="26cae-102">Create Schemas for Flat File Messages</span></span>

## <a name="overview"></a><span data-ttu-id="26cae-103">概述</span><span class="sxs-lookup"><span data-stu-id="26cae-103">Overview</span></span>
<span data-ttu-id="26cae-104">创建 XML 消息架构中所述之后[创建架构的 XML 消息](../core/how-to-create-schemas-for-xml-messages.md)，使用**架构编辑器扩展**属性**架构**节点以启用平面文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="26cae-104">After creating an XML message schema as described in [Creating Schemas for XML Messages](../core/how-to-create-schemas-for-xml-messages.md), use the **Schema Editor Extensions** property of the **Schema** node to enable the flat file extension.</span></span> <span data-ttu-id="26cae-105">启用平面文件扩展将向架构中的许多节点类型添加大量属性。</span><span class="sxs-lookup"><span data-stu-id="26cae-105">Enabling the flat file extension adds a considerable number of properties to many of the node types within a schema.</span></span> <span data-ttu-id="26cae-106">这些属性通常用于控制平面文件业务文档和其等效 XML 业务文档之间如何相互转换，它们的值在架构文件中存储为 XML 架构定义语言 (XSD) 批注。</span><span class="sxs-lookup"><span data-stu-id="26cae-106">These properties are generally used to control how a flat file business document is translated to and from its equivalent XML business document, and their values are stored as XML Schema definition language (XSD ) annotations within the schema file.</span></span> <span data-ttu-id="26cae-107">要想正确使用这些属性，需要一些练习并且完全了解每个属性控制平面文件格式的哪些方面。</span><span class="sxs-lookup"><span data-stu-id="26cae-107">Using these properties properly takes some practice and a thorough understanding of which aspects of the flat file format they each govern.</span></span> 

<span data-ttu-id="26cae-108">有关概念和引用有关平面文件属性的信息，请参阅[注意事项时创建平面文件消息架构](../core/considerations-when-creating-flat-file-message-schemas.md)和**平面文件架构的补充节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="26cae-108">For conceptual and reference information about the flat file properties, see [Considerations When Creating Flat File Message Schemas](../core/considerations-when-creating-flat-file-message-schemas.md) and **Supplemental Node Properties for Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26cae-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26cae-109">See Also</span></span>  
-  [<span data-ttu-id="26cae-110">管理架构在项目中</span><span class="sxs-lookup"><span data-stu-id="26cae-110">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)
-  <span data-ttu-id="26cae-111">这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="26cae-111">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>