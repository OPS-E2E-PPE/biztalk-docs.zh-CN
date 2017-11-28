---
title: "事务集控制编号不匹配 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c4b0c3f-f3be-4c2c-8719-8e40aa7122b9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efd80bac6a5c58306a8d9ca64748ddbb8cb2bc81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-set-control-number-mismatch"></a><span data-ttu-id="e7e8d-102">事务集控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="e7e8d-102">Transaction Set Control Number Mismatch</span></span>
## <a name="details"></a><span data-ttu-id="e7e8d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e7e8d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7e8d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e7e8d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e7e8d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e7e8d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e7e8d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e7e8d-106">Event ID</span></span>|-|  
|<span data-ttu-id="e7e8d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e7e8d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e7e8d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e7e8d-108"> EDI</span></span>|  
|<span data-ttu-id="e7e8d-109">组件</span><span class="sxs-lookup"><span data-stu-id="e7e8d-109">Component</span></span>|<span data-ttu-id="e7e8d-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e7e8d-110">EDI Engine</span></span>|  
|<span data-ttu-id="e7e8d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e7e8d-111">Symbolic Name</span></span>|<span data-ttu-id="e7e8d-112">X12TsControlNumberMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="e7e8d-112">X12TsControlNumberMismatchDescription</span></span>|  
|<span data-ttu-id="e7e8d-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="e7e8d-113">Message Text</span></span>|<span data-ttu-id="e7e8d-114">事务集控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="e7e8d-114">Transaction Set Control Number Mismatch</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e7e8d-115">解释</span><span class="sxs-lookup"><span data-stu-id="e7e8d-115">Explanation</span></span>  
 <span data-ttu-id="e7e8d-116">此错误/警告/信息事件表明 EDI 接收管道拒绝了传入的事务集，因为事务集的 SE02 字段中包含的控制编号与 ST02 字段中的控制编号不匹配。</span><span class="sxs-lookup"><span data-stu-id="e7e8d-116">This Error/Warning/Information event indicates that the EDI receive pipeline rejected the incoming transaction set because the control number contained in the SE02 field of the transaction set did not match the control number in the ST02 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e7e8d-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="e7e8d-117">User Action</span></span>  
 <span data-ttu-id="e7e8d-118">若要解决此错误，请让事务集的发送方更改所拒绝事务集的 SE02 字段中的控制编号，使其与 ST02 字段中的控制编号相同，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="e7e8d-118">To resolve this error, have the sender of the transaction set change the control number in the SE02 field of the rejected transaction set to be the same as the control number in the ST02 field, and then resend the interchange.</span></span>