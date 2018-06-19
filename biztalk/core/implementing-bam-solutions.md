---
title: 实现 BAM 解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18a5bc04-1b0a-4242-b599-760e696f5c06
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a167f2991250c446bedcb6bb235739f5414454e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257165"
---
# <a name="implementing-bam-solutions"></a><span data-ttu-id="8d43e-102">实现 BAM 解决方案</span><span class="sxs-lookup"><span data-stu-id="8d43e-102">Implementing BAM Solutions</span></span>
<span data-ttu-id="8d43e-103">本部分介绍的方式来实现 BAM 解决方案，包括捕获感兴趣数据，将数据发送到 BAM，并修改的数据将发送到 BAM 由于变化的业务需求。</span><span class="sxs-lookup"><span data-stu-id="8d43e-103">This section describes ways to implement your BAM solution, including capturing data of interest, sending data to BAM, and modifying the data you send to BAM as a result of changing business requirements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8d43e-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="8d43e-104">In This Section</span></span>  
  
-   [<span data-ttu-id="8d43e-105">安装 BAM 事件软件</span><span class="sxs-lookup"><span data-stu-id="8d43e-105">Installing the BAM-Eventing Software</span></span>](../core/installing-the-bam-eventing-software.md)  
  
-   [<span data-ttu-id="8d43e-106">跟踪配置文件编辑器</span><span class="sxs-lookup"><span data-stu-id="8d43e-106">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)  
  
-   [<span data-ttu-id="8d43e-107">实现事件流 BAM 活动</span><span class="sxs-lookup"><span data-stu-id="8d43e-107">Implementing BAM Activities with Event Streams</span></span>](../core/implementing-bam-activities-with-event-streams.md)  
  
-   [<span data-ttu-id="8d43e-108">BAM 侦听器是什么？</span><span class="sxs-lookup"><span data-stu-id="8d43e-108">What Is the BAM Interceptor?</span></span>](../core/what-is-the-bam-interceptor.md)  
  
-   [<span data-ttu-id="8d43e-109">如何创建自定义分析任务</span><span class="sxs-lookup"><span data-stu-id="8d43e-109">How to Create a Custom Analysis Task</span></span>](../core/how-to-create-a-custom-analysis-task.md)  
  
-   [<span data-ttu-id="8d43e-110">有关 BAM 事件发布的性能注意事项</span><span class="sxs-lookup"><span data-stu-id="8d43e-110">Performance Considerations for BAM Event Publishing</span></span>](../core/performance-considerations-for-bam-event-publishing.md)  
  
-   [<span data-ttu-id="8d43e-111">BAM 代码维护注意事项</span><span class="sxs-lookup"><span data-stu-id="8d43e-111">Considerations for BAM Code Maintenance</span></span>](../core/considerations-for-bam-code-maintenance.md)  
  
-   [<span data-ttu-id="8d43e-112">使用 BAM Api 的注意事项</span><span class="sxs-lookup"><span data-stu-id="8d43e-112">Considerations for Working with BAM APIs</span></span>](../core/considerations-for-working-with-bam-apis.md)  
  
-   [<span data-ttu-id="8d43e-113">如何使用查找 BAM 数据扩充</span><span class="sxs-lookup"><span data-stu-id="8d43e-113">How to Enrich BAM Data Using Lookups</span></span>](../core/how-to-enrich-bam-data-using-lookups.md)  
  
-   [<span data-ttu-id="8d43e-114">部署本地化的 BAM XML 文件</span><span class="sxs-lookup"><span data-stu-id="8d43e-114">Deploying Localized BAM XML Files</span></span>](../core/deploying-localized-bam-xml-files.md)  
  
-   [<span data-ttu-id="8d43e-115">使用 BAM WCF 和 WF 拦截器</span><span class="sxs-lookup"><span data-stu-id="8d43e-115">Using the BAM WCF and WF Interceptors</span></span>](../core/using-the-bam-wcf-and-wf-interceptors.md)