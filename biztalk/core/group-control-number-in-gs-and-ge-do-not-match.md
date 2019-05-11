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
ms.openlocfilehash: 0d2e08bf3520b1a1b10abd66059e037fe258ec3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344886"
---
# <a name="group-control-number-in-gs-and-ge-do-not-match"></a><span data-ttu-id="84b68-102">GS 和 GE 中的组控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="84b68-102">Group control number in GS and GE do not match</span></span>
## <a name="details"></a><span data-ttu-id="84b68-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="84b68-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="84b68-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="84b68-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="84b68-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="84b68-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="84b68-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="84b68-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="84b68-107">事件源</span><span class="sxs-lookup"><span data-stu-id="84b68-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="84b68-108">EDI</span><span class="sxs-lookup"><span data-stu-id="84b68-108">EDI</span></span> |
|    <span data-ttu-id="84b68-109">组件</span><span class="sxs-lookup"><span data-stu-id="84b68-109">Component</span></span>    |                                       <span data-ttu-id="84b68-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="84b68-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="84b68-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="84b68-111">Symbolic Name</span></span>  |                         <span data-ttu-id="84b68-112">X12FaControlNumberMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="84b68-112">X12FaControlNumberMismatchDescription</span></span>                          |
|  <span data-ttu-id="84b68-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="84b68-113">Message Text</span></span>   |                     <span data-ttu-id="84b68-114">GS 和 GE 中的组控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="84b68-114">Group control number in GS and GE do not match</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="84b68-115">解释</span><span class="sxs-lookup"><span data-stu-id="84b68-115">Explanation</span></span>  
 <span data-ttu-id="84b68-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为交换的 GS06 和 GE02 字段中包含的控制编号具有不同的值。</span><span class="sxs-lookup"><span data-stu-id="84b68-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the control numbers contained in the GS06 and GE02 fields of the  interchange do not have the same value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="84b68-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="84b68-117">User Action</span></span>  
 <span data-ttu-id="84b68-118">若要解决此错误，请确保交换的 GS06 和 GE02 字段中包含的组控制编号具有相同的值，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="84b68-118">To resolve this error, make sure that the group control numbers contained in the GS06 and GE02 fields of the interchange have the same value, and then have the interchange resent.</span></span>