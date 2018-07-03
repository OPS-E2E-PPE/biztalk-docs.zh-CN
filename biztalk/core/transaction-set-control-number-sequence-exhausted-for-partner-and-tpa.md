---
title: 事务集控制编号序列的合作伙伴和 TPA 耗尽 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f194ca-3e0f-4ad4-8bc8-88aa7e5193a7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c39815ccd013deea9ac4ef78426320e5c371feb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968510"
---
# <a name="transaction-set-control-number-sequence-exhausted-for-partner-and-tpa"></a><span data-ttu-id="572c0-102">事务集控制编号序列的合作伙伴和 TPA 已耗尽</span><span class="sxs-lookup"><span data-stu-id="572c0-102">Transaction set control number sequence exhausted for Partner and TPA</span></span>
## <a name="details"></a><span data-ttu-id="572c0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="572c0-103">Details</span></span>  
  
|                 |                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="572c0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="572c0-104">Product Name</span></span>   |                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                           |
| <span data-ttu-id="572c0-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="572c0-105">Product Version</span></span> |                                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                       |
|    <span data-ttu-id="572c0-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="572c0-106">Event ID</span></span>     |                                                                                   -                                                                                    |
|  <span data-ttu-id="572c0-107">事件源</span><span class="sxs-lookup"><span data-stu-id="572c0-107">Event Source</span></span>   |                                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="572c0-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="572c0-108"> EDI</span></span>                                         |
|    <span data-ttu-id="572c0-109">组件</span><span class="sxs-lookup"><span data-stu-id="572c0-109">Component</span></span>    |                                                                               <span data-ttu-id="572c0-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="572c0-110">EDI Engine</span></span>                                                                               |
|  <span data-ttu-id="572c0-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="572c0-111">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="572c0-112">EdiControlNumberExhaustedForParty</span><span class="sxs-lookup"><span data-stu-id="572c0-112">EdiControlNumberExhaustedForParty</span></span>                                                                    |
|  <span data-ttu-id="572c0-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="572c0-113">Message Text</span></span>   | <span data-ttu-id="572c0-114">事务集控制编号序列已用尽 '{1}对于 TPA{2}。</span><span class="sxs-lookup"><span data-stu-id="572c0-114">Transaction set control number sequence exhausted for Partner '{1}' for the TPA '{2}'.</span></span> <span data-ttu-id="572c0-115">重置该序列中的{2}-使用 BizTalk Server 管理的 EDI 属性。</span><span class="sxs-lookup"><span data-stu-id="572c0-115">Reset the sequence in {2} - EDI Properties using BizTalk Server Administration.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="572c0-116">解释</span><span class="sxs-lookup"><span data-stu-id="572c0-116">Explanation</span></span>  
 <span data-ttu-id="572c0-117">此错误/警告/信息事件表明 BizTalk Server 无法处理文档，因为对于 {2} 中的协议来说，事务集控制范围已经用尽。</span><span class="sxs-lookup"><span data-stu-id="572c0-117">This Error/Warning/Information event indicates BizTalk Server was not able to process the document because the Transaction set control range has been used up for the agreement in {2}.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="572c0-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="572c0-118">User Action</span></span>  
 <span data-ttu-id="572c0-119">若要解决此错误，请选中该复选框以重置 {2} 协议的控制编号或增加控制编号范围，或者针对协议中的控制编号范围规范单击“重置”按钮。</span><span class="sxs-lookup"><span data-stu-id="572c0-119">To resolve this error, please tick the checkbox to reset the control number for the {2} agreement or increase the control number range or hit the reset button against the control number range specification in the agreement.</span></span>