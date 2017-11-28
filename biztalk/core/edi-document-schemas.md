---
title: "EDI 文档架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc3a30b8-0686-4c06-985b-13f2c95f8e99
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db79e5e4421719a936f68c409c166f9eac38605c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-document-schemas"></a><span data-ttu-id="f0ae5-102">EDI 文档架构</span><span class="sxs-lookup"><span data-stu-id="f0ae5-102">EDI Document Schemas</span></span>
<span data-ttu-id="f0ae5-103">文档架构用于定义 EDI 事务文档类型的正文。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-103">Document schemas define the body of an EDI transaction document type.</span></span>  
  
## <a name="schema-delivery-and-setup"></a><span data-ttu-id="f0ae5-104">架构送达与安装</span><span class="sxs-lookup"><span data-stu-id="f0ae5-104">Schema Delivery and Setup</span></span>  
 <span data-ttu-id="f0ae5-105">EDI 文档架构中的自解压可执行文件中的压缩状态传递[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-105">EDI document schemas are delivered in a compressed state in a self-extracting executable, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe.</span></span> <span data-ttu-id="f0ae5-106">自解压缩可执行文件可确保创建适当的文件夹结构（按照编码类型和版本/发行版子类型）。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-106">The self-extracting executable ensures that an appropriate folder structure is created (per the encoding type and version/release sub types).</span></span> <span data-ttu-id="f0ae5-107">此可执行文件执行时，它会将 EANCOM、EDIFACT、HIPAA 和 X12 架构存储在同一目录的子文件夹中作为可执行文件。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-107">When executed, the executable deposits EANCOM, EDIFACT, HIPAA, and X12 schemas into subfolders in the same directory as the executable.</span></span>  
  
 <span data-ttu-id="f0ae5-108">默认的架构命名空间包括：</span><span class="sxs-lookup"><span data-stu-id="f0ae5-108">The default schema namespaces are:</span></span>  
  
-   <span data-ttu-id="f0ae5-109">对于 X12 – `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`</span><span class="sxs-lookup"><span data-stu-id="f0ae5-109">For X12 – `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`</span></span>  
  
-   <span data-ttu-id="f0ae5-110">对于 EDIFACT – `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`</span><span class="sxs-lookup"><span data-stu-id="f0ae5-110">For EDIFACT – `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`</span></span>  
  
## <a name="schema-naming-convention"></a><span data-ttu-id="f0ae5-111">架构命名约定</span><span class="sxs-lookup"><span data-stu-id="f0ae5-111">Schema Naming Convention</span></span>  
 <span data-ttu-id="f0ae5-112">X12 和 EDIFACT 编码类型的命名约定是\<编码 > _\<版本 >\<版本 >\_\<Doctype >。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-112">The naming convention for the X12 and EDIFACT encoding type is \<Encoding>_\<Version>\<Release>\_\<Doctype>.</span></span> <span data-ttu-id="f0ae5-113">例如，X12_00401_864.xsd 架构代表 X12 864 文档类型（版本为 004、发行版为 01），EDIFACT_D01C_AUTHOR.xsd 架构代表 EDIFACT AUTHOR 文档类型（版本为 D01、发行版为 C）。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-113">Examples are the X12_00401_864.xsd schema for the X12 864 document type (version 004, release 01) and the EDIFACT_D01C_AUTHOR.xsd schema for the EDIFACT AUTHOR document type (version D01, release C).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0ae5-114">EDIFACT 架构的架构名区分大小写。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-114">The schema name of an EDIFACT schema is case-sensitive.</span></span> <span data-ttu-id="f0ae5-115">例如，EFACT_D98B_ORDERS 与 EFACT_d98B_Orders 将是两个不同的架构。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-115">For example, EFACT_D98B_ORDERS and EFACT_d98B_Orders would be two different schemas.</span></span>  
  
## <a name="schema-contents"></a><span data-ttu-id="f0ae5-116">架构内容</span><span class="sxs-lookup"><span data-stu-id="f0ae5-116">Schema Contents</span></span>  
 <span data-ttu-id="f0ae5-117">对于 X12 编码的文档，文档架构以 ST 事务集标头开头，以 SE 事务集尾部结尾。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-117">A document schema starts with the ST transaction set header and ends with the SE transaction set trailer for an X12-encoded document.</span></span> <span data-ttu-id="f0ae5-118">对于 EDIFACT 编码的文档，文档架构以 UNH 消息标头开头，以 UNT 消息尾部结尾。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-118">It starts with the UNH message header and ends with the UNT message trailer for an EDIFACT-encoded document.</span></span> <span data-ttu-id="f0ae5-119">架构将定义这些标头和尾部的每个数据元素。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-119">The schema defines each data element of these headers and trailers.</span></span>  
  
 <span data-ttu-id="f0ae5-120">文档架构则定义事务集/消息中的每个段，以及这些段中的数据元素。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-120">A document schema then defines each segment within the transaction set/message and the data elements within those segments.</span></span> <span data-ttu-id="f0ae5-121">例如，X12_00401_864.xsd 架构定义 BMG 段中的 BMG01、BMG02 和 BMG03 元素。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-121">For example, the X12_00401_864.xsd schema defines the BMG01, BMG02, and BMG03 elements of the BMG segments.</span></span> <span data-ttu-id="f0ae5-122">架构指定段的复杂数据类型的特性，例如字段顺序、分隔符类型和命名空间。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-122">The schema specifies the characteristics of the segment's complex data type, such as the field order, delimiter type, and namespace.</span></span> <span data-ttu-id="f0ae5-123">如果存在针对段的跨字段验证规则，则架构将定义这些规则。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-123">If there are cross-field validation rules for the segment, the schema defines the rules.</span></span> <span data-ttu-id="f0ae5-124">有关详细信息，请参阅[交叉字段段验证](../core/cross-field-segment-validation.md)。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-124">For more information, see [Cross Field-Segment Validation](../core/cross-field-segment-validation.md).</span></span>  
  
 <span data-ttu-id="f0ae5-125">架构指定段内每个数据元素的特性，如简单数据类型、最少出现次数、最小长度及最大长度。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-125">The schema specifies the characteristics of each data element within the segment, such as the simple data type, minimum occurrences, minimum length, and maximum length.</span></span>  
  
 <span data-ttu-id="f0ae5-126">如果消息类型中存在循环，则架构将定义每个循环内的数据元素、循环的最小和最大次数，以及循环是绑定循环还是非绑定循环。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-126">If there is a loop in the message type, the schema defines the data elements within each loop, the minimum and maximum occurrences of the loop, and whether the loop is bounded or unbounded.</span></span> <span data-ttu-id="f0ae5-127">架构还定义段的嵌套，以及循环是显式循环还是隐式循环。</span><span class="sxs-lookup"><span data-stu-id="f0ae5-127">The schema also defines nesting of a segment, and whether the loop is explicit or implicit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ae5-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0ae5-128">See Also</span></span>  
 <span data-ttu-id="f0ae5-129">[EDI 消息结构](../core/edi-message-structure.md) </span><span class="sxs-lookup"><span data-stu-id="f0ae5-129">[EDI Message Structure](../core/edi-message-structure.md) </span></span>  
 [<span data-ttu-id="f0ae5-130">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="f0ae5-130">EDI Message Validation</span></span>](../core/edi-message-validation.md)