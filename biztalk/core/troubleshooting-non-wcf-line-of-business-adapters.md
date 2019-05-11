---
title: 故障排除非-WCF 业务线适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d5f7877-656f-406e-9edb-d6b9a0705b02
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6cf91a9219f385be1269420ef2965a643bbc29a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65296646"
---
# <a name="troubleshooting-non-wcf-line-of-business-adapters"></a><span data-ttu-id="82b44-102">故障排除非-WCF 业务线适配器</span><span class="sxs-lookup"><span data-stu-id="82b44-102">Troubleshooting non-WCF Line of Business Adapters</span></span>
## <a name="failed-to-retrieve-error"></a><span data-ttu-id="82b44-103">"无法检索"错误</span><span class="sxs-lookup"><span data-stu-id="82b44-103">“Failed to retrieve” error</span></span>  
 <span data-ttu-id="82b44-104">使用非-WCF 业务线 LOB 适配器时，可能会出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="82b44-104">When using a non-WCF Line of Business (LOB) adapter, the following errors may occur:</span></span>  
  
-   <span data-ttu-id="82b44-105">无法检索系统</span><span class="sxs-lookup"><span data-stu-id="82b44-105">Failed to retrieve system</span></span>  
  
-   <span data-ttu-id="82b44-106">浏览代理：在构造函数中捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="82b44-106">Browsing agent: Error trapped in constructor.</span></span> <span data-ttu-id="82b44-107">目标计算机主动拒绝连接。</span><span class="sxs-lookup"><span data-stu-id="82b44-107">Target machine Actively refused connection.</span></span>  
  
-   <span data-ttu-id="82b44-108">运行时代理：在构造函数中捕获的错误。</span><span class="sxs-lookup"><span data-stu-id="82b44-108">Runtime agent: Error trapped in constructor.</span></span> <span data-ttu-id="82b44-109">目标计算机主动拒绝连接。</span><span class="sxs-lookup"><span data-stu-id="82b44-109">Target machine Actively refused connection.</span></span>  
  
### <a name="cause"></a><span data-ttu-id="82b44-110">原因</span><span class="sxs-lookup"><span data-stu-id="82b44-110">Cause</span></span>  
 <span data-ttu-id="82b44-111">LOB 适配器使用.Net 远程处理。</span><span class="sxs-lookup"><span data-stu-id="82b44-111">The LOB adapters use .Net Remoting.</span></span> <span data-ttu-id="82b44-112">如果.Net 远程处理激活花费的时间超过预期，适配器可能会返回这些错误。</span><span class="sxs-lookup"><span data-stu-id="82b44-112">If the .Net Remoting activation takes longer than expected, the adapter may return these errors.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="82b44-113">解决方法</span><span class="sxs-lookup"><span data-stu-id="82b44-113">Resolution</span></span>  
 <span data-ttu-id="82b44-114">创建**StartAgentSleep**注册表项并增大超时值：</span><span class="sxs-lookup"><span data-stu-id="82b44-114">Create the **StartAgentSleep** registry key and increase the timeout value:</span></span>  
  
1. <span data-ttu-id="82b44-115">打开注册表并转到*HKEY_LOCAL_MACHINE\software\Microsoft\BizTalkAdapters*。</span><span class="sxs-lookup"><span data-stu-id="82b44-115">Open the registry and go to *HKEY_LOCAL_MACHINE\software\Microsoft\BizTalkAdapters*.</span></span>  
  
2. <span data-ttu-id="82b44-116">创建新的 DWORD 值具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="82b44-116">Create a new DWORD value with the following properties:</span></span>  
  
    <span data-ttu-id="82b44-117">名称：StartAgentSleep</span><span class="sxs-lookup"><span data-stu-id="82b44-117">Name: StartAgentSleep</span></span>  
  
    <span data-ttu-id="82b44-118">基址：Decimal</span><span class="sxs-lookup"><span data-stu-id="82b44-118">Base: Decimal</span></span>  
  
    <span data-ttu-id="82b44-119">值数据：1000</span><span class="sxs-lookup"><span data-stu-id="82b44-119">Value data: 1000</span></span>  
  
   <span data-ttu-id="82b44-120">值数据以毫秒 (ms) 为单位。</span><span class="sxs-lookup"><span data-stu-id="82b44-120">Value data is measured in milliseconds (ms).</span></span> <span data-ttu-id="82b44-121">1000 毫秒等于 1 秒。</span><span class="sxs-lookup"><span data-stu-id="82b44-121">1000ms equals 1 second.</span></span>  
  
   <span data-ttu-id="82b44-122">在某些系统中，一秒可能不够。</span><span class="sxs-lookup"><span data-stu-id="82b44-122">In some systems, one second may not be enough.</span></span> <span data-ttu-id="82b44-123">增大该值并进行测试，以帮助确定所需的适当超时值。</span><span class="sxs-lookup"><span data-stu-id="82b44-123">Increase the value and test to help determine the appropriate timeout needed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="82b44-124">添加**StartAgentSleep**注册表项会影响**所有**非 WCF LOB 适配器。</span><span class="sxs-lookup"><span data-stu-id="82b44-124">Adding the **StartAgentSleep** registry key impacts **all** the non-WCF LOB adapters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b44-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="82b44-125">See Also</span></span>  
 [<span data-ttu-id="82b44-126">BizTalk Server 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="82b44-126">Troubleshooting BizTalk Server Adapters</span></span>](../core/troubleshooting-biztalk-server-adapters.md)