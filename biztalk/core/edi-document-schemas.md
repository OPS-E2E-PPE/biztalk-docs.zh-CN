---
title: EDI 文档架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc3a30b8-0686-4c06-985b-13f2c95f8e99
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebe89a18538cb09c88ecb3098ca556c75422c803
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530805"
---
# <a name="edi-document-schemas"></a><span data-ttu-id="0fb44-102">EDI 文档架构</span><span class="sxs-lookup"><span data-stu-id="0fb44-102">EDI Document Schemas</span></span>
<span data-ttu-id="0fb44-103">文档架构用于定义 EDI 事务文档类型的正文。</span><span class="sxs-lookup"><span data-stu-id="0fb44-103">Document schemas define the body of an EDI transaction document type.</span></span>  
  
## <a name="schema-delivery-and-setup"></a><span data-ttu-id="0fb44-104">架构送达与安装程序</span><span class="sxs-lookup"><span data-stu-id="0fb44-104">Schema Delivery and Setup</span></span>  
 <span data-ttu-id="0fb44-105">EDI 文档架构中的自解压缩可执行文件，采用压缩形式传递[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe。</span><span class="sxs-lookup"><span data-stu-id="0fb44-105">EDI document schemas are delivered in a compressed state in a self-extracting executable, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe.</span></span> <span data-ttu-id="0fb44-106">自解压缩可执行文件可确保适当的文件夹结构创建 （按照编码类型和版本/发行版子类型）。</span><span class="sxs-lookup"><span data-stu-id="0fb44-106">The self-extracting executable ensures that an appropriate folder structure is created (per the encoding type and version/release sub types).</span></span> <span data-ttu-id="0fb44-107">可执行文件执行时，它 EANCOM、 EDIFACT、 HIPAA 和 X12 架构与可执行文件相同的目录的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0fb44-107">When executed, the executable deposits EANCOM, EDIFACT, HIPAA, and X12 schemas into subfolders in the same directory as the executable.</span></span>  
  
 <span data-ttu-id="0fb44-108">默认架构命名空间包括：</span><span class="sxs-lookup"><span data-stu-id="0fb44-108">The default schema namespaces are:</span></span>  
  
-   <span data-ttu-id="0fb44-109">对于 X12 – `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`</span><span class="sxs-lookup"><span data-stu-id="0fb44-109">For X12 – `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`</span></span>  
  
-   <span data-ttu-id="0fb44-110">对于 EDIFACT – `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`</span><span class="sxs-lookup"><span data-stu-id="0fb44-110">For EDIFACT – `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`</span></span>  
  
## <a name="schema-naming-convention"></a><span data-ttu-id="0fb44-111">架构命名约定</span><span class="sxs-lookup"><span data-stu-id="0fb44-111">Schema Naming Convention</span></span>  
 <span data-ttu-id="0fb44-112">针对 X12 和 EDIFACT 编码类型的命名约定\<编码\>*\<版本\>\<发布\>\\*  \<Doctype\>。</span><span class="sxs-lookup"><span data-stu-id="0fb44-112">The naming convention for the X12 and EDIFACT encoding type is \<Encoding\>*\<Version\>\<Release\>\\*\<Doctype\>.</span></span> <span data-ttu-id="0fb44-113">示例包括，X12_00401_864.xsd 架构代表 X12 864 文档类型 （版本为 004、 发行版） 和 EDIFACT AUTHOR 文档类型的 EDIFACT_D01C_AUTHOR.xsd 架构 （版本为 D01、 发行版为 C）。</span><span class="sxs-lookup"><span data-stu-id="0fb44-113">Examples are the X12_00401_864.xsd schema for the X12 864 document type (version 004, release 01) and the EDIFACT_D01C_AUTHOR.xsd schema for the EDIFACT AUTHOR document type (version D01, release C).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fb44-114">EDIFACT 架构的架构名称是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0fb44-114">The schema name of an EDIFACT schema is case-sensitive.</span></span> <span data-ttu-id="0fb44-115">例如，EFACT_D98B_ORDERS 与 EFACT_d98B_Orders 将是两个不同的架构。</span><span class="sxs-lookup"><span data-stu-id="0fb44-115">For example, EFACT_D98B_ORDERS and EFACT_d98B_Orders would be two different schemas.</span></span>  
  
## <a name="schema-contents"></a><span data-ttu-id="0fb44-116">架构内容</span><span class="sxs-lookup"><span data-stu-id="0fb44-116">Schema Contents</span></span>  
 <span data-ttu-id="0fb44-117">文档架构以 ST 事务集标头，X12 编码的文档 SE 事务集尾部结尾。</span><span class="sxs-lookup"><span data-stu-id="0fb44-117">A document schema starts with the ST transaction set header and ends with the SE transaction set trailer for an X12-encoded document.</span></span> <span data-ttu-id="0fb44-118">它以 UNH 消息标头，对于 EDIFACT 编码文档 UNT 消息尾部结尾。</span><span class="sxs-lookup"><span data-stu-id="0fb44-118">It starts with the UNH message header and ends with the UNT message trailer for an EDIFACT-encoded document.</span></span> <span data-ttu-id="0fb44-119">该架构定义这些标头和尾部的每个数据元素。</span><span class="sxs-lookup"><span data-stu-id="0fb44-119">The schema defines each data element of these headers and trailers.</span></span>  
  
 <span data-ttu-id="0fb44-120">文档架构则定义事务集/消息中的每个段和这些段中的数据元素。</span><span class="sxs-lookup"><span data-stu-id="0fb44-120">A document schema then defines each segment within the transaction set/message and the data elements within those segments.</span></span> <span data-ttu-id="0fb44-121">例如，X12_00401_864.xsd 架构定义 BMG 段 BMG01、 BMG02 和 BMG03 元素。</span><span class="sxs-lookup"><span data-stu-id="0fb44-121">For example, the X12_00401_864.xsd schema defines the BMG01, BMG02, and BMG03 elements of the BMG segments.</span></span> <span data-ttu-id="0fb44-122">该架构指定段的复杂数据类型，例如字段顺序、 分隔符类型和命名空间的特征。</span><span class="sxs-lookup"><span data-stu-id="0fb44-122">The schema specifies the characteristics of the segment's complex data type, such as the field order, delimiter type, and namespace.</span></span> <span data-ttu-id="0fb44-123">如果有段的跨字段验证规则，该架构定义的规则。</span><span class="sxs-lookup"><span data-stu-id="0fb44-123">If there are cross-field validation rules for the segment, the schema defines the rules.</span></span> <span data-ttu-id="0fb44-124">有关详细信息，请参阅[跨字段-段验证](../core/cross-field-segment-validation.md)。</span><span class="sxs-lookup"><span data-stu-id="0fb44-124">For more information, see [Cross Field-Segment Validation](../core/cross-field-segment-validation.md).</span></span>  
  
 <span data-ttu-id="0fb44-125">该架构指定段，如简单数据类型、 最小出现次数、 最小长度和最大长度内每个数据元素的特征。</span><span class="sxs-lookup"><span data-stu-id="0fb44-125">The schema specifies the characteristics of each data element within the segment, such as the simple data type, minimum occurrences, minimum length, and maximum length.</span></span>  
  
 <span data-ttu-id="0fb44-126">如果消息类型中没有循环，该架构定义内的循环中，每个循环、 最小值和最大出现次数的数据元素和循环是有限或不受限制。</span><span class="sxs-lookup"><span data-stu-id="0fb44-126">If there is a loop in the message type, the schema defines the data elements within each loop, the minimum and maximum occurrences of the loop, and whether the loop is bounded or unbounded.</span></span> <span data-ttu-id="0fb44-127">架构还定义段的嵌套循环是显式或隐式和。</span><span class="sxs-lookup"><span data-stu-id="0fb44-127">The schema also defines nesting of a segment, and whether the loop is explicit or implicit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb44-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fb44-128">See Also</span></span>  
 <span data-ttu-id="0fb44-129">[EDI 消息结构](../core/edi-message-structure.md) </span><span class="sxs-lookup"><span data-stu-id="0fb44-129">[EDI Message Structure](../core/edi-message-structure.md) </span></span>  
 [<span data-ttu-id="0fb44-130">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="0fb44-130">EDI Message Validation</span></span>](../core/edi-message-validation.md)