---
title: "在处理事务集，因为未设置 DocType 之后遇到错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a323658c-77d8-4059-aa15-d88c08e5450d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 874b0229eecdd5fe9c046f69789c4708b9280031
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-after-processing-transaction-sets-because-doctype-was-not-set"></a><span data-ttu-id="833ae-102">在处理事务集，因为未设置 DocType 后遇到的错误</span><span class="sxs-lookup"><span data-stu-id="833ae-102">Error encountered after processing Transaction Set(s) because DocType was not set</span></span>
## <a name="details"></a><span data-ttu-id="833ae-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="833ae-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="833ae-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="833ae-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="833ae-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="833ae-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="833ae-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="833ae-106">Event ID</span></span>|-|  
|<span data-ttu-id="833ae-107">事件源</span><span class="sxs-lookup"><span data-stu-id="833ae-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="833ae-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="833ae-108"> EDI</span></span>|  
|<span data-ttu-id="833ae-109">组件</span><span class="sxs-lookup"><span data-stu-id="833ae-109">Component</span></span>|<span data-ttu-id="833ae-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="833ae-110">EDI Engine</span></span>|  
|<span data-ttu-id="833ae-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="833ae-111">Symbolic Name</span></span>|<span data-ttu-id="833ae-112">DocTypeNotSet</span><span class="sxs-lookup"><span data-stu-id="833ae-112">DocTypeNotSet</span></span>|  
|<span data-ttu-id="833ae-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="833ae-113">Message Text</span></span>|<span data-ttu-id="833ae-114">事务集处理 {0} 后遇到错误。</span><span class="sxs-lookup"><span data-stu-id="833ae-114">Error encountered after processing {0} Transaction Set(s).</span></span> <span data-ttu-id="833ae-115">未设置 DocType</span><span class="sxs-lookup"><span data-stu-id="833ae-115">DocType was not set</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="833ae-116">解释</span><span class="sxs-lookup"><span data-stu-id="833ae-116">Explanation</span></span>  
 <span data-ttu-id="833ae-117">此错误/警告/信息事件指示 EDI 接收管道无法处理设置，因为一个传入事务 ST01 (对于 X12 交换) 或 （对于 EDIFACT 交换） UNH2.1 未设置为事务集。</span><span class="sxs-lookup"><span data-stu-id="833ae-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming transaction set because ST01 (for an X12 interchange) or UNH2.1 (for an EDIFACT interchange) was not set for the transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="833ae-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="833ae-118">User Action</span></span>  
 <span data-ttu-id="833ae-119">若要解决此错误，验证在错误中设置事务的 ST01 或 UNH1 段设置为有效的文档类型。</span><span class="sxs-lookup"><span data-stu-id="833ae-119">To resolve this error, verify that the ST01 or UNH1 segment for the transaction set in error is set to a valid document type.</span></span>