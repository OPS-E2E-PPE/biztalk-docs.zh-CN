---
title: EDI 交换结构化元素 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03f47ae2-fa0f-4d88-a700-85f3d515d2d0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc07ae40a3665b47b446b61e24954ca9c588a6a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239525"
---
# <a name="edi-interchange-structural-element"></a><span data-ttu-id="8e6fc-102">EDI 交换结构元素</span><span class="sxs-lookup"><span data-stu-id="8e6fc-102">EDI Interchange Structural Element</span></span>
<span data-ttu-id="8e6fc-103">交换是 EDI 消息的最高级别的结构元素。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-103">The interchange is the highest-level structural element of an EDI message.</span></span> <span data-ttu-id="8e6fc-104">它包含由两个合作伙伴交换的一个或多个组的集合。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-104">It contains a collection of one or more groups exchanged by two partners.</span></span> <span data-ttu-id="8e6fc-105">交换的目标必须是一个贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-105">The destination of an interchange must be a single trading partner.</span></span> <span data-ttu-id="8e6fc-106">交换可能包含一种或多种类型的事务集/消息。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-106">Interchanges may contain transaction sets/message of one or more than one type.</span></span>  
  
 <span data-ttu-id="8e6fc-107">使用交换时，交换自身以及其中的组和事务集/消息由标头定义。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-107">With an interchange, the interchange itself and the groups and transaction sets/messages within it are defined by headers.</span></span> <span data-ttu-id="8e6fc-108">段、数据元素和子元素由分隔符分隔。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-108">Segments, data elements, and sub-elements are delimited by separators.</span></span> <span data-ttu-id="8e6fc-109">每个分隔符都有一个默认值，但可以为参与方定义其他字符。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-109">Each separator has a default value, but may be defined as a different character for the party.</span></span> <span data-ttu-id="8e6fc-110">在 EDIFACT 交换中，在交换中用作分隔符的所选字符是在单独的 UNA 交换标头中定义的。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-110">In EDIFACT interchanges, the characters selected for use as separators in the interchange are defined in a separate UNA Interchange Header.</span></span> <span data-ttu-id="8e6fc-111">而在 X12 交换中，分隔符是在 ISA 交换标头中定义的。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-111">In X12 interchanges, separators are defined in the ISA Interchange Header.</span></span> <span data-ttu-id="8e6fc-112">请注意，在 X12 中，数据元素分隔符是位于第四个字符位置的字符，数据段终止符是位于最后一个字符位置的字符。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-112">Note that in X12, the data element separator is the character in the fourth character position, and the data segment terminator is the character in the last character position.</span></span> <span data-ttu-id="8e6fc-113">其他 X12 分隔符和全部 EDIFACT 分隔符由字段定义，例如 X12 组件分隔符由 ISA16 字段定义，EDIFACT 数据元素分隔符由 UNA2 字段定义。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-113">The other X12 separators and all the EDIFACT separators are defined by fields, such as the X12 component separator by the ISA16 field and the EDIFACT data element separator by the UNA2 field.</span></span>  
  
 <span data-ttu-id="8e6fc-114">交换包括一个用于定义 EDI 消息的信封。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-114">The interchange includes an envelope that defines the EDI message.</span></span> <span data-ttu-id="8e6fc-115">该信封必须以交换标头（X12 中的 ISA 或 EDIFACT 中的 UNA/UNB）开头，且必须以交换尾部 (IEA/UNZ) 结束。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-115">The envelope must start with an Interchange Header (ISA in X12 or UNA/UNB in EDIFACT), and it must end with an Interchange Trailer (IEA/UNZ).</span></span> <span data-ttu-id="8e6fc-116">交换标头包括定义以下各项的元素：发送方和接收方、日期和时间、版本号、与标头和尾部匹配的控制编号以及其他信息。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-116">The Interchange Header includes elements defining the sender and receiver, a date and time, a version number, a control number that matches the header and the trailer, and other information.</span></span>  
  
 <span data-ttu-id="8e6fc-117">ISA12 和 GS8 字段（对于 X12 交换）和 UNH2 字段（对于 EDIFACT 交换）包含发现架构所必需的版本信息。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-117">The ISA12 and GS8 fields (for X12 interchanges) and the UNH2 field (for EDIFACT interchanges) contain version information that is required for schema discovery.</span></span>  
  
 <span data-ttu-id="8e6fc-118">交换尾部具有指示交换中的组数的元素。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-118">The Interchange Trailer has an element that indicates the number of groups within the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e6fc-119">功能安全标头、功能保证标头、功能安全值段和功能安全尾部段均超出 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 的范围。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-119">The functional security header, functional assurance header, functional security value segment, and functional security trailer segments are beyond the scope of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2.</span></span> <span data-ttu-id="8e6fc-120">如果收到具有这些段的交换，则会挂起交换并显示错误日志，指示无法识别这些段。</span><span class="sxs-lookup"><span data-stu-id="8e6fc-120">If an interchange with these segments is received, it will be suspended with an error log indicating that these are unidentified segments.</span></span>