---
title: 事务集控制编号缺失或无效 |Microsoft Docs
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
ms.openlocfilehash: e247e75d7ac1f789ee3c1747e89c1f737c6d71cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394440"
---
# <a name="missing-or-invalid-transaction-set-control-number"></a><span data-ttu-id="8832a-102">事务集控制编号缺失或无效</span><span class="sxs-lookup"><span data-stu-id="8832a-102">Missing or invalid transaction set control number</span></span>
## <a name="details"></a><span data-ttu-id="8832a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8832a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="8832a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8832a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="8832a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8832a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="8832a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8832a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="8832a-107">事件源</span><span class="sxs-lookup"><span data-stu-id="8832a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8832a-108">EDI</span><span class="sxs-lookup"><span data-stu-id="8832a-108">EDI</span></span> |
|    <span data-ttu-id="8832a-109">组件</span><span class="sxs-lookup"><span data-stu-id="8832a-109">Component</span></span>    |                                       <span data-ttu-id="8832a-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="8832a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="8832a-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="8832a-111">Symbolic Name</span></span>  |                    <span data-ttu-id="8832a-112">X12TsMissingOrInvalidTsControlNumberDescription</span><span class="sxs-lookup"><span data-stu-id="8832a-112">X12TsMissingOrInvalidTsControlNumberDescription</span></span>                     |
|  <span data-ttu-id="8832a-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="8832a-113">Message Text</span></span>   |                   <span data-ttu-id="8832a-114">事务集控制编号缺失或无效</span><span class="sxs-lookup"><span data-stu-id="8832a-114">Missing or invalid transaction set control number</span></span>                    |
  
## <a name="explanation"></a><span data-ttu-id="8832a-115">解释</span><span class="sxs-lookup"><span data-stu-id="8832a-115">Explanation</span></span>  
 <span data-ttu-id="8832a-116">此错误/警告/信息事件表明接收管道或发送管道无法处理交换，因为事务集控制编号的值（在 ST02 字段中）缺失或无效。</span><span class="sxs-lookup"><span data-stu-id="8832a-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the interchange because the value of the transaction set control number (in the ST02 field) was missing or had an invalid value.</span></span> <span data-ttu-id="8832a-117">事务集控制编号必须为字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8832a-117">The transaction set control number must be an alphanumeric value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8832a-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="8832a-118">User Action</span></span>  
 <span data-ttu-id="8832a-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="8832a-119">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="8832a-120">确保每个事务集具有一个事务集控制编号。</span><span class="sxs-lookup"><span data-stu-id="8832a-120">Make sure that each transaction set has a transaction set control number.</span></span>  
  
2.  <span data-ttu-id="8832a-121">确保每个事务集控制编号是字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8832a-121">Make sure that each transaction set control number is an alphanumeric value.</span></span>