---
title: 找不到与批相对应的协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d1c0480-9a6f-481a-9143-e5a55707c3b5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b505c9c3919a11e0832ac88a8d20ad8f85d2706
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390178"
---
# <a name="could-not-find-an-agreement-corresponding-to-batch"></a><span data-ttu-id="f362e-102">找不到与批相对应的协议</span><span class="sxs-lookup"><span data-stu-id="f362e-102">Could not find an Agreement corresponding to batch</span></span>
## <a name="details"></a><span data-ttu-id="f362e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f362e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="f362e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f362e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f362e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f362e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="f362e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f362e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="f362e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="f362e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f362e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="f362e-108">EDI</span></span> |
|    <span data-ttu-id="f362e-109">组件</span><span class="sxs-lookup"><span data-stu-id="f362e-109">Component</span></span>    |                                       <span data-ttu-id="f362e-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="f362e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="f362e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="f362e-111">Symbolic Name</span></span>  |                               <span data-ttu-id="f362e-112">AgreementNotFoundForBatch</span><span class="sxs-lookup"><span data-stu-id="f362e-112">AgreementNotFoundForBatch</span></span>                                |
|  <span data-ttu-id="f362e-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="f362e-113">Message Text</span></span>   |                <span data-ttu-id="f362e-114">找不到与批相对应的协议{0}。</span><span class="sxs-lookup"><span data-stu-id="f362e-114">Could not find an Agreement corresponding to batch {0}.</span></span>                 |
  
## <a name="explanation"></a><span data-ttu-id="f362e-115">解释</span><span class="sxs-lookup"><span data-stu-id="f362e-115">Explanation</span></span>  
 <span data-ttu-id="f362e-116">此错误/警告/信息事件表明 BizTalk Server 找不到对应于此 Id 尝试一批，若要启动/停止批处理或处理批处理消息。</span><span class="sxs-lookup"><span data-stu-id="f362e-116">This Error/Warning/Information event indicates BizTalk Server was unable to find a Batch corresponding to this Id while trying to start/stop a batch or process a batch message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f362e-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="f362e-117">User Action</span></span>  
 <span data-ttu-id="f362e-118">若要解决此错误，请确保具有给定 Id 的批处理是包含协议的协议属性中存在。</span><span class="sxs-lookup"><span data-stu-id="f362e-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement.</span></span>