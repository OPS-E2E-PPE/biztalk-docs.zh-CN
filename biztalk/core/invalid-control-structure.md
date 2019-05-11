---
title: 控制结构无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f9bb104-7ea1-429a-8540-49f4d598fd46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a315a5345c84afa138aee377e2b192cfd819f5b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330803"
---
# <a name="invalid-control-structure"></a><span data-ttu-id="d6db5-102">控制结构无效</span><span class="sxs-lookup"><span data-stu-id="d6db5-102">Invalid Control Structure</span></span>
## <a name="details"></a><span data-ttu-id="d6db5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d6db5-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="d6db5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d6db5-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="d6db5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d6db5-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="d6db5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d6db5-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="d6db5-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d6db5-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d6db5-108">EDI</span><span class="sxs-lookup"><span data-stu-id="d6db5-108">EDI</span></span> |
|    <span data-ttu-id="d6db5-109">组件</span><span class="sxs-lookup"><span data-stu-id="d6db5-109">Component</span></span>    |                                       <span data-ttu-id="d6db5-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="d6db5-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="d6db5-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d6db5-111">Symbolic Name</span></span>  |                        <span data-ttu-id="d6db5-112">X12Ta1InvalidControlStructureDescription</span><span class="sxs-lookup"><span data-stu-id="d6db5-112">X12Ta1InvalidControlStructureDescription</span></span>                        |
|  <span data-ttu-id="d6db5-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="d6db5-113">Message Text</span></span>   |                               <span data-ttu-id="d6db5-114">控制结构无效</span><span class="sxs-lookup"><span data-stu-id="d6db5-114">Invalid Control Structure</span></span>                                |
  
## <a name="explanation"></a><span data-ttu-id="d6db5-115">解释</span><span class="sxs-lookup"><span data-stu-id="d6db5-115">Explanation</span></span>  
 <span data-ttu-id="d6db5-116">此错误/警告/信息事件表明 BizTalk Server 无法针对 TA1Schema 验证 TA1 确认的结构。</span><span class="sxs-lookup"><span data-stu-id="d6db5-116">This Error/Warning/Information event indicates that BizTalk Server could not validate the structure of the TA1 acknowledgment against the TA1Schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d6db5-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="d6db5-117">User Action</span></span>  
 <span data-ttu-id="d6db5-118">若要解决此错误，请确定 TA1 确认不符合 TA1Schema 的原因并解决此问题。</span><span class="sxs-lookup"><span data-stu-id="d6db5-118">To resolve this error, determine why the TA1 acknowledgment does not conform to the TA1Schema, and resolve the issue.</span></span>