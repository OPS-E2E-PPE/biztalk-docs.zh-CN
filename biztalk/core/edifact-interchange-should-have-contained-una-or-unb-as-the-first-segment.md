---
title: Edifact 交换应该包含 UNA 或 UNB 作为第一个段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43fd17-31d0-48df-93cd-524b40034764
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ee9d5100c8378b5ee411673c4c185dcf5def365
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017831"
---
# <a name="edifact-interchange-should-have-contained-una-or-unb-as-the-first-segment"></a><span data-ttu-id="6e9a8-102">EDIFACT 交换应该包含 UNA 或 UNB 作为第一个段</span><span class="sxs-lookup"><span data-stu-id="6e9a8-102">Edifact interchange should have contained UNA or UNB as the first segment</span></span>
## <a name="details"></a><span data-ttu-id="6e9a8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6e9a8-103">Details</span></span>  
  
|                 |                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6e9a8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6e9a8-104">Product Name</span></span>   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]        |
| <span data-ttu-id="6e9a8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="6e9a8-105">Product Version</span></span> |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                    |
|    <span data-ttu-id="6e9a8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6e9a8-106">Event ID</span></span>     |                                                -                                                 |
|  <span data-ttu-id="6e9a8-107">事件源</span><span class="sxs-lookup"><span data-stu-id="6e9a8-107">Event Source</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6e9a8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6e9a8-108"> EDI</span></span>      |
|    <span data-ttu-id="6e9a8-109">组件</span><span class="sxs-lookup"><span data-stu-id="6e9a8-109">Component</span></span>    |                                            <span data-ttu-id="6e9a8-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="6e9a8-110">EDI Engine</span></span>                                            |
|  <span data-ttu-id="6e9a8-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="6e9a8-111">Symbolic Name</span></span>  |                                                -                                                 |
|  <span data-ttu-id="6e9a8-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="6e9a8-112">Message Text</span></span>   | <span data-ttu-id="6e9a8-113">Edifact 交换应该包含 UNA 或 UNB 作为第一个段。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-113">Edifact interchange should have contained UNA or UNB as the first segment.</span></span> <span data-ttu-id="6e9a8-114">而是{0}找</span><span class="sxs-lookup"><span data-stu-id="6e9a8-114">Instead {0} was found</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="6e9a8-115">解释</span><span class="sxs-lookup"><span data-stu-id="6e9a8-115">Explanation</span></span>  
 <span data-ttu-id="6e9a8-116">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的 EDIFACT 交换，因为第一个段既不是 UNA，也不是 UNB 段。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the first segment was neither a UNA nor a UNB segment.</span></span> <span data-ttu-id="6e9a8-117">UNA 段是可选的；UNB 段是必需的。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-117">The UNA segment is optional; the UNB segment is mandatory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6e9a8-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="6e9a8-118">User Action</span></span>  
 <span data-ttu-id="6e9a8-119">若要解决此错误，请确保交换的发送方包含 UNA 或 UNB 段作为交换的第一个段，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="6e9a8-119">To resolve this error, ensure that the sender of the interchange includes the UNA or UNB segment as the first segment of the interchange, and then resends the interchange.</span></span>