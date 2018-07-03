---
title: 无效的分隔符集，因为至少一个分隔符在允许的范围之外 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1286559-765b-4728-945d-cf3386e1ba06
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a54467c6d611aefd58d2dfd51c21974c3a5df7c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022507"
---
# <a name="invalid-delimiter-set-because-at-least-one-of-the-delimiters-is-outside-the-allowed-range"></a><span data-ttu-id="e8245-102">分隔符设置无效，因为至少有一个分隔符在允许的范围之外</span><span class="sxs-lookup"><span data-stu-id="e8245-102">Invalid delimiter set because at least one of the delimiters is outside the allowed range</span></span>
## <a name="details"></a><span data-ttu-id="e8245-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e8245-103">Details</span></span>  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e8245-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e8245-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| <span data-ttu-id="e8245-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e8245-105">Product Version</span></span> |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    <span data-ttu-id="e8245-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e8245-106">Event ID</span></span>     |                                                   -                                                    |
|  <span data-ttu-id="e8245-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e8245-107">Event Source</span></span>   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e8245-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e8245-108"> EDI</span></span>         |
|    <span data-ttu-id="e8245-109">组件</span><span class="sxs-lookup"><span data-stu-id="e8245-109">Component</span></span>    |                                               <span data-ttu-id="e8245-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e8245-110">EDI Engine</span></span>                                               |
|  <span data-ttu-id="e8245-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e8245-111">Symbolic Name</span></span>  |                                          <span data-ttu-id="e8245-112">DelimiterOutOfRange</span><span class="sxs-lookup"><span data-stu-id="e8245-112">DelimiterOutOfRange</span></span>                                           |
|  <span data-ttu-id="e8245-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="e8245-113">Message Text</span></span>   | <span data-ttu-id="e8245-114">无效的分隔符集{0}，至少有一个分隔符是 0 到 127 的允许的范围之外</span><span class="sxs-lookup"><span data-stu-id="e8245-114">Invalid delimiter set {0}, atleast one of the delimiters is outside the allowed range of 0 through 127</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e8245-115">解释</span><span class="sxs-lookup"><span data-stu-id="e8245-115">Explanation</span></span>  
 <span data-ttu-id="e8245-116">此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为在交换中的一个或多个包含超出范围的 ASCII 字符中的值设置。</span><span class="sxs-lookup"><span data-stu-id="e8245-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because one or more separators in the interchange was outside the range of values in the ASCII character set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e8245-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="e8245-117">User Action</span></span>  
 <span data-ttu-id="e8245-118">若要解决此错误，请确保交换中的每个分隔符都在 ASCII 字符集中，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="e8245-118">To resolve this error, make sure that each separator in the interchange is in the ASCII character set, and then have the interchange resent.</span></span>