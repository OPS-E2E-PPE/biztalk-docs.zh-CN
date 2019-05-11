---
title: XSD 的角色 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fe08f6b-563f-4bae-a5be-551e487b2a6d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6cb9a975f137263265051be0235f33d35bd4a41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303533"
---
# <a name="role-of-xsd"></a><span data-ttu-id="611fd-102">XSD 的角色</span><span class="sxs-lookup"><span data-stu-id="611fd-102">Role of XSD</span></span>
<span data-ttu-id="611fd-103">XML 架构定义 (XSD) 语言提供了 BizTalk 中定义的消息架构的基本语法。</span><span class="sxs-lookup"><span data-stu-id="611fd-103">The XML Schema definition (XSD) language provides the underlying syntax of the message schemas defined within BizTalk.</span></span> <span data-ttu-id="611fd-104">尽管 BizTalk 编辑器和 BizTalk 映射器中的树视图使用特定于 BizTalk 的图形化层次结构的记录和字段节点 （在其他类型的节点），每个都具有其自己的属性集，此类层次结构构造和保存为 XSD。</span><span class="sxs-lookup"><span data-stu-id="611fd-104">Although the tree views in BizTalk Editor and BizTalk Mapper use a BizTalk-specific graphical hierarchy of record and field nodes (among other types of nodes), each with its own set of properties, such hierarchies are constructed and persisted as XSD.</span></span> <span data-ttu-id="611fd-105">BizTalk 编辑器提供了可以在其中查看添加或删除的架构树视图中的图形表示形式中各个节点，并且如属性的值与这些节点时所构造的 XSD 的只读的 XSD 视图更改。</span><span class="sxs-lookup"><span data-stu-id="611fd-105">BizTalk Editor provides a read-only XSD view in which you can see the XSD that is constructed as various nodes are added to or removed from the graphic representation of the schema in the tree view, and as the values of the properties associated with those nodes are changed.</span></span> <span data-ttu-id="611fd-106">尽管通常不需了解 XSD 成功构造简单的架构使用 BizTalk 编辑器的详细信息，如果您研究一下发生的 XSD 更改，当更改架构层次结构树视图中，您将了解如何使用 XSD。</span><span class="sxs-lookup"><span data-stu-id="611fd-106">Although it is usually not necessary to understand the details of XSD to successfully construct simple schemas with BizTalk Editor, if you study the XSD changes as you make changes to the schema hierarchy in the tree view, you will learn to use XSD.</span></span>  
  
 <span data-ttu-id="611fd-107">在 XSD 中，通过广泛的 BizTalk Server 定义的批注的架构批注功能有效地将 XSD 扩展为支持用于表示诸如平面文件之类的非 XML 消息所需的语义。</span><span class="sxs-lookup"><span data-stu-id="611fd-107">The schema annotation feature within XSD, with the extensive set of annotations defined by BizTalk Server, effectively allows XSD to be extended to support the necessary semantics for representing non-XML messages such as flat files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="611fd-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="611fd-108">See Also</span></span>  
 <span data-ttu-id="611fd-109">[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md) </span><span class="sxs-lookup"><span data-stu-id="611fd-109">[XSD Resources on the Web](../core/xsd-resources-on-the-web.md) </span></span>  
 [<span data-ttu-id="611fd-110">关于架构</span><span class="sxs-lookup"><span data-stu-id="611fd-110">About Schemas</span></span>](../core/about-schemas.md)