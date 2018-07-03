---
title: 事务集标识符缺失或无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 282c8128-7d23-44e2-bf44-e90e52cb5fb1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f0444468b7f7ff52b38bcd8db01a6bded5ed0a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009926"
---
# <a name="missing-or-invalid-transaction-set-identifier"></a><span data-ttu-id="f7b5e-102">事务集标识符缺失或无效</span><span class="sxs-lookup"><span data-stu-id="f7b5e-102">Missing or invalid Transaction set identifier</span></span>
## <a name="details"></a><span data-ttu-id="f7b5e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f7b5e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="f7b5e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f7b5e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f7b5e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f7b5e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="f7b5e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f7b5e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="f7b5e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="f7b5e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f7b5e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f7b5e-108"> EDI</span></span> |
|    <span data-ttu-id="f7b5e-109">组件</span><span class="sxs-lookup"><span data-stu-id="f7b5e-109">Component</span></span>    |                                       <span data-ttu-id="f7b5e-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="f7b5e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="f7b5e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="f7b5e-111">Symbolic Name</span></span>  |                     <span data-ttu-id="f7b5e-112">EfactTsMissingOrInvalidTsIdentiferDescription</span><span class="sxs-lookup"><span data-stu-id="f7b5e-112">EfactTsMissingOrInvalidTsIdentiferDescription</span></span>                      |
|  <span data-ttu-id="f7b5e-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="f7b5e-113">Message Text</span></span>   |                     <span data-ttu-id="f7b5e-114">事务集标识符缺失或无效</span><span class="sxs-lookup"><span data-stu-id="f7b5e-114">Missing or invalid Transaction set identifier</span></span>                      |
  
## <a name="explanation"></a><span data-ttu-id="f7b5e-115">解释</span><span class="sxs-lookup"><span data-stu-id="f7b5e-115">Explanation</span></span>  
 <span data-ttu-id="f7b5e-116">此错误/警告/信息事件表明接收管道或发送管道无法处理 EDIFACT 交换，因为事务集标识符的值（在 UNH2.1 字段中）缺失或无效。</span><span class="sxs-lookup"><span data-stu-id="f7b5e-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the EDIFACT interchange because the value of the transaction set identifier (in the UNH2.1 field) was missing or had an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f7b5e-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="f7b5e-117">User Action</span></span>  
 <span data-ttu-id="f7b5e-118">若要解决此错误，请确保交换具有 UNH2.1 字段的值。</span><span class="sxs-lookup"><span data-stu-id="f7b5e-118">To resolve this error, make sure that the interchange has a value for the UNH2.1 field.</span></span> <span data-ttu-id="f7b5e-119">验证 UNH2.1 的值是否是有效的 1 位到 6 位文档类型的表示符。</span><span class="sxs-lookup"><span data-stu-id="f7b5e-119">Verify that the value of UNH2.1 is a valid one-digit to six-digit document-type designator.</span></span>