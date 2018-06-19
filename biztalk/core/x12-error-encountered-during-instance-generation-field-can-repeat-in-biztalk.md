---
title: 字段可以重复实例生成-期间遇到错误，但尚未定义重复分隔符 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7a6783c-cb35-4ce8-9164-ec34ae500de1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 366caec69fd84b91cf815a58e4975e8e5d7b4d06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290101"
---
# <a name="error-encountered-during-instance-generation--field-can-repeat-but-repetition-delimiter-has-not-been-defined"></a><span data-ttu-id="a85a6-102">实例生成期间遇到错误 - 字段可以重复，但尚未定义重复分隔符</span><span class="sxs-lookup"><span data-stu-id="a85a6-102">Error encountered during instance generation--field can repeat but repetition delimiter has not been defined</span></span>
## <a name="details"></a><span data-ttu-id="a85a6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a85a6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a85a6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a85a6-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a85a6-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="a85a6-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a85a6-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a85a6-106">Event ID</span></span>|-|  
|<span data-ttu-id="a85a6-107">事件源</span><span class="sxs-lookup"><span data-stu-id="a85a6-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a85a6-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="a85a6-108"> EDI</span></span>|  
|<span data-ttu-id="a85a6-109">组件</span><span class="sxs-lookup"><span data-stu-id="a85a6-109">Component</span></span>|<span data-ttu-id="a85a6-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="a85a6-110">EDI Engine</span></span>|  
|<span data-ttu-id="a85a6-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="a85a6-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="a85a6-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="a85a6-112">Message Text</span></span>|<span data-ttu-id="a85a6-113">实例生成期间遇到错误。</span><span class="sxs-lookup"><span data-stu-id="a85a6-113">Error encountered during instance generation.</span></span> <span data-ttu-id="a85a6-114">字段 {0} 可以重复，但尚未定义重复分隔符。</span><span class="sxs-lookup"><span data-stu-id="a85a6-114">The field {0} can repeat but repetition delimiter has not been defined.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a85a6-115">解释</span><span class="sxs-lookup"><span data-stu-id="a85a6-115">Explanation</span></span>  
 <span data-ttu-id="a85a6-116">此错误/警告/信息事件表明 BizTalk Server 无法生成 X12 消息实例，因为指出的字段可以重复（如架构所指定的那样），但尚未定义重复分隔符。</span><span class="sxs-lookup"><span data-stu-id="a85a6-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an X12 message instance because the indicated field can repeat (as specified by the schema), but no repetition separator has been defined.</span></span> <span data-ttu-id="a85a6-117">当架构中某个字段的 minOccurs 大于 1，但已定义了标准标识符而非重复分隔符时会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="a85a6-117">This occurs when a field in the schema has minOccurs equal to more than 1, but a Standard identifier has been defined, rather than a Repetition separator.</span></span> <span data-ttu-id="a85a6-118">（对于 EDIFACT 交换，默认情况下定义了重复分隔符。）</span><span class="sxs-lookup"><span data-stu-id="a85a6-118">(For EDIFACT interchanges, a repetition separator is defined by default.)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a85a6-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="a85a6-119">User Action</span></span>  
 <span data-ttu-id="a85a6-120">若要解决此错误，请在作为交换接收方的参与方的“ISA 段定义”页中为 ISA11 选择重复分隔符而非标准标识符，然后输入用作分隔符的字符。</span><span class="sxs-lookup"><span data-stu-id="a85a6-120">To resolve this error, select Repetition separator rather than Standard identifier for ISA11 in the ISA Segment Definition page for the party as interchange receiver, and enter a character for the separator.</span></span> <span data-ttu-id="a85a6-121">如果尚未为交换解析任何参与方，则在全局属性的“ISA 段定义”页中定义重复分隔符（对于 X12 交换）。</span><span class="sxs-lookup"><span data-stu-id="a85a6-121">If no party has been resolved for the interchange, define the repetition separator in the ISA Segment Definition page of the global properties (for X12 interchanges).</span></span>