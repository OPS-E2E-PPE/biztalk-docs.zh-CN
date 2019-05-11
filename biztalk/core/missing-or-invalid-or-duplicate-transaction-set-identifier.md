---
title: 事务集标识符缺失或无效或重复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8580aab2-9fa4-43fb-b643-10621926591e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2165168f092dfb2e3b82116b1fb32153b5f4551f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324604"
---
# <a name="missing-or-invalid-or-duplicate-transaction-set-identifier"></a><span data-ttu-id="2839e-102">事务集标识符缺失或无效或重复</span><span class="sxs-lookup"><span data-stu-id="2839e-102">Missing or invalid or duplicate Transaction set identifier</span></span>
## <a name="details"></a><span data-ttu-id="2839e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2839e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="2839e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2839e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="2839e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="2839e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="2839e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2839e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="2839e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="2839e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="2839e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="2839e-108">EDI</span></span> |
|    <span data-ttu-id="2839e-109">组件</span><span class="sxs-lookup"><span data-stu-id="2839e-109">Component</span></span>    |                                       <span data-ttu-id="2839e-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="2839e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="2839e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="2839e-111">Symbolic Name</span></span>  |                      <span data-ttu-id="2839e-112">X12TsMissingOrInvalidTsIdentiferDescription2</span><span class="sxs-lookup"><span data-stu-id="2839e-112">X12TsMissingOrInvalidTsIdentiferDescription2</span></span>                      |
|  <span data-ttu-id="2839e-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="2839e-113">Message Text</span></span>   |            <span data-ttu-id="2839e-114">事务集标识符缺失或无效或重复{0}</span><span class="sxs-lookup"><span data-stu-id="2839e-114">Missing or invalid or duplicate Transaction set identifier '{0}'</span></span>            |
  
## <a name="explanation"></a><span data-ttu-id="2839e-115">解释</span><span class="sxs-lookup"><span data-stu-id="2839e-115">Explanation</span></span>  
 <span data-ttu-id="2839e-116">此错误/警告/信息事件表明接收管道或发送管道无法处理 X12 交换，因为事务集标识符的值（在 ST01 字段中）缺失、重复或无效。</span><span class="sxs-lookup"><span data-stu-id="2839e-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the X12 interchange because the value of the transaction set identifier (in the ST01 field) was missing, a duplicate, or had an invalid value.</span></span> <span data-ttu-id="2839e-117">如果文档架构没有 ST 标头和 SE 尾部，则可能会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="2839e-117">This can occur if the document schema does not have an ST header and an SE trailer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2839e-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="2839e-118">User Action</span></span>  
 <span data-ttu-id="2839e-119">若要解决此错误，请确保交换具有与 ST01 字段对应的值并且确保架构具有与 ST 标头和 SE 尾部对应的条目。</span><span class="sxs-lookup"><span data-stu-id="2839e-119">To resolve this error, make sure that the interchange has a value for the ST01 field and that the schema has an entry for the ST header and SE trailer.</span></span> <span data-ttu-id="2839e-120">验证 ST01 的值是否是有效的三位文档类型的表示符。</span><span class="sxs-lookup"><span data-stu-id="2839e-120">Verify that the value of ST01 is a valid three-digit document-type designator.</span></span> <span data-ttu-id="2839e-121">验证 ST01 字段是否未与另一个事务集的 ST01 字段重复。</span><span class="sxs-lookup"><span data-stu-id="2839e-121">Verify that the ST01 field is not a duplicate with the ST01 field of another transaction set.</span></span>