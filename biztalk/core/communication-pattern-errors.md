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
ms.openlocfilehash: ef9f7f4419d6c95b9b11343f395ab8e3d17c7c34
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021080"
---
# <a name="communication-pattern-errors"></a><span data-ttu-id="d4e5f-102">通信模式错误</span><span class="sxs-lookup"><span data-stu-id="d4e5f-102">Communication Pattern Errors</span></span>
<span data-ttu-id="d4e5f-103">诊断和解决 WCF 通信模式错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d4e5f-103">Information for diagnosing and resolving WCF Communication Pattern errors.</span></span>  

## <a name="fault-messages-are-not-supported-on-one-way-ports"></a><span data-ttu-id="d4e5f-104">单向端口不支持错误消息</span><span class="sxs-lookup"><span data-stu-id="d4e5f-104">Fault messages are not supported on one-way ports</span></span>
  
|                 |                                                       <span data-ttu-id="d4e5f-105">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="d4e5f-105">Error details</span></span>                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d4e5f-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="d4e5f-106">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| <span data-ttu-id="d4e5f-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="d4e5f-107">Product Version</span></span> |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    <span data-ttu-id="d4e5f-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d4e5f-108">Event ID</span></span>     |                                                             <span data-ttu-id="d4e5f-109">0</span><span class="sxs-lookup"><span data-stu-id="d4e5f-109">0</span></span>                                                             |
|  <span data-ttu-id="d4e5f-110">事件源</span><span class="sxs-lookup"><span data-stu-id="d4e5f-110">Event Source</span></span>   |                                                             <span data-ttu-id="d4e5f-111">0</span><span class="sxs-lookup"><span data-stu-id="d4e5f-111">0</span></span>                                                             |
|    <span data-ttu-id="d4e5f-112">组件</span><span class="sxs-lookup"><span data-stu-id="d4e5f-112">Component</span></span>    |                                                             <span data-ttu-id="d4e5f-113">0</span><span class="sxs-lookup"><span data-stu-id="d4e5f-113">0</span></span>                                                             |
|  <span data-ttu-id="d4e5f-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="d4e5f-114">Symbolic Name</span></span>  |                                                             <span data-ttu-id="d4e5f-115">0</span><span class="sxs-lookup"><span data-stu-id="d4e5f-115">0</span></span>                                                             |
|  <span data-ttu-id="d4e5f-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="d4e5f-116">Message Text</span></span>   | <span data-ttu-id="d4e5f-117">单向端口上不支持错误消息。</span><span class="sxs-lookup"><span data-stu-id="d4e5f-117">Fault messages are not supported on one-way ports.</span></span> <span data-ttu-id="d4e5f-118">更正服务说明"{0}"端口类型"{1}"，然后重新运行向导</span><span class="sxs-lookup"><span data-stu-id="d4e5f-118">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d4e5f-119">解释</span><span class="sxs-lookup"><span data-stu-id="d4e5f-119">Explanation</span></span>  
 <span data-ttu-id="d4e5f-120">此错误表示尝试使用的服务是单向服务，并且指定了错误。</span><span class="sxs-lookup"><span data-stu-id="d4e5f-120">This error indicates the service trying to be consumed is a one-way service and has the fault specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d4e5f-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="d4e5f-121">User Action</span></span>  
 <span data-ttu-id="d4e5f-122">通过将通信模式从单向模式切换到请求-响应模式来更正服务。</span><span class="sxs-lookup"><span data-stu-id="d4e5f-122">Correct the service by switching the communication pattern from one-way to request-response.</span></span> <span data-ttu-id="d4e5f-123">或者从代码中删除此错误。</span><span class="sxs-lookup"><span data-stu-id="d4e5f-123">Or remove the fault in the code.</span></span>
 
 