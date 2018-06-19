---
title: 缺少或无效的事务集控制编号 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6064b974-e8cd-4486-abc2-010afe0d956e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e9448c9be2cd05c7f7d8c18c13730933c1b5824
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262989"
---
# <a name="missing-or-invalid-transaction-set-control-number"></a><span data-ttu-id="69a4f-102">事务集控制编号缺失或无效</span><span class="sxs-lookup"><span data-stu-id="69a4f-102">Missing or invalid transaction set control number</span></span>
## <a name="details"></a><span data-ttu-id="69a4f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="69a4f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="69a4f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="69a4f-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="69a4f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="69a4f-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="69a4f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="69a4f-106">Event ID</span></span>|-|  
|<span data-ttu-id="69a4f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="69a4f-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="69a4f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="69a4f-108"> EDI</span></span>|  
|<span data-ttu-id="69a4f-109">组件</span><span class="sxs-lookup"><span data-stu-id="69a4f-109">Component</span></span>|<span data-ttu-id="69a4f-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="69a4f-110">EDI Engine</span></span>|  
|<span data-ttu-id="69a4f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="69a4f-111">Symbolic Name</span></span>|<span data-ttu-id="69a4f-112">X12TsMissingOrInvalidTsControlNumberDescription</span><span class="sxs-lookup"><span data-stu-id="69a4f-112">X12TsMissingOrInvalidTsControlNumberDescription</span></span>|  
|<span data-ttu-id="69a4f-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="69a4f-113">Message Text</span></span>|<span data-ttu-id="69a4f-114">事务集控制编号缺失或无效</span><span class="sxs-lookup"><span data-stu-id="69a4f-114">Missing or invalid transaction set control number</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="69a4f-115">解释</span><span class="sxs-lookup"><span data-stu-id="69a4f-115">Explanation</span></span>  
 <span data-ttu-id="69a4f-116">此错误/警告/信息事件表明接收管道或发送管道无法处理交换，因为事务集控制编号的值（在 ST02 字段中）缺失或无效。</span><span class="sxs-lookup"><span data-stu-id="69a4f-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the interchange because the value of the transaction set control number (in the ST02 field) was missing or had an invalid value.</span></span> <span data-ttu-id="69a4f-117">事务集控制编号必须为字母数字值。</span><span class="sxs-lookup"><span data-stu-id="69a4f-117">The transaction set control number must be an alphanumeric value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="69a4f-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="69a4f-118">User Action</span></span>  
 <span data-ttu-id="69a4f-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="69a4f-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="69a4f-120">确保每个事务集具有一个事务集控制编号。</span><span class="sxs-lookup"><span data-stu-id="69a4f-120">Make sure that each transaction set has a transaction set control number.</span></span>  
  
2.  <span data-ttu-id="69a4f-121">确保每个事务集控制编号是字母数字值。</span><span class="sxs-lookup"><span data-stu-id="69a4f-121">Make sure that each transaction set control number is an alphanumeric value.</span></span>