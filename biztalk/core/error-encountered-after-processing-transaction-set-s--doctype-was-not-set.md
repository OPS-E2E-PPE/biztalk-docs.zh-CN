---
title: 处理事务集，因为未设置 DocType 后遇到错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a323658c-77d8-4059-aa15-d88c08e5450d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f106a100aa73234e364cbf0071a705dd47502f52
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348582"
---
# <a name="error-encountered-after-processing-transaction-sets-because-doctype-was-not-set"></a><span data-ttu-id="cf379-102">处理事务集，因为未设置 DocType 后遇到错误</span><span class="sxs-lookup"><span data-stu-id="cf379-102">Error encountered after processing Transaction Set(s) because DocType was not set</span></span>
## <a name="details"></a><span data-ttu-id="cf379-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cf379-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="cf379-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cf379-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="cf379-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="cf379-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="cf379-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cf379-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="cf379-107">事件源</span><span class="sxs-lookup"><span data-stu-id="cf379-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="cf379-108">EDI</span><span class="sxs-lookup"><span data-stu-id="cf379-108">EDI</span></span> |
|    <span data-ttu-id="cf379-109">组件</span><span class="sxs-lookup"><span data-stu-id="cf379-109">Component</span></span>    |                                       <span data-ttu-id="cf379-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="cf379-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="cf379-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="cf379-111">Symbolic Name</span></span>  |                                     <span data-ttu-id="cf379-112">DocTypeNotSet</span><span class="sxs-lookup"><span data-stu-id="cf379-112">DocTypeNotSet</span></span>                                      |
|  <span data-ttu-id="cf379-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="cf379-113">Message Text</span></span>   |     <span data-ttu-id="cf379-114">在处理后遇到错误{0}事务集。</span><span class="sxs-lookup"><span data-stu-id="cf379-114">Error encountered after processing {0} Transaction Set(s).</span></span> <span data-ttu-id="cf379-115">未设置 DocType</span><span class="sxs-lookup"><span data-stu-id="cf379-115">DocType was not set</span></span>     |
  
## <a name="explanation"></a><span data-ttu-id="cf379-116">解释</span><span class="sxs-lookup"><span data-stu-id="cf379-116">Explanation</span></span>  
 <span data-ttu-id="cf379-117">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的事务集，因为 ST01 (对于 X12 交换) 或 UNH2.1 （对于 EDIFACT 交换） 未设置为事务集。</span><span class="sxs-lookup"><span data-stu-id="cf379-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming transaction set because ST01 (for an X12 interchange) or UNH2.1 (for an EDIFACT interchange) was not set for the transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cf379-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="cf379-118">User Action</span></span>  
 <span data-ttu-id="cf379-119">若要解决此错误，验证中错误的事务集的 ST01 或 UNH1 段设置为有效的文档类型。</span><span class="sxs-lookup"><span data-stu-id="cf379-119">To resolve this error, verify that the ST01 or UNH1 segment for the transaction set in error is set to a valid document type.</span></span>