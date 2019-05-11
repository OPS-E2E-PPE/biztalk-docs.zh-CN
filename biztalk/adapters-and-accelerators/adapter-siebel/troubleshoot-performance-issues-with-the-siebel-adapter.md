---
title: 使用 Siebel 适配器进行性能问题故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance issues
- performance, troubleshooting
ms.assetid: fe413b15-f703-4148-99df-17b5be3c74c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2c5ecd89cfe3ea284bdc3264e8db597f29fdde7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370406"
---
# <a name="troubleshoot-performance-issues-with-the-siebel-adapter"></a><span data-ttu-id="4c8d3-102">使用 Siebel 适配器进行故障排除性能问题：</span><span class="sxs-lookup"><span data-stu-id="4c8d3-102">Troubleshoot Performance Issues with the Siebel adapter</span></span>
<span data-ttu-id="4c8d3-103">本部分讨论如何使用故障排除技术来解决使用时可能遇到的性能问题[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4c8d3-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="4c8d3-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="4c8d3-104">Known Issues</span></span>  
  
###  <a name="slowdown-or-stall-in-throughput-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="4c8d3-105">缓慢或停滞在使用适配器与 BizTalk Server 时的吞吐量</span><span class="sxs-lookup"><span data-stu-id="4c8d3-105">Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="4c8d3-106">**问题**</span><span class="sxs-lookup"><span data-stu-id="4c8d3-106">**Problem**</span></span>  
  
 <span data-ttu-id="4c8d3-107">使用时[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，消息发送或接收的适配器数速度变慢或进入停滞。</span><span class="sxs-lookup"><span data-stu-id="4c8d3-107">When using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="4c8d3-108">**原因**</span><span class="sxs-lookup"><span data-stu-id="4c8d3-108">**Cause**</span></span>  
  
 <span data-ttu-id="4c8d3-109">**EnableBizTalkCompatibilityMode**绑定属性中未设置 WCF 自定义发送或接收端口在 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4c8d3-109">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="4c8d3-110">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="4c8d3-110">**Resolution**</span></span>  
  
 <span data-ttu-id="4c8d3-111">设置**EnableBizTalkCompatibilityMode**绑定属性为 True。</span><span class="sxs-lookup"><span data-stu-id="4c8d3-111">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="4c8d3-112">有关此属性的详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="4c8d3-112">For more information about this property, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span> <span data-ttu-id="4c8d3-113">有关如何设置绑定属性的说明，请参阅[配置的绑定属性用于 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="4c8d3-113">For instructions on how to set a binding property, see [Configure the binding properties for Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c8d3-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c8d3-114">See Also</span></span>  
[<span data-ttu-id="4c8d3-115">Siebel 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="4c8d3-115">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)