---
title: "事务集重复控制编号找到 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b2779a0-b365-4c4b-81c7-8f9284748b6e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe63d3814bcce178164054ab8dcf673eeb4f395a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-set-duplicate-control-number-found"></a><span data-ttu-id="eafbb-102">发现事务集重复控制编号</span><span class="sxs-lookup"><span data-stu-id="eafbb-102">Transaction Set duplicate control number found</span></span>
## <a name="details"></a><span data-ttu-id="eafbb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="eafbb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eafbb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="eafbb-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="eafbb-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="eafbb-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="eafbb-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="eafbb-106">Event ID</span></span>|-|  
|<span data-ttu-id="eafbb-107">事件源</span><span class="sxs-lookup"><span data-stu-id="eafbb-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="eafbb-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="eafbb-108"> EDI</span></span>|  
|<span data-ttu-id="eafbb-109">组件</span><span class="sxs-lookup"><span data-stu-id="eafbb-109">Component</span></span>|<span data-ttu-id="eafbb-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="eafbb-110">EDI Engine</span></span>|  
|<span data-ttu-id="eafbb-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="eafbb-111">Symbolic Name</span></span>|<span data-ttu-id="eafbb-112">X12TsDuplicateNumberFoundDescription</span><span class="sxs-lookup"><span data-stu-id="eafbb-112">X12TsDuplicateNumberFoundDescription</span></span>|  
|<span data-ttu-id="eafbb-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="eafbb-113">Message Text</span></span>|<span data-ttu-id="eafbb-114">发现事务集重复控制编号</span><span class="sxs-lookup"><span data-stu-id="eafbb-114">Transaction Set duplicate control number found</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eafbb-115">解释</span><span class="sxs-lookup"><span data-stu-id="eafbb-115">Explanation</span></span>  
 <span data-ttu-id="eafbb-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为该交换的组中某个事务集的事务集控制编号与该组中的另一个事务集的控制编号相同。</span><span class="sxs-lookup"><span data-stu-id="eafbb-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the transaction set control number for a transaction set in a group of that interchange was the same as the control number for another transaction set in that group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eafbb-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="eafbb-117">User Action</span></span>  
 <span data-ttu-id="eafbb-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="eafbb-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="eafbb-119">请更改传入交换中事务集的事务集控制编号，以便组中的事务集没有重复的控制编码。</span><span class="sxs-lookup"><span data-stu-id="eafbb-119">Change the transaction set control numbers of transaction sets in incoming interchange so there are no duplicate control numbers for transaction sets in a group.</span></span>  
  
-   <span data-ttu-id="eafbb-120">按照如下方式禁用检查重复的事务集控制编号：</span><span class="sxs-lookup"><span data-stu-id="eafbb-120">Disable the check for duplicate transaction set control numbers as follows:</span></span>  
  
    1.  <span data-ttu-id="eafbb-121">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="eafbb-121">Open the BizTalk Server Administration Console.</span></span>  
  
    2.  <span data-ttu-id="eafbb-122">打开发送交换的参与方的“EDI 属性”对话框。</span><span class="sxs-lookup"><span data-stu-id="eafbb-122">Open the EDI Properties dialog box for the party that sent the interchange.</span></span>  
  
    3.  <span data-ttu-id="eafbb-123">对于 X12 交换，请清除“EDI 属性”对话框的“X12 交换处理属性”页中的“检查组中重复的 ST2（事务集控制编号）”。</span><span class="sxs-lookup"><span data-stu-id="eafbb-123">For X12 interchanges, clear the "Check for duplicate ST2 (Transaction set control number) in group" in the X12 Interchange Processing Properties Page of the EDI Properties dialog box.</span></span>  
  
    4.  <span data-ttu-id="eafbb-124">对于 EDIFACT 交换，请清除“EDI 属性”对话框的“EDIFACT 交换处理属性”页中的“检查组中重复的 UNH1（事务集参考编号）”。</span><span class="sxs-lookup"><span data-stu-id="eafbb-124">For EDIFACT interchanges, clear the "Check for duplicate UNH1 (Transaction set reference number) in group" property in the EDIFACT Interchange Processing Properties Page of the EDI Properties dialog box.</span></span>