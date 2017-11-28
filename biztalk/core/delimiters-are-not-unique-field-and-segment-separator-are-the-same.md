---
title: "分隔符不唯一，是相同的字段和段分隔符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1441434a-e969-4803-8e44-c7738d9b23ed
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 440ffb1213936fba4b08a8ee478f6c141eba38fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="delimiters-are-not-unique-field-and-segment-separator-are-the-same"></a><span data-ttu-id="556b5-102">分隔符不唯一，字段和段分隔符相同</span><span class="sxs-lookup"><span data-stu-id="556b5-102">Delimiters are not unique, field and segment separator are the same</span></span>
## <a name="details"></a><span data-ttu-id="556b5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="556b5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="556b5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="556b5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="556b5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="556b5-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="556b5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="556b5-106">Event ID</span></span>|-|  
|<span data-ttu-id="556b5-107">事件源</span><span class="sxs-lookup"><span data-stu-id="556b5-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="556b5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="556b5-108"> EDI</span></span>|  
|<span data-ttu-id="556b5-109">组件</span><span class="sxs-lookup"><span data-stu-id="556b5-109">Component</span></span>|<span data-ttu-id="556b5-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="556b5-110">EDI Engine</span></span>|  
|<span data-ttu-id="556b5-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="556b5-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="556b5-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="556b5-112">Message Text</span></span>|<span data-ttu-id="556b5-113">分隔符不唯一，字段和段分隔符相同</span><span class="sxs-lookup"><span data-stu-id="556b5-113">Delimiters are not unique, field and segment separator are the same</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="556b5-114">解释</span><span class="sxs-lookup"><span data-stu-id="556b5-114">Explanation</span></span>  
 <span data-ttu-id="556b5-115">此错误/警告/信息事件表明 EDI 发送管道无法处理传出的交换，因为数据元素和段分隔符是相同的值。</span><span class="sxs-lookup"><span data-stu-id="556b5-115">This Error/Warning/Information event indicates that the EDI send pipeline could not process an outgoing interchange because the data element and segment separators were the same value.</span></span> <span data-ttu-id="556b5-116">在 X12 交换中，数据元素分隔符是 ISA 段的第四个字符位置中的字符，段终止符是 ISA 段的最后一个字符位置中的字符。</span><span class="sxs-lookup"><span data-stu-id="556b5-116">In an X12 interchange, the data element separator is the character in the fourth character position of the ISA segment and the segment terminator is the character in the last character position of the ISA segment.</span></span> <span data-ttu-id="556b5-117">在 EDIFACT 交换中，数据元素分隔符是 UNA2 字段中的字符，段终止符是 UNA6 字段中的字符。</span><span class="sxs-lookup"><span data-stu-id="556b5-117">In an EDIFACT interchange, the data element separator is the character in the UNA2 field and the segment terminator is the character in the UNA6 field.</span></span> <span data-ttu-id="556b5-118">保留的批方案中可能会发生两个分隔符具有相同值的情况（但这会导致错误），或者如果交换通过直通传输接收，然后由发送端口选取作为 MessageBox 中的 XML 文件，也可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="556b5-118">Two separators with the same value can occur (but will cause an error condition) in a preserved batch scenario, or if an interchange is received via a passthrough transmit and then picked up by the send port as an XML file in the MessageBox.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="556b5-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="556b5-119">User Action</span></span>  
 <span data-ttu-id="556b5-120">若要解决此错误，请更改交换中数据元素或段分隔符的值，然后重新提交交换。</span><span class="sxs-lookup"><span data-stu-id="556b5-120">To resolve this error, change the value of either the data element or segment separator in the interchange, and then resubmit the interchange.</span></span>