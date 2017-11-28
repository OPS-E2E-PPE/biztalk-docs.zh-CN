---
title: "解决性能问题与 Oracle 数据库适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance issues, troubleshooting
- troubleshooting, performance issues
ms.assetid: 2035cd2e-ce87-419b-aada-61d257671623
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20b0f8db3f1b7549f6189b348b7353d6dac159a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-performance-issues-with-the-oracle-database-adapter"></a><span data-ttu-id="3f0b4-102">解决与 Oracle 数据库适配器的性能问题</span><span class="sxs-lookup"><span data-stu-id="3f0b4-102">Troubleshoot performance issues with the Oracle Database adapter</span></span>
<span data-ttu-id="3f0b4-103">本部分讨论如何使用故障排除方法来解决在使用时可能遇到的性能问题[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3f0b4-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="3f0b4-104">已知的问题</span><span class="sxs-lookup"><span data-stu-id="3f0b4-104">Known Issue</span></span>  
 <span data-ttu-id="3f0b4-105">以下是使用时可能遇到的最常见性能问题[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，以及其可能的原因和解决方法。</span><span class="sxs-lookup"><span data-stu-id="3f0b4-105">The following is the most common performance issue you might encounter when using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], along with its probable cause and resolution.</span></span>  
  
##  <span data-ttu-id="3f0b4-106"><a name="BKMK_Slowdown"></a>缓慢或吞吐量与 BizTalk Server 使用适配器时停止</span><span class="sxs-lookup"><span data-stu-id="3f0b4-106"><a name="BKMK_Slowdown"></a> Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="3f0b4-107">**问题**</span><span class="sxs-lookup"><span data-stu-id="3f0b4-107">**Problem**</span></span>  
  
 <span data-ttu-id="3f0b4-108">使用时[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，由适配器发送或接收的消息数变慢或进入停止。</span><span class="sxs-lookup"><span data-stu-id="3f0b4-108">When using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="3f0b4-109">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="3f0b4-109">**Cause**</span></span>  
  
 <span data-ttu-id="3f0b4-110">**EnableBizTalkCompatibilityMode**绑定属性未设置在 WCF 自定义上发送或接收 BizTalk Server 管理控制台中的端口。</span><span class="sxs-lookup"><span data-stu-id="3f0b4-110">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="3f0b4-111">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="3f0b4-111">**Resolution**</span></span>  
  
 <span data-ttu-id="3f0b4-112">设置**EnableBizTalkCompatibilityMode**绑定属性为 True。</span><span class="sxs-lookup"><span data-stu-id="3f0b4-112">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="3f0b4-113">有关此属性的详细信息，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0b4-113">For more information about this property, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span> <span data-ttu-id="3f0b4-114">有关如何设置绑定属性的说明，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="3f0b4-114">For instructions on how to set a binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
### <a name="possible-memory-leak-on-a-64-bit-computer-when-using-the-oracle-database-adapter-to-perform-operations-involving-float-data-type"></a><span data-ttu-id="3f0b4-115">当使用 Oracle 数据库适配器执行涉及 FLOAT 数据类型的操作的 64 位计算机上可能的内存泄漏</span><span class="sxs-lookup"><span data-stu-id="3f0b4-115">Possible memory leak on a 64-bit computer when using the Oracle database adapter to perform operations involving FLOAT data type</span></span>  
 <span data-ttu-id="3f0b4-116">**问题**</span><span class="sxs-lookup"><span data-stu-id="3f0b4-116">**Problem**</span></span>  
  
 <span data-ttu-id="3f0b4-117">使用时，你可能会遇到内存泄漏[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行涉及 FLOAT 数据类型的操作的 64 位计算机上。</span><span class="sxs-lookup"><span data-stu-id="3f0b4-117">You may experience a memory leak when using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] on a 64-bit computer to perform operations that involve FLOAT data types.</span></span>  
  
 <span data-ttu-id="3f0b4-118">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="3f0b4-118">**Resolution**</span></span>  
  
 <span data-ttu-id="3f0b4-119">安装.NET \<*版本*> (x64) 64 位计算机上的。</span><span class="sxs-lookup"><span data-stu-id="3f0b4-119">Install .NET \<*version*> (x64) on the 64-bit computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0b4-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f0b4-120">See Also</span></span>  
[<span data-ttu-id="3f0b4-121">解决 Oracle 数据库 adapter.md</span><span class="sxs-lookup"><span data-stu-id="3f0b4-121">Troubleshoot the Oracle Database adapter.md</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)