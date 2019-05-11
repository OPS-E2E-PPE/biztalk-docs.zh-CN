---
title: Schema 节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ea02c2a-ee00-4f44-9086-83d7ac4a8832
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c14658eb48e4031345ec8ce3e9618ef601f5f5ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396938"
---
# <a name="schema-node"></a><span data-ttu-id="66fe1-102">Schema 节点</span><span class="sxs-lookup"><span data-stu-id="66fe1-102">Schema Node</span></span>

## <a name="overview"></a><span data-ttu-id="66fe1-103">概述</span><span class="sxs-lookup"><span data-stu-id="66fe1-103">Overview</span></span>
<span data-ttu-id="66fe1-104">在 BizTalk 编辑器中，架构层次结构的顶层是始终**架构**节点，不能重命名。</span><span class="sxs-lookup"><span data-stu-id="66fe1-104">In BizTalk Editor, the top of the schema hierarchy is always the **Schema** node, which cannot be renamed.</span></span> <span data-ttu-id="66fe1-105">**架构**节点对应于**架构**架构的 XML 架构定义 (XSD) 语言表示形式中的元素。</span><span class="sxs-lookup"><span data-stu-id="66fe1-105">The **Schema** node corresponds to the **schema** element in the XML Schema definition (XSD) language representation of the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66fe1-106">在 BizTalk 编辑器中，**架构**节点表示的字符串\<架构\>架构树视图中。</span><span class="sxs-lookup"><span data-stu-id="66fe1-106">In BizTalk Editor, the **Schema** node is represented with the string \<Schema\> in the schema tree view.</span></span>  
  
 <span data-ttu-id="66fe1-107">在常规的属性**架构**节点对应的属性**架构**架构的 XSD 表示形式中的元素。</span><span class="sxs-lookup"><span data-stu-id="66fe1-107">In general, the properties of the **Schema** node correspond to the attributes of the **schema** element in the XSD representation of the schema.</span></span> <span data-ttu-id="66fe1-108">有关节点属性的常规信息，请参阅[节点属性](../core/node-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="66fe1-108">For general information about node properties, see [Node Properties](../core/node-properties.md).</span></span> <span data-ttu-id="66fe1-109">有关参考信息的属性**架构**节点，请参阅**Schema 节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="66fe1-109">For reference information about the properties of the **Schema** node, see the **Schema Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="66fe1-110">在 BizTalk 编辑器中，创建新的 XML 架构时**架构**节点和一个**根**自动创建节点。</span><span class="sxs-lookup"><span data-stu-id="66fe1-110">When you create a new XML schema in BizTalk Editor, the **Schema** node and one **Root** node are created automatically.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="66fe1-111">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="66fe1-111">XSD representation</span></span>  
 <span data-ttu-id="66fe1-112">以下示例所示，在粗体类型中，对应于架构的 XSD 表示形式中的行**\<架构\>** 架构的树视图中的节点。</span><span class="sxs-lookup"><span data-stu-id="66fe1-112">The following example shows, in bold type, the lines in the XSD representation of the schema that correspond to the **\<Schema\>** node in the tree view of the schema.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="Root">  
        <xs:complexType />  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="66fe1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="66fe1-113">See Also</span></span>  
 <span data-ttu-id="66fe1-114">[BizTalk 架构表示法](../core/biztalk-representation-of-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="66fe1-114">[BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md) </span></span>  
 <span data-ttu-id="66fe1-115">[节点属性](../core/node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="66fe1-115">[Node Properties](../core/node-properties.md) </span></span>  
 [<span data-ttu-id="66fe1-116">设置节点属性</span><span class="sxs-lookup"><span data-stu-id="66fe1-116">Set Node Properties</span></span>](../core/how-to-set-node-properties.md)