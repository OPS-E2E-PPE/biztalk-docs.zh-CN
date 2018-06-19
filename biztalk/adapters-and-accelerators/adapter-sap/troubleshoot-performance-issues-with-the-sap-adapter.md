---
title: 解决性能问题与 SAP 适配器 |Microsoft 文档
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
ms.openlocfilehash: ef9e18a2f26af993da36a13d389f2aff2ad2f60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217117"
---
# <a name="troubleshoot-performance-issues-with-the-sap-adapter"></a><span data-ttu-id="7f988-102">与 SAP 适配器解决性能问题</span><span class="sxs-lookup"><span data-stu-id="7f988-102">Troubleshoot Performance Issues with the SAP adapter</span></span>
<span data-ttu-id="7f988-103">本部分讨论如何使用故障排除方法来解决在使用时可能遇到的性能问题[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7f988-103">This section discusses using troubleshooting techniques to resolve performance issues that you might encounter when using [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
##  <a name="BKMK_SAPSlowdown"></a><span data-ttu-id="7f988-104">缓慢或吞吐量与 BizTalk Server 使用适配器时停止</span><span class="sxs-lookup"><span data-stu-id="7f988-104">Slowdown or stall in throughput when using the adapter with BizTalk Server</span></span>  
 <span data-ttu-id="7f988-105">**问题**</span><span class="sxs-lookup"><span data-stu-id="7f988-105">**Problem**</span></span>  
  
 <span data-ttu-id="7f988-106">使用时[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，由适配器发送或接收的消息数变慢或进入停止。</span><span class="sxs-lookup"><span data-stu-id="7f988-106">When using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the number of messages sent or received by the adapter slows down or comes to a stall.</span></span>  
  
 <span data-ttu-id="7f988-107">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="7f988-107">**Cause**</span></span>  
  
 <span data-ttu-id="7f988-108">**EnableBizTalkCompatibilityMode**绑定属性未设置在 WCF 自定义上发送或接收 BizTalk Server 管理控制台中的端口。</span><span class="sxs-lookup"><span data-stu-id="7f988-108">The **EnableBizTalkCompatibilityMode** binding property is not set on the WCF-Custom send or receive port in BizTalk Server Administration Console.</span></span>  
  
 <span data-ttu-id="7f988-109">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="7f988-109">**Resolution**</span></span>  
  
 <span data-ttu-id="7f988-110">设置**EnableBizTalkCompatibilityMode**绑定属性为 True。</span><span class="sxs-lookup"><span data-stu-id="7f988-110">Set the **EnableBizTalkCompatibilityMode** binding property to True.</span></span> <span data-ttu-id="7f988-111">有关此属性的详细信息，请参阅[了解针对 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7f988-111">For more information about this property, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span> <span data-ttu-id="7f988-112">有关如何设置绑定属性的说明，请参阅[配置 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="7f988-112">For instructions on how to set a binding property, see [Configure the binding properties for the SAP adapter](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md).</span></span>  
  
##  <a name="BKMK_SAPMemLeak"></a><span data-ttu-id="7f988-113">可能的内存泄漏时参数的使用 NULL 值</span><span class="sxs-lookup"><span data-stu-id="7f988-113">Possible memory leak when using NULL values for parameters</span></span>  
 <span data-ttu-id="7f988-114">**问题**</span><span class="sxs-lookup"><span data-stu-id="7f988-114">**Problem**</span></span>  
  
 <span data-ttu-id="7f988-115">你可能会观察内存泄漏如果 SAP 系统中调用项目时未指定输入或表参数的值。</span><span class="sxs-lookup"><span data-stu-id="7f988-115">You may observe memory leak if you do not specify values for input or table parameters while invoking artifacts in the SAP system.</span></span>  
  
 <span data-ttu-id="7f988-116">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="7f988-116">**Resolution**</span></span>  
  
 <span data-ttu-id="7f988-117">请确保在调用 SAP 系统中的项目时指定的输入和表的所有参数的值。</span><span class="sxs-lookup"><span data-stu-id="7f988-117">Make sure you specify values for all the input and table parameters while invoking an artifact in the SAP system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f988-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f988-118">See Also</span></span>  
[<span data-ttu-id="7f988-119">故障排除 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="7f988-119">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)