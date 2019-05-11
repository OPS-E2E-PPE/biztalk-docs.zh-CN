---
title: 循环重复小于允许的最小次数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0be21d1d-86da-456b-83e6-c91f1dc9fb48
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27188ecbf45cb147d718a7349c123ce195c4a1a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380502"
---
# <a name="loop-repeats-less-than-the-minimum-allowed-number-of-times"></a><span data-ttu-id="3e9f5-102">循环重复次数小于允许的最小时间数</span><span class="sxs-lookup"><span data-stu-id="3e9f5-102">Loop repeats less than the minimum allowed number of times</span></span>
## <a name="details"></a><span data-ttu-id="3e9f5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3e9f5-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="3e9f5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3e9f5-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="3e9f5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="3e9f5-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="3e9f5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3e9f5-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="3e9f5-107">事件源</span><span class="sxs-lookup"><span data-stu-id="3e9f5-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3e9f5-108">EDI</span><span class="sxs-lookup"><span data-stu-id="3e9f5-108">EDI</span></span> |
|    <span data-ttu-id="3e9f5-109">组件</span><span class="sxs-lookup"><span data-stu-id="3e9f5-109">Component</span></span>    |                                       <span data-ttu-id="3e9f5-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="3e9f5-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="3e9f5-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="3e9f5-111">Symbolic Name</span></span>  |                          <span data-ttu-id="3e9f5-112">X12SeLoopRepeatsLessTimesDescription</span><span class="sxs-lookup"><span data-stu-id="3e9f5-112">X12SeLoopRepeatsLessTimesDescription</span></span>                          |
|  <span data-ttu-id="3e9f5-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="3e9f5-113">Message Text</span></span>   |               <span data-ttu-id="3e9f5-114">循环重复次数小于允许的最小时间数</span><span class="sxs-lookup"><span data-stu-id="3e9f5-114">Loop repeats less than the minimum allowed number of times</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="3e9f5-115">解释</span><span class="sxs-lookup"><span data-stu-id="3e9f5-115">Explanation</span></span>  
 <span data-ttu-id="3e9f5-116">此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为该交换包含一个重复次数小于消息架构所需的最小次数的循环。</span><span class="sxs-lookup"><span data-stu-id="3e9f5-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained a loop that repeated fewer times than the minimum number of times required by the message schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3e9f5-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="3e9f5-117">User Action</span></span>  
 <span data-ttu-id="3e9f5-118">若要解决此错误，请确保循环重复交换中至少为消息架构中的循环指定的 minOccurs 属性的最大次数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="3e9f5-118">To resolve this error, make sure that the loop repeats in the interchange at least the number of times in the minOccurs property specified for the loop in the message schema, and then have the interchange resent.</span></span>