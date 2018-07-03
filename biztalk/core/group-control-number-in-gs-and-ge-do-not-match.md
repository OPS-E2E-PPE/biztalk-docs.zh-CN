---
title: GS 和 GE 中的组控制编号不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2419f61-2717-4347-a4be-54362330c7e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f162bdcfd76d25a37e196c37c25cbb970fb27155
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993630"
---
# <a name="group-control-number-in-gs-and-ge-do-not-match"></a><span data-ttu-id="ae727-102">GS 和 GE 中的组控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="ae727-102">Group control number in GS and GE do not match</span></span>
## <a name="details"></a><span data-ttu-id="ae727-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ae727-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ae727-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ae727-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ae727-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ae727-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ae727-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ae727-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ae727-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ae727-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ae727-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ae727-108"> EDI</span></span> |
|    <span data-ttu-id="ae727-109">组件</span><span class="sxs-lookup"><span data-stu-id="ae727-109">Component</span></span>    |                                       <span data-ttu-id="ae727-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="ae727-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="ae727-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ae727-111">Symbolic Name</span></span>  |                         <span data-ttu-id="ae727-112">X12FaControlNumberMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="ae727-112">X12FaControlNumberMismatchDescription</span></span>                          |
|  <span data-ttu-id="ae727-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ae727-113">Message Text</span></span>   |                     <span data-ttu-id="ae727-114">GS 和 GE 中的组控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="ae727-114">Group control number in GS and GE do not match</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="ae727-115">解释</span><span class="sxs-lookup"><span data-stu-id="ae727-115">Explanation</span></span>  
 <span data-ttu-id="ae727-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为交换的 GS06 和 GE02 字段中包含的控制编号具有不同的值。</span><span class="sxs-lookup"><span data-stu-id="ae727-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the control numbers contained in the GS06 and GE02 fields of the  interchange do not have the same value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ae727-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="ae727-117">User Action</span></span>  
 <span data-ttu-id="ae727-118">若要解决此错误，请确保交换的 GS06 和 GE02 字段中包含的组控制编号具有相同的值，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="ae727-118">To resolve this error, make sure that the group control numbers contained in the GS06 and GE02 fields of the interchange have the same value, and then have the interchange resent.</span></span>