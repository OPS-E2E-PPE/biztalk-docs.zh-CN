---
title: 通信模式错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06656073-9bae-4d6f-98ae-2714a72ee79c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20a878f34b1e78509bec85fedbc2cf115a7140ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357042"
---
# <a name="communication-pattern-errors"></a><span data-ttu-id="2ca3e-102">通信模式错误</span><span class="sxs-lookup"><span data-stu-id="2ca3e-102">Communication Pattern Errors</span></span>
<span data-ttu-id="2ca3e-103">诊断和解决 WCF 通信模式错误的信息。</span><span class="sxs-lookup"><span data-stu-id="2ca3e-103">Information for diagnosing and resolving WCF Communication Pattern errors.</span></span>  

## <a name="fault-messages-are-not-supported-on-one-way-ports"></a><span data-ttu-id="2ca3e-104">单向端口不支持错误消息</span><span class="sxs-lookup"><span data-stu-id="2ca3e-104">Fault messages are not supported on one-way ports</span></span>
  
|                 |                                                       <span data-ttu-id="2ca3e-105">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="2ca3e-105">Error details</span></span>                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2ca3e-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="2ca3e-106">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| <span data-ttu-id="2ca3e-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="2ca3e-107">Product Version</span></span> |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    <span data-ttu-id="2ca3e-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2ca3e-108">Event ID</span></span>     |                                                             <span data-ttu-id="2ca3e-109">0</span><span class="sxs-lookup"><span data-stu-id="2ca3e-109">0</span></span>                                                             |
|  <span data-ttu-id="2ca3e-110">事件源</span><span class="sxs-lookup"><span data-stu-id="2ca3e-110">Event Source</span></span>   |                                                             <span data-ttu-id="2ca3e-111">0</span><span class="sxs-lookup"><span data-stu-id="2ca3e-111">0</span></span>                                                             |
|    <span data-ttu-id="2ca3e-112">组件</span><span class="sxs-lookup"><span data-stu-id="2ca3e-112">Component</span></span>    |                                                             <span data-ttu-id="2ca3e-113">0</span><span class="sxs-lookup"><span data-stu-id="2ca3e-113">0</span></span>                                                             |
|  <span data-ttu-id="2ca3e-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="2ca3e-114">Symbolic Name</span></span>  |                                                             <span data-ttu-id="2ca3e-115">0</span><span class="sxs-lookup"><span data-stu-id="2ca3e-115">0</span></span>                                                             |
|  <span data-ttu-id="2ca3e-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="2ca3e-116">Message Text</span></span>   | <span data-ttu-id="2ca3e-117">单向端口不支持错误消息。</span><span class="sxs-lookup"><span data-stu-id="2ca3e-117">Fault messages are not supported on one-way ports.</span></span> <span data-ttu-id="2ca3e-118">更正服务说明"{0}"端口类型"{1}"，然后重新运行向导</span><span class="sxs-lookup"><span data-stu-id="2ca3e-118">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2ca3e-119">解释</span><span class="sxs-lookup"><span data-stu-id="2ca3e-119">Explanation</span></span>  
 <span data-ttu-id="2ca3e-120">此错误表示尝试使用该服务是单向服务且指定了错误。</span><span class="sxs-lookup"><span data-stu-id="2ca3e-120">This error indicates the service trying to be consumed is a one-way service and has the fault specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2ca3e-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="2ca3e-121">User Action</span></span>  
 <span data-ttu-id="2ca3e-122">通过切换到请求-响应从单向通信模式来更正该服务。</span><span class="sxs-lookup"><span data-stu-id="2ca3e-122">Correct the service by switching the communication pattern from one-way to request-response.</span></span> <span data-ttu-id="2ca3e-123">或在代码中删除该故障。</span><span class="sxs-lookup"><span data-stu-id="2ca3e-123">Or remove the fault in the code.</span></span>
 
 