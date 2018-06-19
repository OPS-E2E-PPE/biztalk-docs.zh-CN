---
title: SDK 示例 |Microsoft 文档
description: 适配器、 应用程序部署、 BAM、 业务规则、 业务流程、 管道，再 BizTalk Server 中提供的更多 SDK 示例
ms.custom: ''
ms.date: 10/17/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53bca653-e604-4452-8805-72632d3397c2
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5780e90260f591696e494411deff97a4cdc246f3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972827"
---
# <a name="samples-in-the-sdk"></a><span data-ttu-id="073e9-103">SDK 中的示例</span><span class="sxs-lookup"><span data-stu-id="073e9-103">Samples in the SDK</span></span>

## <a name="folder-paths"></a><span data-ttu-id="073e9-104">文件夹路径</span><span class="sxs-lookup"><span data-stu-id="073e9-104">Folder paths</span></span>
<span data-ttu-id="073e9-105">本部分介绍在 Microsoft 所含的 30 多个示例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]软件开发工具包 (SDK)。</span><span class="sxs-lookup"><span data-stu-id="073e9-105">This section describes more than 30 samples included in the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Software Development Kit (SDK).</span></span> <span data-ttu-id="073e9-106">本部分提供了有关每个示例的详细信息，其中包括有关如何生成和运行示例的说明以及可以期望出现的结果。</span><span class="sxs-lookup"><span data-stu-id="073e9-106">The section provides detailed information about each sample, including instructions for building the sample, how to run it, and what results to expect.</span></span>  
  
 <span data-ttu-id="073e9-107">示例文档使用路径缩写\<*示例路径*\>来表示你的安装中的示例的路径。</span><span class="sxs-lookup"><span data-stu-id="073e9-107">The samples documentation uses the path abbreviation \<*Samples Path*\> to denote the path to the samples in your installation.</span></span> <span data-ttu-id="073e9-108">默认路径会因安装时的相应设置而异。</span><span class="sxs-lookup"><span data-stu-id="073e9-108">The default for the path can vary based on decisions made during installation.</span></span> <span data-ttu-id="073e9-109">下表提供了常见安装方案的默认路径。</span><span class="sxs-lookup"><span data-stu-id="073e9-109">The following table provides the default path for common installation scenarios.</span></span>  
  
|<span data-ttu-id="073e9-110">Description</span><span class="sxs-lookup"><span data-stu-id="073e9-110">Description</span></span>|<span data-ttu-id="073e9-111">路径</span><span class="sxs-lookup"><span data-stu-id="073e9-111">Path</span></span>|  
|-----------------|----------|  
|<span data-ttu-id="073e9-112">在 32 位平台上安装</span><span class="sxs-lookup"><span data-stu-id="073e9-112">Installation on 32-bit platform</span></span>|[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="073e9-113">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="073e9-113">\SDK\Samples</span></span>|  
|<span data-ttu-id="073e9-114">在 64 位平台上安装。</span><span class="sxs-lookup"><span data-stu-id="073e9-114">Installation on a 64-bit platform.</span></span>|[!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)]<span data-ttu-id="073e9-115">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="073e9-115">\SDK\Samples</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="073e9-116">为了简便起见，此 SDK 中的示例和本文档假定您使用的是 BizTalk Server 的单个计算机开发人员版安装。</span><span class="sxs-lookup"><span data-stu-id="073e9-116">For the sake of simplicity, the samples in this SDK, and this documentation, assume that you are using a single computer developer installation of BizTalk Server.</span></span> <span data-ttu-id="073e9-117">如果不执行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的完整安装，则某些示例可能无法正常使用。</span><span class="sxs-lookup"><span data-stu-id="073e9-117">If you do not perform a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some samples may not work properly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="073e9-118">所有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK 项都以英语提供，仅在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的英语版本安装中受支持。</span><span class="sxs-lookup"><span data-stu-id="073e9-118">All of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK items are provided in English and are supported only for English-language installations of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="available-samples"></a><span data-ttu-id="073e9-119">可用示例</span><span class="sxs-lookup"><span data-stu-id="073e9-119">Available samples</span></span> 
  
-   [<span data-ttu-id="073e9-120">适配器示例 - 开发</span><span class="sxs-lookup"><span data-stu-id="073e9-120">Adapter Samples - Development</span></span>](../core/adapter-samples-development.md)  
  
-   [<span data-ttu-id="073e9-121">适配器示例 - 用法</span><span class="sxs-lookup"><span data-stu-id="073e9-121">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)  
  
-   [<span data-ttu-id="073e9-122">Admin（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="073e9-122">Admin (BizTalk Server Samples Folder)</span></span>](../core/admin-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="073e9-123">应用程序部署（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="073e9-123">Application Deployment (BizTalk Server Samples Folder)</span></span>](../core/application-deployment-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="073e9-124">业务活动监视（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="073e9-124">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>](../core/business-activity-monitoring-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="073e9-125">业务规则（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="073e9-125">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="073e9-126">EDI 和 AS2（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="073e9-126">EDI and AS2 (BizTalk Server Samples Folder)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="073e9-127">消息传送（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="073e9-127">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="073e9-128">业务流程（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="073e9-128">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="073e9-129">管道（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="073e9-129">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="073e9-130">SSO（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="073e9-130">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="073e9-131">XML 工具（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="073e9-131">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)