---
title: "平面文件架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8009fba7-85f0-4795-9284-5b4e94b3fc72
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674a862b3966088bb1d75dd17ceacd47c30bdda1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-schemas"></a><span data-ttu-id="bd0d3-102">平面文件架构</span><span class="sxs-lookup"><span data-stu-id="bd0d3-102">Flat File Schemas</span></span>

## <a name="purpose-of-flat-file-schemas"></a><span data-ttu-id="bd0d3-103">平面文件架构的用途</span><span class="sxs-lookup"><span data-stu-id="bd0d3-103">Purpose of flat file schemas</span></span>
<span data-ttu-id="bd0d3-104">平面文件架构有两种用途。</span><span class="sxs-lookup"><span data-stu-id="bd0d3-104">Flat file schemas serve two purposes.</span></span> <span data-ttu-id="bd0d3-105">它们可以将所有相同的记录和字段特性（包括结构）定义为 XML 架构，并提供用于定义所有平面文件特性的机制，在将平面文件实例消息翻译为等效的 XML 实例消息（或将 XML 实例消息翻译为等效的平面文件实例消息）时需要使用这些特性。</span><span class="sxs-lookup"><span data-stu-id="bd0d3-105">They define all of the same record and field characteristics (including structure) as XML schemas, and they provide a mechanism for defining all of the flat file characteristics that are required to translate a flat file instance message into an equivalent XML instance message (or vice versa).</span></span> <span data-ttu-id="bd0d3-106">在 BizTalk 映射器中使用平面文件架构来定义平面文件实例消息向其他目标结构的转换时，前一种用途最为有用。</span><span class="sxs-lookup"><span data-stu-id="bd0d3-106">The former purpose is most useful when using the flat file schema within BizTalk Mapper to define a transformation of conforming flat file instance messages into a different, destination structure.</span></span> <span data-ttu-id="bd0d3-107">由 BizTalk 映射器中的目标架构定义的目标结构可以由平面文件消息架构（可以是 XML 架构）控制，也可以不通过该架构控制。</span><span class="sxs-lookup"><span data-stu-id="bd0d3-107">The destination structure, defined by the destination schema in BizTalk Mapper, may or may not be governed by a flat file message schema (it could be an XML schema).</span></span>  
  
 <span data-ttu-id="bd0d3-108">后一种用途用于文档的平面文件格式与其等效的 XML 格式之间的转换，它使用的信息非常广泛，并通过使用其批注语法将这些信息添加到 XML 架构定义 (XSD) 语言架构中。</span><span class="sxs-lookup"><span data-stu-id="bd0d3-108">The latter purpose, that of translating between the flat file format of the document and its equivalent XML format, uses an extensive set of information that is added to the XML Schema definition (XSD) language schema using its annotation syntax.</span></span> <span data-ttu-id="bd0d3-109">在根据控制 XML 实例消息结构的架构对 XML 实例消息进行验证时，就 XSD 而言，在用途方面此信息是多余的。</span><span class="sxs-lookup"><span data-stu-id="bd0d3-109">This information is superfluous from an XSD perspective, in terms of its usefulness in validating an XML instance message against the schema that governs its structure.</span></span> <span data-ttu-id="bd0d3-110">不过，XSD 批注语法提供一个用于存储内各种不同的作用域，范围从架构范围以中的批注的形式存储的信息中的XSD架构的平面文件结构信息的方便机制**架构**元素的信息的特定于特定记录或字段，以在相应的批注的形式存储**元素**或**属性**元素。</span><span class="sxs-lookup"><span data-stu-id="bd0d3-110">Nevertheless, the XSD annotation syntax provides a convenient mechanism for storing flat file structure information within the XSD schema within a variety of different scopes, ranging from schema-wide information stored as annotations within the **schema** element, to information that is specific to a particular record or field, stored as annotations within the corresponding **element** or **attribute** element.</span></span>  
  
 <span data-ttu-id="bd0d3-111">使平面文件架构与其 XML 等效项不同的另一个特性是实例消息不能与基于其内容的控制架构相匹配。</span><span class="sxs-lookup"><span data-stu-id="bd0d3-111">Another characteristic of flat file schemas that make them different than their XML counterparts is the fact that instance messages cannot be matched to their governing schemas based on their content.</span></span> <span data-ttu-id="bd0d3-112">必须指定静态架构集以供平面文件拆装器在运行时使用。</span><span class="sxs-lookup"><span data-stu-id="bd0d3-112">Instead, a static set of schemas must be specified for use by the flat file disassembler at runtime.</span></span>  
  
 <span data-ttu-id="bd0d3-113">若要查看的平面文件的特征与关联的其他节点属性，你需要指定**平面文件扩展名**使用**架构编辑器扩展**属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="bd0d3-113">To see the additional node properties associated with the characteristics of flat files, you need to specify the **Flat File Extension** by using the **Schema Editor Extensions** property of the **Schema** node.</span></span> <span data-ttu-id="bd0d3-114">默认情况下这些都不显示。</span><span class="sxs-lookup"><span data-stu-id="bd0d3-114">They do not appear by default.</span></span>  
  
 <span data-ttu-id="bd0d3-115">有关特定于平面文件架构的节点属性的详细信息，请参阅**平面文件架构的补充节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="bd0d3-115">For detailed information about the node properties that are specific to flat file schemas, see the **Supplemental Node Properties for Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bd0d3-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd0d3-116">See Also</span></span>  
 [<span data-ttu-id="bd0d3-117">不同类型的 BizTalk 架构</span><span class="sxs-lookup"><span data-stu-id="bd0d3-117">Different Types of BizTalk Schemas</span></span>](../core/different-types-of-biztalk-schemas.md)