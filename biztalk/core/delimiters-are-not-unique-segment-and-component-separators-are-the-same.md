---
title: 分隔符不唯一，段和组件分隔符相同 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13c41899-02af-4678-a4ad-f3dc48c1fdfb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6068b13502b8893fd5065957b6dd73072236126
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983774"
---
# <a name="delimiters-are-not-unique-segment-and-component-separators-are-the-same"></a><span data-ttu-id="504ff-102">分隔符不唯一，段和组件分隔符相同</span><span class="sxs-lookup"><span data-stu-id="504ff-102">Delimiters are not unique, segment and component separators are the same</span></span>
## <a name="details"></a><span data-ttu-id="504ff-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="504ff-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="504ff-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="504ff-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="504ff-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="504ff-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="504ff-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="504ff-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="504ff-107">事件源</span><span class="sxs-lookup"><span data-stu-id="504ff-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="504ff-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="504ff-108"> EDI</span></span> |
|    <span data-ttu-id="504ff-109">组件</span><span class="sxs-lookup"><span data-stu-id="504ff-109">Component</span></span>    |                                       <span data-ttu-id="504ff-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="504ff-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="504ff-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="504ff-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="504ff-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="504ff-112">Message Text</span></span>   |        <span data-ttu-id="504ff-113">分隔符不唯一，段和组件分隔符相同</span><span class="sxs-lookup"><span data-stu-id="504ff-113">Delimiters are not unique, segment and component separators are the same</span></span>        |
  
## <a name="explanation"></a><span data-ttu-id="504ff-114">解释</span><span class="sxs-lookup"><span data-stu-id="504ff-114">Explanation</span></span>  
 <span data-ttu-id="504ff-115">此错误/警告/信息事件表明 EDI 发送管道无法处理传出交换，因为段终止符或组件分隔符是相同的值。</span><span class="sxs-lookup"><span data-stu-id="504ff-115">This Error/Warning/Information event indicates that the EDI send pipeline could not process an outgoing interchange because the segment terminator or the component separator were the same value.</span></span> <span data-ttu-id="504ff-116">在 X12 交换中，段终止符是处于 ISA 段中最后一个字符位置的字符，组件分隔符是 ISA16 字段中的字符。</span><span class="sxs-lookup"><span data-stu-id="504ff-116">In an X12 interchange, the segment terminator is character in the last character position of the ISA segment and the component separator is the character in the ISA16 field.</span></span> <span data-ttu-id="504ff-117">在 EDIFACT 交换中，段终止符是 UNA6 字段中的字符，组件分隔符是 UNA1 字段中的字符。</span><span class="sxs-lookup"><span data-stu-id="504ff-117">In an EDIFACT interchange, the segment terminator is the character in the UNA6 field and the component separator is the character in the UNA1 field.</span></span> <span data-ttu-id="504ff-118">保留的批方案中可能会发生两个分隔符具有相同值的情况（但这会导致错误），或者如果交换通过直通传输接收，然后由发送端口选取作为 MessageBox 中的 XML 文件，也可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="504ff-118">Two separators with the same value can occur (but will cause an error condition) in a preserved batch scenario, or if an interchange is received via a passthrough transmit and then picked up by the send port as an XML file in the MessageBox.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="504ff-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="504ff-119">User Action</span></span>  
 <span data-ttu-id="504ff-120">若要解决此错误，请更改交换中段终止符或组件分隔符的值，然后重新提交交换。</span><span class="sxs-lookup"><span data-stu-id="504ff-120">To resolve this error, change the value of either the segment terminator or the component separator in the interchange, and then resubmit the interchange.</span></span>