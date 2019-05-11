---
title: 使用 BAM WCF 和 WF 侦听器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a87a643-8e15-47d1-8d2a-3d899a1494ff
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb9d025e4ffae6561b885e76952f0d0c310dbdcf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320993"
---
# <a name="using-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="19dec-102">使用 BAM WCF 和 WF 侦听器</span><span class="sxs-lookup"><span data-stu-id="19dec-102">Using the BAM WCF and WF Interceptors</span></span>
<span data-ttu-id="19dec-103">BAM 侦听器将扩展的 BAM 侦听器功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 Windows Workflow Foundation (WF)、 Windows Communication Framework (WCF) 和其他运行时环境。</span><span class="sxs-lookup"><span data-stu-id="19dec-103">BAM interceptors extend the BAM interceptor functionality for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] into Windows Workflow Foundation (WF), Windows Communication Framework (WCF), and other runtime environments.</span></span> <span data-ttu-id="19dec-104">通过使用 BAM 侦听器，可以跟踪业务流程，无需重新编译 WF 或 WCF 解决方案 — 通过配置文件使用 XML 和一系列元素，将应用程序事件映射到 BAM 活动定义的数据进行集成相关 ID、 继续标记和其他必需和可选项目。</span><span class="sxs-lookup"><span data-stu-id="19dec-104">By using a BAM interceptor, you can track your business processes without recompiling your WF or WCF solution — integration is done through a configuration file using XML and a series of elements that map application events to BAM activities and define the data, correlation ID, continuation token and other required and optional artifacts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19dec-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="19dec-105">In This Section</span></span>  
  
-   [<span data-ttu-id="19dec-106">BAM WCF 和 WF 侦听器概述</span><span class="sxs-lookup"><span data-stu-id="19dec-106">What Are the BAM WCF and WF Interceptors?</span></span>](../core/what-are-the-bam-wcf-and-wf-interceptors.md)  
  
-   [<span data-ttu-id="19dec-107">BAM WCF 和 WF 侦听器的已知问题</span><span class="sxs-lookup"><span data-stu-id="19dec-107">Known Issues with the BAM WCF and WF Interceptors</span></span>](../core/known-issues-with-the-bam-wcf-and-wf-interceptors.md)  
  
-   [<span data-ttu-id="19dec-108">高可用性环境中的 BAM 侦听器</span><span class="sxs-lookup"><span data-stu-id="19dec-108">BAM Interceptors in a High Availability Environment</span></span>](../core/bam-interceptors-in-a-high-availability-environment.md)  
  
-   [<span data-ttu-id="19dec-109">BAM 侦听器性能计数器</span><span class="sxs-lookup"><span data-stu-id="19dec-109">BAM Interceptor Performance Counters</span></span>](../core/bam-interceptor-performance-counters.md)  
  
-   [<span data-ttu-id="19dec-110">使用 BAM API 加载 BAM 侦听器</span><span class="sxs-lookup"><span data-stu-id="19dec-110">Loading BAM Interceptors Using the BAM API</span></span>](../core/loading-bam-interceptors-using-the-bam-api.md)  
  
-   [<span data-ttu-id="19dec-111">BAM 侦听器疑难解答</span><span class="sxs-lookup"><span data-stu-id="19dec-111">Troubleshooting BAM Interceptors</span></span>](../core/troubleshooting-bam-interceptors.md)  
  
-   [<span data-ttu-id="19dec-112">BAM 侦听器的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="19dec-112">Security Considerations for BAM Interceptors</span></span>](../core/security-considerations-for-bam-interceptors.md)  
  
-   [<span data-ttu-id="19dec-113">侦听器配置文件</span><span class="sxs-lookup"><span data-stu-id="19dec-113">Interceptor Configuration File</span></span>](../core/interceptor-configuration-file.md)  
  
-   [<span data-ttu-id="19dec-114">BAM WF 侦听器</span><span class="sxs-lookup"><span data-stu-id="19dec-114">BAM WF Interceptor</span></span>](../core/bam-wf-interceptor.md)  
  
-   [<span data-ttu-id="19dec-115">配置 WCF 适配器以侦听 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="19dec-115">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)  
  
-   [<span data-ttu-id="19dec-116">BAM WCF 侦听器</span><span class="sxs-lookup"><span data-stu-id="19dec-116">BAM WCF Interceptor</span></span>](../core/bam-wcf-interceptor.md)