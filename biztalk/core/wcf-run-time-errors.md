---
title: WCF 运行时错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5591bd4-aa15-4c7a-903e-fc73b880692f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ca38035582fe8a8d37d66f61fbca820dd14c0c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267003"
---
# <a name="wcf-run-time-errors"></a><span data-ttu-id="43656-102">WCF 运行时错误</span><span class="sxs-lookup"><span data-stu-id="43656-102">WCF Run-Time Errors</span></span>
<span data-ttu-id="43656-103">有关诊断和解决 WCF 运行时事件的信息。</span><span class="sxs-lookup"><span data-stu-id="43656-103">Information for diagnosing and resolving WCF run-time events.</span></span>  
  
## <a name="wcf-service-host-restarted"></a><span data-ttu-id="43656-104">WCF 服务主机重新启动</span><span class="sxs-lookup"><span data-stu-id="43656-104">WCF service host restarted</span></span>
  
|                 |                                   <span data-ttu-id="43656-105">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="43656-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="43656-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="43656-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="43656-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="43656-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="43656-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="43656-108">Event ID</span></span>     |                                       <span data-ttu-id="43656-109">0x1FB0</span><span class="sxs-lookup"><span data-stu-id="43656-109">0x1FB0</span></span>                                       |
|  <span data-ttu-id="43656-110">事件源</span><span class="sxs-lookup"><span data-stu-id="43656-110">Event Source</span></span>   |                                         <span data-ttu-id="43656-111">0</span><span class="sxs-lookup"><span data-stu-id="43656-111">0</span></span>                                          |
|    <span data-ttu-id="43656-112">组件</span><span class="sxs-lookup"><span data-stu-id="43656-112">Component</span></span>    |                                         <span data-ttu-id="43656-113">0</span><span class="sxs-lookup"><span data-stu-id="43656-113">0</span></span>                                          |
|  <span data-ttu-id="43656-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="43656-114">Symbolic Name</span></span>  |                          <span data-ttu-id="43656-115">BTS_I_WCF_SERVICE_HOST_RESTARTED</span><span class="sxs-lookup"><span data-stu-id="43656-115">BTS_I_WCF_SERVICE_HOST_RESTARTED</span></span>                          |
|  <span data-ttu-id="43656-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="43656-116">Message Text</span></span>   |                                         <span data-ttu-id="43656-117">0</span><span class="sxs-lookup"><span data-stu-id="43656-117">0</span></span>                                          |
  
## <a name="explanation"></a><span data-ttu-id="43656-118">解释</span><span class="sxs-lookup"><span data-stu-id="43656-118">Explanation</span></span>  
 <span data-ttu-id="43656-119">此消息提供了一种让 WCF 适配器写入“信息性”事件日志项的方法（为适配器提供的 API 允许创建警告或错误，而不是信息）。</span><span class="sxs-lookup"><span data-stu-id="43656-119">This message provides a way for the WCF adapter to write an “informational” event log entry (the provided APIs for adapters allow the creation of warnings or errors, not information).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="43656-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="43656-120">User Action</span></span>  
 <span data-ttu-id="43656-121">如果您在事件日志中看到此信息性事件，则表示自动恢复已成功。</span><span class="sxs-lookup"><span data-stu-id="43656-121">If you see this informational event in the event log, it indicates that the auto-recovery has succeeded.</span></span> <span data-ttu-id="43656-122">关于此消息，无需执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="43656-122">No further action in regard to this message is necessary.</span></span>