---
title: 包含的段数不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c868de02-fda7-4d84-be50-2c08cde0450c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 418f81c895660c93ebdb26924d0a279ccd46e72f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325156"
---
# <a name="number-of-included-segments-do-not-match"></a><span data-ttu-id="54b80-102">包括的段的数目不匹配</span><span class="sxs-lookup"><span data-stu-id="54b80-102">Number of included segments do not match</span></span>
## <a name="details"></a><span data-ttu-id="54b80-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="54b80-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="54b80-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="54b80-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="54b80-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="54b80-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="54b80-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="54b80-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="54b80-107">事件源</span><span class="sxs-lookup"><span data-stu-id="54b80-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="54b80-108">EDI</span><span class="sxs-lookup"><span data-stu-id="54b80-108">EDI</span></span> |
|    <span data-ttu-id="54b80-109">组件</span><span class="sxs-lookup"><span data-stu-id="54b80-109">Component</span></span>    |                                       <span data-ttu-id="54b80-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="54b80-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="54b80-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="54b80-111">Symbolic Name</span></span>  |                        <span data-ttu-id="54b80-112">X12TsIncludedSegCountMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="54b80-112">X12TsIncludedSegCountMismatchDescription</span></span>                        |
|  <span data-ttu-id="54b80-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="54b80-113">Message Text</span></span>   |                        <span data-ttu-id="54b80-114">包括的段的数目不匹配</span><span class="sxs-lookup"><span data-stu-id="54b80-114">Number of included segments do not match</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="54b80-115">解释</span><span class="sxs-lookup"><span data-stu-id="54b80-115">Explanation</span></span>  
 <span data-ttu-id="54b80-116">此错误/警告/信息事件表明 X12 交换的事务集中的段数不等于事务集尾部中的数量（SE01 字段）。</span><span class="sxs-lookup"><span data-stu-id="54b80-116">This Error/Warning/Information event indicates that the number of segments in the transaction set of the X12 interchange does not equal the number in the transaction set trailer (SE01 field).</span></span> <span data-ttu-id="54b80-117">保留交换并且出错时挂起交换时会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="54b80-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="54b80-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="54b80-118">User Action</span></span>  
 <span data-ttu-id="54b80-119">若要解决此错误，请确保交换尾部的 SE01 字段中的数量与事务集中的段数相同，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="54b80-119">To resolve this error, make sure that the number in the SE01 field of the interchange trailer is the same as the number of segments in the transaction set, and then resend the interchange.</span></span>