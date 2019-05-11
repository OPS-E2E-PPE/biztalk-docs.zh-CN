---
title: 可接受 X12 功能组控制编号已达到来宾设置的最大限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05cba774-fa35-4694-aa34-d7151f8cd75c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a8fed734f07b8d55a349a8b20498e1c9238c8ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388693"
---
# <a name="max-limit-of-acceptable-x12-functional-group-control-number-has-reached-for-guest-settings"></a><span data-ttu-id="af066-102">可接受 X12 功能组控制编号已达到来宾设置的最大限制</span><span class="sxs-lookup"><span data-stu-id="af066-102">Max limit of acceptable X12 functional group control number has reached for Guest settings</span></span>
## <a name="details"></a><span data-ttu-id="af066-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="af066-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="af066-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="af066-104">Product Name</span></span>   |                                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                               |
| <span data-ttu-id="af066-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="af066-105">Product Version</span></span> |                                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                           |
|    <span data-ttu-id="af066-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="af066-106">Event ID</span></span>     |                                                                                                       -                                                                                                       |
|  <span data-ttu-id="af066-107">事件源</span><span class="sxs-lookup"><span data-stu-id="af066-107">Event Source</span></span>   |                                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="af066-108">EDI</span><span class="sxs-lookup"><span data-stu-id="af066-108">EDI</span></span>                                                             |
|    <span data-ttu-id="af066-109">组件</span><span class="sxs-lookup"><span data-stu-id="af066-109">Component</span></span>    |                                                                                                  <span data-ttu-id="af066-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="af066-110">EDI Engine</span></span>                                                                                                   |
|  <span data-ttu-id="af066-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="af066-111">Symbolic Name</span></span>  |                                                                                          <span data-ttu-id="af066-112">GlobalEdifactUnhNumberError</span><span class="sxs-lookup"><span data-stu-id="af066-112">GlobalEdifactUnhNumberError</span></span>                                                                                          |
|  <span data-ttu-id="af066-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="af066-113">Message Text</span></span>   | <span data-ttu-id="af066-114">已达到“来宾”设置的可接受 X12 功能组控制编号最大限制。</span><span class="sxs-lookup"><span data-stu-id="af066-114">Max limit of acceptable X12 functional group control number has reached for Guest settings.</span></span> <span data-ttu-id="af066-115">导航到合作伙伴协议管理器的全局配置接收方角色屏幕中的字段 GS 6 可重置计数器</span><span class="sxs-lookup"><span data-stu-id="af066-115">Reset counter by navigating to Global configuration receiver role screen, field GS 6 in Partner Agreement manager</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="af066-116">解释</span><span class="sxs-lookup"><span data-stu-id="af066-116">Explanation</span></span>  
 <span data-ttu-id="af066-117">此错误/警告/信息事件表明发送管道无法处理传出的 X12 交换，因为在全局设置中指定的 GS06 字段中的组控制编号大于所允许的最大值。</span><span class="sxs-lookup"><span data-stu-id="af066-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing X12 interchange because the group control number in the GS06 field specified in the global settings was greater than the maximum allowable value.</span></span> <span data-ttu-id="af066-118">组控制编号的最大字符数为 9。</span><span class="sxs-lookup"><span data-stu-id="af066-118">The maximum number of characters for the group control number is 9.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="af066-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="af066-119">User Action</span></span>  
 <span data-ttu-id="af066-120">若要解决此错误，请按照如下方式重置组控制编号：</span><span class="sxs-lookup"><span data-stu-id="af066-120">To resolve this error, reset the group control number, as follows:</span></span>  
  
1.  <span data-ttu-id="af066-121">在“EDI 全局属性”对话框中，打开“GS 和 ST 段定义”页。</span><span class="sxs-lookup"><span data-stu-id="af066-121">In the EDI Global Properties dialog box, open the GS and ST Segment Definition page.</span></span>  
  
2.  <span data-ttu-id="af066-122">单击与 GS06 字段关联的“编辑”字段。</span><span class="sxs-lookup"><span data-stu-id="af066-122">Click the Edit field associated with the GS06 field.</span></span>  
  
3.  <span data-ttu-id="af066-123">将组控制编号设置为一个新值，以便该字段具有 9 个或更少的数字。</span><span class="sxs-lookup"><span data-stu-id="af066-123">Set the group control number to a new value such that the field has nine or fewer digits.</span></span>