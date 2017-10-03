---
title: "通信模式错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06656073-9bae-4d6f-98ae-2714a72ee79c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36677694b8f2d0973c04d942a196d055b696bd5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="communication-pattern-errors"></a><span data-ttu-id="1be87-102">通信模式错误</span><span class="sxs-lookup"><span data-stu-id="1be87-102">Communication Pattern Errors</span></span>
<span data-ttu-id="1be87-103">用于诊断和解决 WCF 通信模式错误的信息。</span><span class="sxs-lookup"><span data-stu-id="1be87-103">Information for diagnosing and resolving WCF Communication Pattern errors.</span></span>  

## <a name="fault-messages-are-not-supported-on-one-way-ports"></a><span data-ttu-id="1be87-104">单向端口不支持错误消息</span><span class="sxs-lookup"><span data-stu-id="1be87-104">Fault messages are not supported on one-way ports</span></span>
  
||<span data-ttu-id="1be87-105">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="1be87-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="1be87-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="1be87-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1be87-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="1be87-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="1be87-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1be87-108">Event ID</span></span>|<span data-ttu-id="1be87-109">0</span><span class="sxs-lookup"><span data-stu-id="1be87-109">0</span></span>|  
|<span data-ttu-id="1be87-110">事件源</span><span class="sxs-lookup"><span data-stu-id="1be87-110">Event Source</span></span>|<span data-ttu-id="1be87-111">0</span><span class="sxs-lookup"><span data-stu-id="1be87-111">0</span></span>|  
|<span data-ttu-id="1be87-112">组件</span><span class="sxs-lookup"><span data-stu-id="1be87-112">Component</span></span>|<span data-ttu-id="1be87-113">0</span><span class="sxs-lookup"><span data-stu-id="1be87-113">0</span></span>|  
|<span data-ttu-id="1be87-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="1be87-114">Symbolic Name</span></span>|<span data-ttu-id="1be87-115">0</span><span class="sxs-lookup"><span data-stu-id="1be87-115">0</span></span>|  
|<span data-ttu-id="1be87-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="1be87-116">Message Text</span></span>|<span data-ttu-id="1be87-117">单向端口上不支持错误消息。</span><span class="sxs-lookup"><span data-stu-id="1be87-117">Fault messages are not supported on one-way ports.</span></span> <span data-ttu-id="1be87-118">更正服务说明"{0}"端口类型"{1}"，然后重新运行该向导</span><span class="sxs-lookup"><span data-stu-id="1be87-118">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1be87-119">解释</span><span class="sxs-lookup"><span data-stu-id="1be87-119">Explanation</span></span>  
 <span data-ttu-id="1be87-120">此错误表示尝试使用的服务是单向服务，并且指定了错误。</span><span class="sxs-lookup"><span data-stu-id="1be87-120">This error indicates the service trying to be consumed is a one-way service and has the fault specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1be87-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="1be87-121">User Action</span></span>  
 <span data-ttu-id="1be87-122">通过将通信模式从单向模式切换到请求-响应模式来更正服务。</span><span class="sxs-lookup"><span data-stu-id="1be87-122">Correct the service by switching the communication pattern from one-way to request-response.</span></span> <span data-ttu-id="1be87-123">或者从代码中删除此错误。</span><span class="sxs-lookup"><span data-stu-id="1be87-123">Or remove the fault in the code.</span></span>
 
 