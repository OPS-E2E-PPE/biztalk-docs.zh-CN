---
title: "使用 BAM WCF 和 WF 拦截器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a87a643-8e15-47d1-8d2a-3d899a1494ff
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ea631ed3a9058128a71373b6e6c7eb55ebad6c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="5cf87-102">使用 BAM WCF 和 WF 侦听器</span><span class="sxs-lookup"><span data-stu-id="5cf87-102">Using the BAM WCF and WF Interceptors</span></span>
<span data-ttu-id="5cf87-103">BAM 侦听器将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 BAM 侦听器功能扩展到 Windows Workflow Foundation (WF)、Windows Communication Framework (WCF) 和其他运行时环境中。</span><span class="sxs-lookup"><span data-stu-id="5cf87-103">BAM interceptors extend the BAM interceptor functionality for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] into Windows Workflow Foundation (WF), Windows Communication Framework (WCF), and other runtime environments.</span></span> <span data-ttu-id="5cf87-104">通过使用 BAM 侦听器，您可以跟踪业务流程而不必重新编译 WF 或 WCF 解决方案。通过一个配置文件即可实现集成，此配置文件使用了 XML 和一系列将应用程序事件映射至 BAM 活动并定义数据、相关 ID、继续标记和其他必需及可选项目的元素。</span><span class="sxs-lookup"><span data-stu-id="5cf87-104">By using a BAM interceptor, you can track your business processes without recompiling your WF or WCF solution — integration is done through a configuration file using XML and a series of elements that map application events to BAM activities and define the data, correlation ID, continuation token and other required and optional artifacts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5cf87-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="5cf87-105">In This Section</span></span>  
  
-   [<span data-ttu-id="5cf87-106">BAM WCF 和 WF 拦截器有哪些？</span><span class="sxs-lookup"><span data-stu-id="5cf87-106">What Are the BAM WCF and WF Interceptors?</span></span>](../core/what-are-the-bam-wcf-and-wf-interceptors.md)  
  
-   [<span data-ttu-id="5cf87-107">BAM WCF 和 WF 拦截器已知的问题</span><span class="sxs-lookup"><span data-stu-id="5cf87-107">Known Issues with the BAM WCF and WF Interceptors</span></span>](../core/known-issues-with-the-bam-wcf-and-wf-interceptors.md)  
  
-   [<span data-ttu-id="5cf87-108">在高可用性环境中的 BAM 拦截器</span><span class="sxs-lookup"><span data-stu-id="5cf87-108">BAM Interceptors in a High Availability Environment</span></span>](../core/bam-interceptors-in-a-high-availability-environment.md)  
  
-   [<span data-ttu-id="5cf87-109">BAM 拦截器性能计数器</span><span class="sxs-lookup"><span data-stu-id="5cf87-109">BAM Interceptor Performance Counters</span></span>](../core/bam-interceptor-performance-counters.md)  
  
-   [<span data-ttu-id="5cf87-110">加载 BAM 拦截器使用 BAM API</span><span class="sxs-lookup"><span data-stu-id="5cf87-110">Loading BAM Interceptors Using the BAM API</span></span>](../core/loading-bam-interceptors-using-the-bam-api.md)  
  
-   [<span data-ttu-id="5cf87-111">故障排除 BAM 拦截器</span><span class="sxs-lookup"><span data-stu-id="5cf87-111">Troubleshooting BAM Interceptors</span></span>](../core/troubleshooting-bam-interceptors.md)  
  
-   [<span data-ttu-id="5cf87-112">BAM 拦截器的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="5cf87-112">Security Considerations for BAM Interceptors</span></span>](../core/security-considerations-for-bam-interceptors.md)  
  
-   [<span data-ttu-id="5cf87-113">拦截器配置文件</span><span class="sxs-lookup"><span data-stu-id="5cf87-113">Interceptor Configuration File</span></span>](../core/interceptor-configuration-file.md)  
  
-   [<span data-ttu-id="5cf87-114">BAM WF 拦截器</span><span class="sxs-lookup"><span data-stu-id="5cf87-114">BAM WF Interceptor</span></span>](../core/bam-wf-interceptor.md)  
  
-   [<span data-ttu-id="5cf87-115">配置 WCF 适配器以截获 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="5cf87-115">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)  
  
-   [<span data-ttu-id="5cf87-116">BAM WCF 拦截器</span><span class="sxs-lookup"><span data-stu-id="5cf87-116">BAM WCF Interceptor</span></span>](../core/bam-wcf-interceptor.md)