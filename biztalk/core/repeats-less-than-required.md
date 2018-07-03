---
title: 重复次数小于必需次数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5bebc13-0e70-4f73-99c0-fed917d79fba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f0ca660f792494e66d3ad26ead90f8878d80a0d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974886"
---
# <a name="repeats-less-than-required"></a><span data-ttu-id="a8fff-102">重复次数小于必需次数</span><span class="sxs-lookup"><span data-stu-id="a8fff-102">Repeats less than required</span></span>
## <a name="details"></a><span data-ttu-id="a8fff-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a8fff-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a8fff-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a8fff-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a8fff-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="a8fff-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a8fff-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a8fff-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a8fff-107">事件源</span><span class="sxs-lookup"><span data-stu-id="a8fff-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a8fff-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="a8fff-108"> EDI</span></span> |
|    <span data-ttu-id="a8fff-109">组件</span><span class="sxs-lookup"><span data-stu-id="a8fff-109">Component</span></span>    |                                       <span data-ttu-id="a8fff-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="a8fff-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="a8fff-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="a8fff-111">Symbolic Name</span></span>  |                        <span data-ttu-id="a8fff-112">X12FeRepeatsLessThanRequiredDescription</span><span class="sxs-lookup"><span data-stu-id="a8fff-112">X12FeRepeatsLessThanRequiredDescription</span></span>                         |
|  <span data-ttu-id="a8fff-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="a8fff-113">Message Text</span></span>   |                               <span data-ttu-id="a8fff-114">重复次数小于必需次数</span><span class="sxs-lookup"><span data-stu-id="a8fff-114">Repeats less than required</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="a8fff-115">解释</span><span class="sxs-lookup"><span data-stu-id="a8fff-115">Explanation</span></span>  
 <span data-ttu-id="a8fff-116">此错误/警告/信息事件表明 X12 交换中位于循环内外的段的重复次数小于文档架构所需的次数。</span><span class="sxs-lookup"><span data-stu-id="a8fff-116">This Error/Warning/Information event indicates that segments in an X12 interchange that are either inside or outside of a loop repeated fewer times than required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a8fff-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="a8fff-117">User Action</span></span>  
 <span data-ttu-id="a8fff-118">若要解决此错误，请确保位于交换中某个循环内外的段重复架构中指定的次数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="a8fff-118">To resolve this error, make sure that the segments that are either inside or outside of a loop in the interchange repeat the numbers of times specified in the schema, and then resend the interchange.</span></span>