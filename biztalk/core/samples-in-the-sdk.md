---
title: SDK 示例 |Microsoft Docs
description: 适配器、 应用程序部署、 BAM、 业务规则、 业务流程、 管道和多个 BizTalk Server 中可用的 SDK 示例
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
ms.openlocfilehash: a5dc386b29a2b6070a50570080697d2a54ed537b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009454"
---
# <a name="samples-in-the-sdk"></a><span data-ttu-id="cc5b0-103">SDK 中的示例</span><span class="sxs-lookup"><span data-stu-id="cc5b0-103">Samples in the SDK</span></span>

## <a name="folder-paths"></a><span data-ttu-id="cc5b0-104">文件夹路径</span><span class="sxs-lookup"><span data-stu-id="cc5b0-104">Folder paths</span></span>
<span data-ttu-id="cc5b0-105">本部分介绍了 Microsoft 中包含的 30 多个示例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]软件开发工具包 (SDK)。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-105">This section describes more than 30 samples included in the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Software Development Kit (SDK).</span></span> <span data-ttu-id="cc5b0-106">本部分提供了有关每个示例的详细信息，其中包括有关如何生成和运行示例的说明以及可以期望出现的结果。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-106">The section provides detailed information about each sample, including instructions for building the sample, how to run it, and what results to expect.</span></span>  

 <span data-ttu-id="cc5b0-107">示例文档使用路径的缩写形式\<*示例路径*\>来表示示例在您的安装路径。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-107">The samples documentation uses the path abbreviation \<*Samples Path*\> to denote the path to the samples in your installation.</span></span> <span data-ttu-id="cc5b0-108">默认路径会因安装时的相应设置而异。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-108">The default for the path can vary based on decisions made during installation.</span></span> <span data-ttu-id="cc5b0-109">下表提供了常见安装方案的默认路径。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-109">The following table provides the default path for common installation scenarios.</span></span>  


|            <span data-ttu-id="cc5b0-110">Description</span><span class="sxs-lookup"><span data-stu-id="cc5b0-110">Description</span></span>             |                                            <span data-ttu-id="cc5b0-111">路径</span><span class="sxs-lookup"><span data-stu-id="cc5b0-111">Path</span></span>                                            |
|------------------------------------|--------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cc5b0-112">在 32 位平台上安装</span><span class="sxs-lookup"><span data-stu-id="cc5b0-112">Installation on 32-bit platform</span></span>   |    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="cc5b0-113">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="cc5b0-113">\SDK\Samples</span></span>    |
| <span data-ttu-id="cc5b0-114">在 64 位平台上安装。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-114">Installation on a 64-bit platform.</span></span> | [!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)]<span data-ttu-id="cc5b0-115">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="cc5b0-115">\SDK\Samples</span></span> |

> [!IMPORTANT]
>  <span data-ttu-id="cc5b0-116">为了简便起见，此 SDK 中的示例和本文档假定您使用的是 BizTalk Server 的单个计算机开发人员版安装。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-116">For the sake of simplicity, the samples in this SDK, and this documentation, assume that you are using a single computer developer installation of BizTalk Server.</span></span> <span data-ttu-id="cc5b0-117">如果不执行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的完整安装，则某些示例可能无法正常使用。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-117">If you do not perform a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some samples may not work properly.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="cc5b0-118">所有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK 项都以英语提供，仅在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的英语版本安装中受支持。</span><span class="sxs-lookup"><span data-stu-id="cc5b0-118">All of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK items are provided in English and are supported only for English-language installations of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

## <a name="available-samples"></a><span data-ttu-id="cc5b0-119">可用的示例</span><span class="sxs-lookup"><span data-stu-id="cc5b0-119">Available samples</span></span> 

-   [<span data-ttu-id="cc5b0-120">适配器示例 - 开发</span><span class="sxs-lookup"><span data-stu-id="cc5b0-120">Adapter Samples - Development</span></span>](../core/adapter-samples-development.md)  

-   [<span data-ttu-id="cc5b0-121">适配器示例 - 用法</span><span class="sxs-lookup"><span data-stu-id="cc5b0-121">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)  

-   [<span data-ttu-id="cc5b0-122">Admin（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="cc5b0-122">Admin (BizTalk Server Samples Folder)</span></span>](../core/admin-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="cc5b0-123">应用程序部署（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="cc5b0-123">Application Deployment (BizTalk Server Samples Folder)</span></span>](../core/application-deployment-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="cc5b0-124">业务活动监视（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="cc5b0-124">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>](../core/business-activity-monitoring-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="cc5b0-125">业务规则（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="cc5b0-125">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="cc5b0-126">EDI 和 AS2（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="cc5b0-126">EDI and AS2 (BizTalk Server Samples Folder)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="cc5b0-127">消息传送（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="cc5b0-127">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="cc5b0-128">业务流程（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="cc5b0-128">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="cc5b0-129">管道（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="cc5b0-129">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="cc5b0-130">SSO（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="cc5b0-130">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="cc5b0-131">XML 工具（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="cc5b0-131">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)