---
title: 事务集预告片缺少 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07753300-fe47-47a6-a947-6abec10c1c90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7f1c153aa0bb62b6c62f4eeebf9d1fb9bea004b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279285"
---
# <a name="transaction-set-trailer-missing"></a><span data-ttu-id="7a5db-102">事务集尾部缺失</span><span class="sxs-lookup"><span data-stu-id="7a5db-102">Transaction Set Trailer Missing</span></span>
## <a name="details"></a><span data-ttu-id="7a5db-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7a5db-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7a5db-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7a5db-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7a5db-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7a5db-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7a5db-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7a5db-106">Event ID</span></span>|-|  
|<span data-ttu-id="7a5db-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7a5db-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7a5db-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7a5db-108"> EDI</span></span>|  
|<span data-ttu-id="7a5db-109">组件</span><span class="sxs-lookup"><span data-stu-id="7a5db-109">Component</span></span>|<span data-ttu-id="7a5db-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="7a5db-110">EDI Engine</span></span>|  
|<span data-ttu-id="7a5db-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7a5db-111">Symbolic Name</span></span>|<span data-ttu-id="7a5db-112">X12TsTrailerMissingDescription</span><span class="sxs-lookup"><span data-stu-id="7a5db-112">X12TsTrailerMissingDescription</span></span>|  
|<span data-ttu-id="7a5db-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="7a5db-113">Message Text</span></span>|<span data-ttu-id="7a5db-114">事务集尾部缺失</span><span class="sxs-lookup"><span data-stu-id="7a5db-114">Transaction Set Trailer Missing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7a5db-115">解释</span><span class="sxs-lookup"><span data-stu-id="7a5db-115">Explanation</span></span>  
 <span data-ttu-id="7a5db-116">此错误/警告/信息事件表明接收管道无法处理传入的事务集或发送管道无法处理传出的事务集，因为该事务集不包含 SE 事务集尾部（对于 X12 事务集）或 UNT 消息尾部（对于 EDIFACT 事务集）。</span><span class="sxs-lookup"><span data-stu-id="7a5db-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming transaction set or the send pipeline could not process the outgoing transaction set because the transaction set did not include the SE transaction set trailer (for X12 transaction sets) or the UNT message trailer (for EDIFACT transaction sets).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7a5db-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="7a5db-117">User Action</span></span>  
 <span data-ttu-id="7a5db-118">若要解决此错误，请让事务集的发送方向事务集中添加一个 SE 事务集尾部（对于 X12 事务集）或 UNT 消息尾部（对于 EDIFACT 事务集），然后重新发送事务集。</span><span class="sxs-lookup"><span data-stu-id="7a5db-118">To resolve this error, have the sender of the transaction set add to the transaction set an SE transaction set trailer (for X12 transaction sets) or the UNT message trailer (for EDIFACT transaction sets), and then resend the transaction set.</span></span>