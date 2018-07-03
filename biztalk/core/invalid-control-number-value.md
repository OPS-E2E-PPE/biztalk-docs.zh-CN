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
ms.openlocfilehash: 09b274170505bf1b010d61fbefe9d43a51528aac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019835"
---
# <a name="invalid-control-number-value"></a><span data-ttu-id="9a0b8-102">控制编号值无效</span><span class="sxs-lookup"><span data-stu-id="9a0b8-102">Invalid Control Number Value</span></span>
## <a name="details"></a><span data-ttu-id="9a0b8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9a0b8-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9a0b8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9a0b8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9a0b8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="9a0b8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9a0b8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9a0b8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9a0b8-107">事件源</span><span class="sxs-lookup"><span data-stu-id="9a0b8-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9a0b8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9a0b8-108"> EDI</span></span> |
|    <span data-ttu-id="9a0b8-109">组件</span><span class="sxs-lookup"><span data-stu-id="9a0b8-109">Component</span></span>    |                                       <span data-ttu-id="9a0b8-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="9a0b8-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="9a0b8-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="9a0b8-111">Symbolic Name</span></span>  |                       <span data-ttu-id="9a0b8-112">X12Ta1InvalidControlNumberValueDescription</span><span class="sxs-lookup"><span data-stu-id="9a0b8-112">X12Ta1InvalidControlNumberValueDescription</span></span>                       |
|  <span data-ttu-id="9a0b8-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="9a0b8-113">Message Text</span></span>   |                              <span data-ttu-id="9a0b8-114">控制编号值无效</span><span class="sxs-lookup"><span data-stu-id="9a0b8-114">Invalid Control Number Value</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="9a0b8-115">解释</span><span class="sxs-lookup"><span data-stu-id="9a0b8-115">Explanation</span></span>  
 <span data-ttu-id="9a0b8-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中控制编号的值（交换、组或事务集）不符合架构指定的数据类型或者没有架构指定的正确位数。</span><span class="sxs-lookup"><span data-stu-id="9a0b8-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of a control number (interchange, group, or transaction set) in the interchange did not conform to the data type or did not have the correct number of digits specified by the schema.</span></span> <span data-ttu-id="9a0b8-117">在 BaseArtifacts.dll 中，架构为 X12ServiceSchema 或 EdifactServiceSchema。</span><span class="sxs-lookup"><span data-stu-id="9a0b8-117">The schema is the X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9a0b8-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="9a0b8-118">User Action</span></span>  
 <span data-ttu-id="9a0b8-119">若要解决此错误，请确保控制编号符合架构指定的数据类型和位数，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="9a0b8-119">To resolve this error, make sure that the control number conforms to the data type and number of digits specified by the schema, and then have the interchange resent.</span></span>