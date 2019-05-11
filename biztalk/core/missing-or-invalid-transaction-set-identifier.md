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
ms.openlocfilehash: c9dca8c7d26eb826ff6da339ae77040e5527238c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324522"
---
# <a name="missing-or-invalid-transaction-set-identifier"></a><span data-ttu-id="f3693-102">事务集标识符缺失或无效</span><span class="sxs-lookup"><span data-stu-id="f3693-102">Missing or invalid Transaction set identifier</span></span>
## <a name="details"></a><span data-ttu-id="f3693-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f3693-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="f3693-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f3693-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f3693-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f3693-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="f3693-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f3693-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="f3693-107">事件源</span><span class="sxs-lookup"><span data-stu-id="f3693-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f3693-108">EDI</span><span class="sxs-lookup"><span data-stu-id="f3693-108">EDI</span></span> |
|    <span data-ttu-id="f3693-109">组件</span><span class="sxs-lookup"><span data-stu-id="f3693-109">Component</span></span>    |                                       <span data-ttu-id="f3693-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="f3693-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="f3693-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="f3693-111">Symbolic Name</span></span>  |                     <span data-ttu-id="f3693-112">EfactTsMissingOrInvalidTsIdentiferDescription</span><span class="sxs-lookup"><span data-stu-id="f3693-112">EfactTsMissingOrInvalidTsIdentiferDescription</span></span>                      |
|  <span data-ttu-id="f3693-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="f3693-113">Message Text</span></span>   |                     <span data-ttu-id="f3693-114">事务集标识符缺失或无效</span><span class="sxs-lookup"><span data-stu-id="f3693-114">Missing or invalid Transaction set identifier</span></span>                      |
  
## <a name="explanation"></a><span data-ttu-id="f3693-115">解释</span><span class="sxs-lookup"><span data-stu-id="f3693-115">Explanation</span></span>  
 <span data-ttu-id="f3693-116">此错误/警告/信息事件表明接收或发送管道不无法处理 EDIFACT 交换，因为事务集标识符 （在 UNH2.1 字段中） 的值缺失或具有无效值。</span><span class="sxs-lookup"><span data-stu-id="f3693-116">This Error/Warning/Information event indicates that the receive or send pipeline could not process the EDIFACT interchange because the value of the transaction set identifier (in the UNH2.1 field) was missing or had an invalid value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f3693-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="f3693-117">User Action</span></span>  
 <span data-ttu-id="f3693-118">若要解决此错误，请确保交换具有 UNH2.1 字段的值。</span><span class="sxs-lookup"><span data-stu-id="f3693-118">To resolve this error, make sure that the interchange has a value for the UNH2.1 field.</span></span> <span data-ttu-id="f3693-119">验证 UNH2.1 的值是有效的一位到 6 位文档类型指示符。</span><span class="sxs-lookup"><span data-stu-id="f3693-119">Verify that the value of UNH2.1 is a valid one-digit to six-digit document-type designator.</span></span>