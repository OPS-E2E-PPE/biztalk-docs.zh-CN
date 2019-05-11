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
ms.openlocfilehash: bb28a11b7f13ab12819bc474af26653051c112bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397911"
---
# <a name="repeats-less-than-required"></a><span data-ttu-id="98618-102">重复次数小于必需次数</span><span class="sxs-lookup"><span data-stu-id="98618-102">Repeats less than required</span></span>
## <a name="details"></a><span data-ttu-id="98618-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="98618-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="98618-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="98618-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="98618-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="98618-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="98618-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="98618-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="98618-107">事件源</span><span class="sxs-lookup"><span data-stu-id="98618-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="98618-108">EDI</span><span class="sxs-lookup"><span data-stu-id="98618-108">EDI</span></span> |
|    <span data-ttu-id="98618-109">组件</span><span class="sxs-lookup"><span data-stu-id="98618-109">Component</span></span>    |                                       <span data-ttu-id="98618-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="98618-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="98618-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="98618-111">Symbolic Name</span></span>  |                        <span data-ttu-id="98618-112">X12FeRepeatsLessThanRequiredDescription</span><span class="sxs-lookup"><span data-stu-id="98618-112">X12FeRepeatsLessThanRequiredDescription</span></span>                         |
|  <span data-ttu-id="98618-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="98618-113">Message Text</span></span>   |                               <span data-ttu-id="98618-114">重复次数小于必需次数</span><span class="sxs-lookup"><span data-stu-id="98618-114">Repeats less than required</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="98618-115">解释</span><span class="sxs-lookup"><span data-stu-id="98618-115">Explanation</span></span>  
 <span data-ttu-id="98618-116">此错误/警告/信息事件表明 X12 交换中位于循环内外的段的重复次数小于文档架构所需的次数。</span><span class="sxs-lookup"><span data-stu-id="98618-116">This Error/Warning/Information event indicates that segments in an X12 interchange that are either inside or outside of a loop repeated fewer times than required by the document schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="98618-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="98618-117">User Action</span></span>  
 <span data-ttu-id="98618-118">若要解决此错误，请确保位于交换中某个循环内外的段重复架构中指定的次数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="98618-118">To resolve this error, make sure that the segments that are either inside or outside of a loop in the interchange repeat the numbers of times specified in the schema, and then resend the interchange.</span></span>