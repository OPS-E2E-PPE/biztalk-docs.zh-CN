---
title: 错误 Ack 生成已失败，因为最大限制为 X12 事务方 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c78a7cef-24ae-4d09-9043-2f53c301302d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e845960a85ebe2ebf90b8549634a0097676c80c5
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004702"
---
# <a name="error-ack-generation-has-failed-as-maximum-limit-of-x12-transaction-party"></a><span data-ttu-id="2650c-102">错误 Ack 生成已失败，因为最大限制为 X12 事务方</span><span class="sxs-lookup"><span data-stu-id="2650c-102">Error-Ack generation has failed as maximum limit of X12 transaction-party</span></span>
## <a name="details"></a><span data-ttu-id="2650c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2650c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2650c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2650c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2650c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="2650c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2650c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2650c-106">Event ID</span></span>|-|  
|<span data-ttu-id="2650c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="2650c-107">Event Source</span></span>|<span data-ttu-id="2650c-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="2650c-108">BizTalk Server EDI</span></span>|  
|<span data-ttu-id="2650c-109">组件</span><span class="sxs-lookup"><span data-stu-id="2650c-109">Component</span></span>|<span data-ttu-id="2650c-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="2650c-110">EDI Engine</span></span>|  
|<span data-ttu-id="2650c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="2650c-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="2650c-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="2650c-112">Message Text</span></span>|<span data-ttu-id="2650c-113">无法生成确认，因为参与方 {0} 已达到可接受的 X12 事务集控制编号的最大限制。</span><span class="sxs-lookup"><span data-stu-id="2650c-113">Acknowledgement generation has failed as max limit of acceptable X12 transaction set control number has reached for party {0}.</span></span> <span data-ttu-id="2650c-114">导航到发送方角色屏幕中的“参与方”、合作伙伴协议管理器中的字段 ST 2 可重置计数器</span><span class="sxs-lookup"><span data-stu-id="2650c-114">Reset counter by navigating to Party in sender role screen, field ST 2 in Partner Agreement manager.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2650c-115">解释</span><span class="sxs-lookup"><span data-stu-id="2650c-115">Explanation</span></span>  
 <span data-ttu-id="2650c-116">此错误/警告/信息事件表明 BizTalk Server 无法生成对 X12 交换的确认，因为在确认的事务集控制编号 (ST2) 中输入的控制编号大于 ST2 所允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="2650c-116">This Error/Warning/Information event indicates that BizTalk Server could not generate an acknowledgment to the X12 interchange because the control number that it entered in the Transaction set control number (ST2) of the acknowledgment is greater than the maximum value allowed for ST2.</span></span> <span data-ttu-id="2650c-117">在这种情况下，BizTalk Server 使用 EDI 参与方属性来创建确认。</span><span class="sxs-lookup"><span data-stu-id="2650c-117">In this instance, BizTalk Server used the EDI party properties to create the acknowledgment.</span></span>  
  
 <span data-ttu-id="2650c-118">事务集控制编号的最大值取决于用于控制编号的位数。</span><span class="sxs-lookup"><span data-stu-id="2650c-118">The maximum value of the transaction set control number depends upon the number of digits used for the control number.</span></span> <span data-ttu-id="2650c-119">所有三个字段的最大长度是 9；前缀和后缀字段的最大长度是 8。</span><span class="sxs-lookup"><span data-stu-id="2650c-119">The maximum length of all three fields is 9; the maximum length of the prefix and suffix fields is 8.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2650c-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="2650c-120">User Action</span></span>  
 <span data-ttu-id="2650c-121">若要解决此错误，请将“GS 和 ST 段定义”页的事务集控制编号 (ST2) 的控制编号字段 (ST2.2) 重置为低于最大限制的值。</span><span class="sxs-lookup"><span data-stu-id="2650c-121">To resolve this error, reset the control number field (ST2.2) of the Transaction set control number (ST2) in the GS and ST Segment Definition Page to a value that is lower than the maximum limit.</span></span> <span data-ttu-id="2650c-122">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的“EDI 全局属性”对话框中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="2650c-122">Set this property in the EDI Global Properties dialog box in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>