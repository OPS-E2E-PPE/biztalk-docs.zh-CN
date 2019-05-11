---
title: 发现事务集重复控制编号 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b2779a0-b365-4c4b-81c7-8f9284748b6e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f273d7e66f4ebe942044e30adccbc7994720a99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279719"
---
# <a name="transaction-set-duplicate-control-number-found"></a><span data-ttu-id="062b5-102">发现事务集重复控制编号</span><span class="sxs-lookup"><span data-stu-id="062b5-102">Transaction Set duplicate control number found</span></span>
## <a name="details"></a><span data-ttu-id="062b5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="062b5-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="062b5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="062b5-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="062b5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="062b5-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="062b5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="062b5-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="062b5-107">事件源</span><span class="sxs-lookup"><span data-stu-id="062b5-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="062b5-108">EDI</span><span class="sxs-lookup"><span data-stu-id="062b5-108">EDI</span></span> |
|    <span data-ttu-id="062b5-109">组件</span><span class="sxs-lookup"><span data-stu-id="062b5-109">Component</span></span>    |                                       <span data-ttu-id="062b5-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="062b5-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="062b5-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="062b5-111">Symbolic Name</span></span>  |                          <span data-ttu-id="062b5-112">X12TsDuplicateNumberFoundDescription</span><span class="sxs-lookup"><span data-stu-id="062b5-112">X12TsDuplicateNumberFoundDescription</span></span>                          |
|  <span data-ttu-id="062b5-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="062b5-113">Message Text</span></span>   |                     <span data-ttu-id="062b5-114">发现事务集重复控制编号</span><span class="sxs-lookup"><span data-stu-id="062b5-114">Transaction Set duplicate control number found</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="062b5-115">解释</span><span class="sxs-lookup"><span data-stu-id="062b5-115">Explanation</span></span>  
 <span data-ttu-id="062b5-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为事务集控制编号的组中的事务集的交换已与另一个的控制编号相同事务集在该组中。</span><span class="sxs-lookup"><span data-stu-id="062b5-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the transaction set control number for a transaction set in a group of that interchange was the same as the control number for another transaction set in that group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="062b5-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="062b5-117">User Action</span></span>  
 <span data-ttu-id="062b5-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="062b5-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="062b5-119">组中的更改的事务集数量的事务设置中传入的交换，因此事务没有重复的控制编号的控件集。</span><span class="sxs-lookup"><span data-stu-id="062b5-119">Change the transaction set control numbers of transaction sets in incoming interchange so there are no duplicate control numbers for transaction sets in a group.</span></span>  
  
-   <span data-ttu-id="062b5-120">禁用对重复的事务集控制编号的检查，如下所示：</span><span class="sxs-lookup"><span data-stu-id="062b5-120">Disable the check for duplicate transaction set control numbers as follows:</span></span>  
  
    1.  <span data-ttu-id="062b5-121">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="062b5-121">Open the BizTalk Server Administration Console.</span></span>  
  
    2.  <span data-ttu-id="062b5-122">打开发送交换的参与方 EDI 属性对话框。</span><span class="sxs-lookup"><span data-stu-id="062b5-122">Open the EDI Properties dialog box for the party that sent the interchange.</span></span>  
  
    3.  <span data-ttu-id="062b5-123">对于 X12 交换，清除"检查重复的 st2 （事务集控制编号） 组中"x12 交换处理属性页 EDI 属性对话框。</span><span class="sxs-lookup"><span data-stu-id="062b5-123">For X12 interchanges, clear the "Check for duplicate ST2 (Transaction set control number) in group" in the X12 Interchange Processing Properties Page of the EDI Properties dialog box.</span></span>  
  
    4.  <span data-ttu-id="062b5-124">对于 EDIFACT 交换，清除"检查重复的 unh1 （事务集参考编号） 组中"EDIFACT 交换处理属性页的 EDI 属性对话框中的属性。</span><span class="sxs-lookup"><span data-stu-id="062b5-124">For EDIFACT interchanges, clear the "Check for duplicate UNH1 (Transaction set reference number) in group" property in the EDIFACT Interchange Processing Properties Page of the EDI Properties dialog box.</span></span>