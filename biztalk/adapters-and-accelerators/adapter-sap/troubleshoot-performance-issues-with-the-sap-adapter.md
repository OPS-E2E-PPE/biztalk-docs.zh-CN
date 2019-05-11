---
title: 使用 SAP 适配器进行性能问题故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, performance
- performance, troubleshooting
ms.assetid: 7e8e9fec-0edf-4c67-837c-0e271b2ffe68
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c44bf56f73cd23de36e53ae6f0720d863e4f694e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372386"
---
# <a name="troubleshoot-performance-issues-with-the-sap-adapter"></a><span data-ttu-id="9084c-102">使用 SAP 适配器进行故障排除性能问题：</span><span class="sxs-lookup"><span data-stu-id="9084c-102">Troubleshoot Performance Issues with the SAP adapter</span></span>
<span data-ttu-id="9084c-103">本部分讨论如何使用故障排除技术来解决使用时可能遇到的性能问题[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9084c-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
##  <a name="BKMK_SAPSlowdown"></a> <span data-ttu-id="9084c-104">缓慢或停滞在使用适配器与 BizTalk Server 时的吞吐量</span><span class="sxs-lookup"><span data-stu-id="9084c-104">Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="9084c-105">**问题**</span><span class="sxs-lookup"><span data-stu-id="9084c-105">**Problem**</span></span>  
  
 <span data-ttu-id="9084c-106">使用时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，消息发送或接收的适配器数速度变慢或进入停滞。</span><span class="sxs-lookup"><span data-stu-id="9084c-106">When using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="9084c-107">**原因**</span><span class="sxs-lookup"><span data-stu-id="9084c-107">**Cause**</span></span>  
  
 <span data-ttu-id="9084c-108">**EnableBizTalkCompatibilityMode**绑定属性中未设置 WCF 自定义发送或接收端口在 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="9084c-108">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration Console.</span></span>  
  
 <span data-ttu-id="9084c-109">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="9084c-109">**Resolution**</span></span>  
  
 <span data-ttu-id="9084c-110">设置**EnableBizTalkCompatibilityMode**绑定属性为 True。</span><span class="sxs-lookup"><span data-stu-id="9084c-110">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="9084c-111">有关此属性的详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="9084c-111">For more information about this property, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span> <span data-ttu-id="9084c-112">有关如何设置绑定属性的说明，请参阅[配置的 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="9084c-112">For instructions on how to set a binding property, see [Configure the binding properties for the SAP adapter](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).</span></span>  
  
##  <a name="BKMK_SAPMemLeak"></a> <span data-ttu-id="9084c-113">使用参数的 NULL 值时可能出现的内存泄漏</span><span class="sxs-lookup"><span data-stu-id="9084c-113">Possible memory leak when using NULL values for parameters</span></span>  
 <span data-ttu-id="9084c-114">**问题**</span><span class="sxs-lookup"><span data-stu-id="9084c-114">**Problem**</span></span>  
  
 <span data-ttu-id="9084c-115">您可能会观察到内存泄漏如果调用 SAP 系统中的项目时未指定输入或表参数的值。</span><span class="sxs-lookup"><span data-stu-id="9084c-115">You may observe memory leak if you do not specify values for input or table parameters while invoking artifacts in the SAP system.</span></span>  
  
 <span data-ttu-id="9084c-116">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="9084c-116">**Resolution**</span></span>  
  
 <span data-ttu-id="9084c-117">请确保在 SAP 系统中调用项目时指定的输入和表的所有参数的值。</span><span class="sxs-lookup"><span data-stu-id="9084c-117">Make sure you specify values for all the input and table parameters while invoking an artifact in the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9084c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9084c-118">See Also</span></span>  
[<span data-ttu-id="9084c-119">SAP 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="9084c-119">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)