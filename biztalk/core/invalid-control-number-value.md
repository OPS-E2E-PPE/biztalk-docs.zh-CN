---
title: 控制编号值无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ac762e2-2d48-45e8-b4c4-2df246b7568c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b426d7bb5834dac14f3bc1db24f62a40eb71ffb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330834"
---
# <a name="invalid-control-number-value"></a><span data-ttu-id="b828f-102">控制编号值无效</span><span class="sxs-lookup"><span data-stu-id="b828f-102">Invalid Control Number Value</span></span>
## <a name="details"></a><span data-ttu-id="b828f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b828f-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="b828f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b828f-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="b828f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="b828f-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="b828f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b828f-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="b828f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="b828f-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b828f-108">EDI</span><span class="sxs-lookup"><span data-stu-id="b828f-108">EDI</span></span> |
|    <span data-ttu-id="b828f-109">组件</span><span class="sxs-lookup"><span data-stu-id="b828f-109">Component</span></span>    |                                       <span data-ttu-id="b828f-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="b828f-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="b828f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="b828f-111">Symbolic Name</span></span>  |                       <span data-ttu-id="b828f-112">X12Ta1InvalidControlNumberValueDescription</span><span class="sxs-lookup"><span data-stu-id="b828f-112">X12Ta1InvalidControlNumberValueDescription</span></span>                       |
|  <span data-ttu-id="b828f-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="b828f-113">Message Text</span></span>   |                              <span data-ttu-id="b828f-114">控制编号值无效</span><span class="sxs-lookup"><span data-stu-id="b828f-114">Invalid Control Number Value</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="b828f-115">解释</span><span class="sxs-lookup"><span data-stu-id="b828f-115">Explanation</span></span>  
 <span data-ttu-id="b828f-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中控制编号的值（交换、组或事务集）不符合架构指定的数据类型或者没有架构指定的正确位数。</span><span class="sxs-lookup"><span data-stu-id="b828f-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of a control number (interchange, group, or transaction set) in the interchange did not conform to the data type or did not have the correct number of digits specified by the schema.</span></span> <span data-ttu-id="b828f-117">在 BaseArtifacts.dll 中，架构为 X12ServiceSchema 或 EdifactServiceSchema。</span><span class="sxs-lookup"><span data-stu-id="b828f-117">The schema is the X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b828f-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="b828f-118">User Action</span></span>  
 <span data-ttu-id="b828f-119">若要解决此错误，请确保控制编号符合架构指定的数据类型和位数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="b828f-119">To resolve this error, make sure that the control number conforms to the data type and number of digits specified by the schema, and then have the interchange resent.</span></span>