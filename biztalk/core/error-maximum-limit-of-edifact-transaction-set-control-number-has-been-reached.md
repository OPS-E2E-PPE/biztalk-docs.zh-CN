---
title: 确认生成失败，因为已达到参与方设置的 Edifact 事务集控制编号的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcbb6374-0403-42b0-892b-b35157a2c74a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b639f80d6ad203074e0542df6672f2d7b89aa2ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001342"
---
# <a name="acknowledgement-generation-has-failed-as-maximum-limit-of-edifact-transaction-set-control-number-has-been-reached-for-party-settings"></a><span data-ttu-id="79702-102">确认生成失败，因为已达到参与方设置的 EDIFACT 事务集控制编号的上限</span><span class="sxs-lookup"><span data-stu-id="79702-102">Acknowledgement generation has failed as maximum limit of Edifact transaction set control number has been reached for party settings</span></span>
## <a name="details"></a><span data-ttu-id="79702-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="79702-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="79702-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="79702-104">Product Name</span></span>   |                                                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                            |
| <span data-ttu-id="79702-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="79702-105">Product Version</span></span> |                                                                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                                        |
|    <span data-ttu-id="79702-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="79702-106">Event ID</span></span>     |                                                                                                                    -                                                                                                                     |
|  <span data-ttu-id="79702-107">事件源</span><span class="sxs-lookup"><span data-stu-id="79702-107">Event Source</span></span>   |                                                                                                            <span data-ttu-id="79702-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="79702-108">BizTalk Server EDI</span></span>                                                                                                            |
|    <span data-ttu-id="79702-109">组件</span><span class="sxs-lookup"><span data-stu-id="79702-109">Component</span></span>    |                                                                                                                <span data-ttu-id="79702-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="79702-110">EDI Engine</span></span>                                                                                                                |
|  <span data-ttu-id="79702-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="79702-111">Symbolic Name</span></span>  |                                                                                                                    -                                                                                                                     |
|  <span data-ttu-id="79702-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="79702-112">Message Text</span></span>   | <span data-ttu-id="79702-113">确认生成失败，因为可接受 Edifact 事务集控制编号已达到参与方的最大限制{0}。</span><span class="sxs-lookup"><span data-stu-id="79702-113">Acknowledgement generation has failed as max limit of acceptable Edifact transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="79702-114">导航到参与方在发送方角色屏幕、 合作伙伴协议管理器中的字段 UNH 1 可重置计数器。</span><span class="sxs-lookup"><span data-stu-id="79702-114">Reset counter by navigating to Party in sender role screen, field UNH 1 in Partner Agreement manager.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="79702-115">解释</span><span class="sxs-lookup"><span data-stu-id="79702-115">Explanation</span></span>  
 <span data-ttu-id="79702-116">此错误/警告/信息事件表明 BizTalk Server 无法生成对 EDIFACT 交换的确认，因为在确认的事务集参考编号 (UNH1) 中输入的控制编号大于 UNH1 所允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="79702-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an acknowledgment to the EDIFACT interchange because the control number that it entered in the Transaction set reference number (UNH1) of the acknowledgment is greater than the maximum value allowed for UNH1.</span></span> <span data-ttu-id="79702-117">在这种情况下，BizTalk Server 使用 EDI 参与方属性来创建确认。</span><span class="sxs-lookup"><span data-stu-id="79702-117">In this instance, BizTalk Server used the EDI party properties to create the acknowledgment.</span></span>  
  
 <span data-ttu-id="79702-118">事务集参考编号的最大值取决于用于参考编号的位数。</span><span class="sxs-lookup"><span data-stu-id="79702-118">The maximum value of the transaction set reference number depends upon the number of digits used for the reference number.</span></span> <span data-ttu-id="79702-119">参考编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。</span><span class="sxs-lookup"><span data-stu-id="79702-119">The maximum number of characters is 14 for the reference number, 13 for the prefix and suffix, and 14 for all three fields combined.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79702-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="79702-120">User Action</span></span>  
 <span data-ttu-id="79702-121">若要解决此错误，请将“UNG 和 UNH 段定义”页的事务集参考编号 (UNH1) 的参考编号字段 (UNH1.2) 重置为低于最大限制的值。</span><span class="sxs-lookup"><span data-stu-id="79702-121">To resolve this error, reset the reference number field (UNH1.2) of the Transaction set reference number (UNH1) in the UNG and UNH Segment Definition Page to a value that is lower than the maximum limit.</span></span> <span data-ttu-id="79702-122">在 BizTalk Server 管理控制台的 EDI 属性对话框中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="79702-122">Set this property in the EDI Properties dialog box in the BizTalk Server Administration Console.</span></span>