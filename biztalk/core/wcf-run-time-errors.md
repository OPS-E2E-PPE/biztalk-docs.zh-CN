---
title: WCF 运行时错误 |Microsoft 文档
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
ms.openlocfilehash: 97f4107ddf791b8d9fd152f2258cd3185f23498f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288189"
---
# <a name="wcf-run-time-errors"></a><span data-ttu-id="8adf5-102">WCF 运行时错误</span><span class="sxs-lookup"><span data-stu-id="8adf5-102">WCF Run-Time Errors</span></span>
<span data-ttu-id="8adf5-103">用于诊断和解决 WCF 运行时事件的信息。</span><span class="sxs-lookup"><span data-stu-id="8adf5-103">Information for diagnosing and resolving WCF run-time events.</span></span>  
  
## <a name="wcf-service-host-restarted"></a><span data-ttu-id="8adf5-104">WCF 服务主机重新启动</span><span class="sxs-lookup"><span data-stu-id="8adf5-104">WCF service host restarted</span></span>
  
||<span data-ttu-id="8adf5-105">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="8adf5-105">Error details</span></span>|  
|-|-|  
|<span data-ttu-id="8adf5-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="8adf5-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="8adf5-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="8adf5-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="8adf5-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8adf5-108">Event ID</span></span>|<span data-ttu-id="8adf5-109">0x1FB0</span><span class="sxs-lookup"><span data-stu-id="8adf5-109">0x1FB0</span></span>|  
|<span data-ttu-id="8adf5-110">事件源</span><span class="sxs-lookup"><span data-stu-id="8adf5-110">Event Source</span></span>|<span data-ttu-id="8adf5-111">0</span><span class="sxs-lookup"><span data-stu-id="8adf5-111">0</span></span>|  
|<span data-ttu-id="8adf5-112">组件</span><span class="sxs-lookup"><span data-stu-id="8adf5-112">Component</span></span>|<span data-ttu-id="8adf5-113">0</span><span class="sxs-lookup"><span data-stu-id="8adf5-113">0</span></span>|  
|<span data-ttu-id="8adf5-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="8adf5-114">Symbolic Name</span></span>|<span data-ttu-id="8adf5-115">BTS_I_WCF_SERVICE_HOST_RESTARTED</span><span class="sxs-lookup"><span data-stu-id="8adf5-115">BTS_I_WCF_SERVICE_HOST_RESTARTED</span></span>|  
|<span data-ttu-id="8adf5-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="8adf5-116">Message Text</span></span>|<span data-ttu-id="8adf5-117">0</span><span class="sxs-lookup"><span data-stu-id="8adf5-117">0</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8adf5-118">解释</span><span class="sxs-lookup"><span data-stu-id="8adf5-118">Explanation</span></span>  
 <span data-ttu-id="8adf5-119">此消息提供了一种让 WCF 适配器写入“信息性”事件日志项的方法（为适配器提供的 API 允许创建警告或错误，而不是信息）。</span><span class="sxs-lookup"><span data-stu-id="8adf5-119">This message provides a way for the WCF adapter to write an “informational” event log entry (the provided APIs for adapters allow the creation of warnings or errors, not information).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8adf5-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="8adf5-120">User Action</span></span>  
 <span data-ttu-id="8adf5-121">如果您在事件日志中看到此信息性事件，则表示自动恢复已成功。</span><span class="sxs-lookup"><span data-stu-id="8adf5-121">If you see this informational event in the event log, it indicates that the auto-recovery has succeeded.</span></span> <span data-ttu-id="8adf5-122">关于此消息，无需执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="8adf5-122">No further action in regard to this message is necessary.</span></span>