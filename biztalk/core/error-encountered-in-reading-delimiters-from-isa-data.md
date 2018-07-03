---
title: 中从 ISA 数据读取分隔符时遇到错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8cb60abd-53c8-45e1-a840-d27dc974aad7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3cb0dac30c18cb2c6da9c5a57818ce301fe95ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015734"
---
# <a name="error-encountered-in-reading-delimiters-from-isa-data"></a><span data-ttu-id="5cb27-102">读取 ISA 数据中的分隔符时遇到错误</span><span class="sxs-lookup"><span data-stu-id="5cb27-102">Error encountered in reading delimiters from ISA data</span></span>
## <a name="details"></a><span data-ttu-id="5cb27-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5cb27-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="5cb27-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5cb27-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="5cb27-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="5cb27-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="5cb27-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5cb27-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="5cb27-107">事件源</span><span class="sxs-lookup"><span data-stu-id="5cb27-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="5cb27-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="5cb27-108"> EDI</span></span> |
|    <span data-ttu-id="5cb27-109">组件</span><span class="sxs-lookup"><span data-stu-id="5cb27-109">Component</span></span>    |                                       <span data-ttu-id="5cb27-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="5cb27-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="5cb27-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="5cb27-111">Symbolic Name</span></span>  |                                     <span data-ttu-id="5cb27-112">InvalidIsaData</span><span class="sxs-lookup"><span data-stu-id="5cb27-112">InvalidIsaData</span></span>                                     |
|  <span data-ttu-id="5cb27-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="5cb27-113">Message Text</span></span>   |                 <span data-ttu-id="5cb27-114">读取 ISA 数据中的分隔符时遇到错误</span><span class="sxs-lookup"><span data-stu-id="5cb27-114">Error encountered in reading delimiters from ISA data</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="5cb27-115">解释</span><span class="sxs-lookup"><span data-stu-id="5cb27-115">Explanation</span></span>  
 <span data-ttu-id="5cb27-116">此错误/警告/信息事件表明 EDI 接收管道在处理传入的 X12 交换时遇到错误，因为它无法解析 ISA 段中的分隔符。</span><span class="sxs-lookup"><span data-stu-id="5cb27-116">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when processing an incoming X12 interchange because it could not parse the separators from the ISA segment.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5cb27-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="5cb27-117">User Action</span></span>  
 <span data-ttu-id="5cb27-118">若要解决此错误，请验证传入交换的 ISA 段中的分隔符是否唯一且有效。</span><span class="sxs-lookup"><span data-stu-id="5cb27-118">To resolve this error, verify that the separators in the ISA segment of the incoming interchange are unique and valid.</span></span> <span data-ttu-id="5cb27-119">如果不是，则交换的发送方在每个分隔符字段（重复分隔符的 ISA11 段和组件分隔符的 ISA16 段）输入唯一且有效的值，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="5cb27-119">If not, have the sender of the interchange enter unique and valid values into each of the separator fields (the ISA11 segment for the repetition separator and the ISA16 segment for the component separator), and then resend the interchange.</span></span>