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
ms.openlocfilehash: df75d019b9af36f4ef7fce21ea17dc1e9a8e7aac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999926"
---
# <a name="wcf-run-time-errors"></a><span data-ttu-id="8a394-102">WCF 运行时错误</span><span class="sxs-lookup"><span data-stu-id="8a394-102">WCF Run-Time Errors</span></span>
<span data-ttu-id="8a394-103">有关诊断和解决 WCF 运行时事件的信息。</span><span class="sxs-lookup"><span data-stu-id="8a394-103">Information for diagnosing and resolving WCF run-time events.</span></span>  
  
## <a name="wcf-service-host-restarted"></a><span data-ttu-id="8a394-104">WCF 服务主机重新启动</span><span class="sxs-lookup"><span data-stu-id="8a394-104">WCF service host restarted</span></span>
  
|                 |                                   <span data-ttu-id="8a394-105">错误详细信息</span><span class="sxs-lookup"><span data-stu-id="8a394-105">Error details</span></span>                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="8a394-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="8a394-106">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="8a394-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="8a394-107">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="8a394-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8a394-108">Event ID</span></span>     |                                       <span data-ttu-id="8a394-109">0x1FB0</span><span class="sxs-lookup"><span data-stu-id="8a394-109">0x1FB0</span></span>                                       |
|  <span data-ttu-id="8a394-110">事件源</span><span class="sxs-lookup"><span data-stu-id="8a394-110">Event Source</span></span>   |                                         <span data-ttu-id="8a394-111">0</span><span class="sxs-lookup"><span data-stu-id="8a394-111">0</span></span>                                          |
|    <span data-ttu-id="8a394-112">组件</span><span class="sxs-lookup"><span data-stu-id="8a394-112">Component</span></span>    |                                         <span data-ttu-id="8a394-113">0</span><span class="sxs-lookup"><span data-stu-id="8a394-113">0</span></span>                                          |
|  <span data-ttu-id="8a394-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="8a394-114">Symbolic Name</span></span>  |                          <span data-ttu-id="8a394-115">BTS_I_WCF_SERVICE_HOST_RESTARTED</span><span class="sxs-lookup"><span data-stu-id="8a394-115">BTS_I_WCF_SERVICE_HOST_RESTARTED</span></span>                          |
|  <span data-ttu-id="8a394-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="8a394-116">Message Text</span></span>   |                                         <span data-ttu-id="8a394-117">0</span><span class="sxs-lookup"><span data-stu-id="8a394-117">0</span></span>                                          |
  
## <a name="explanation"></a><span data-ttu-id="8a394-118">解释</span><span class="sxs-lookup"><span data-stu-id="8a394-118">Explanation</span></span>  
 <span data-ttu-id="8a394-119">此消息提供了一种让 WCF 适配器写入“信息性”事件日志项的方法（为适配器提供的 API 允许创建警告或错误，而不是信息）。</span><span class="sxs-lookup"><span data-stu-id="8a394-119">This message provides a way for the WCF adapter to write an “informational” event log entry (the provided APIs for adapters allow the creation of warnings or errors, not information).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8a394-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="8a394-120">User Action</span></span>  
 <span data-ttu-id="8a394-121">如果您在事件日志中看到此信息性事件，则表示自动恢复已成功。</span><span class="sxs-lookup"><span data-stu-id="8a394-121">If you see this informational event in the event log, it indicates that the auto-recovery has succeeded.</span></span> <span data-ttu-id="8a394-122">关于此消息，无需执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="8a394-122">No further action in regard to this message is necessary.</span></span>