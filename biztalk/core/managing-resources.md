---
title: 管理资源 |Microsoft Docs
description: 使用 btstask 或 BizTalk 管理适用于程序集、 脚本、 证书、 绑定文件和 BizTalk Server 中的更多
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b478ef2e-1363-4c2c-a4b7-6a582a6b33a5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a26a0afc6832dfa4c8401442dc000262dab3aec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380219"
---
# <a name="manage-resources"></a><span data-ttu-id="d356c-103">管理资源</span><span class="sxs-lookup"><span data-stu-id="d356c-103">Manage Resources</span></span>

## <a name="overview"></a><span data-ttu-id="d356c-104">概述</span><span class="sxs-lookup"><span data-stu-id="d356c-104">Overview</span></span>
<span data-ttu-id="d356c-105">在本部分中的主题提供有关如何使用 BizTalk Server 管理控制台或 BTSTask 命令行工具来管理 BizTalk Server 资源部署到 BizTalk 组后的说明。</span><span class="sxs-lookup"><span data-stu-id="d356c-105">The topics in this section provide instructions on how to use the BizTalk Server Administration console or the BTSTask command-line tool to manage BizTalk Server resources after they have been deployed into a BizTalk group.</span></span> <span data-ttu-id="d356c-106">资源包括以下类型的项目：</span><span class="sxs-lookup"><span data-stu-id="d356c-106">Resources include the following types of artifacts:</span></span>  
  
-   <span data-ttu-id="d356c-107">BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="d356c-107">BizTalk Assemblies</span></span>  
  
-   <span data-ttu-id="d356c-108">预处理和后处理脚本</span><span class="sxs-lookup"><span data-stu-id="d356c-108">Pre- and post-processing scripts</span></span>  
  
-   <span data-ttu-id="d356c-109">.NET 程序集</span><span class="sxs-lookup"><span data-stu-id="d356c-109">.NET assemblies</span></span>  
  
-   <span data-ttu-id="d356c-110">COM 组件</span><span class="sxs-lookup"><span data-stu-id="d356c-110">COM components</span></span>  
  
-   <span data-ttu-id="d356c-111">证书</span><span class="sxs-lookup"><span data-stu-id="d356c-111">Certificates</span></span>  
  
-   <span data-ttu-id="d356c-112">特别文件</span><span class="sxs-lookup"><span data-stu-id="d356c-112">Ad hoc files</span></span>  
  
-   <span data-ttu-id="d356c-113">BAM 定义</span><span class="sxs-lookup"><span data-stu-id="d356c-113">BAM definitions</span></span>  
  
-   <span data-ttu-id="d356c-114">绑定文件</span><span class="sxs-lookup"><span data-stu-id="d356c-114">Binding files</span></span>  
  
-   <span data-ttu-id="d356c-115">虚拟目录</span><span class="sxs-lookup"><span data-stu-id="d356c-115">Virtual directories</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d356c-116">Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。</span><span class="sxs-lookup"><span data-stu-id="d356c-116">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="d356c-117">有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="d356c-117">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
> 
> [!NOTE]
>  <span data-ttu-id="d356c-118">不要将具有相同的名称，不区分大小写，多个资源添加到 BizTalk Server 组。</span><span class="sxs-lookup"><span data-stu-id="d356c-118">Do not add multiple resources with the same name, regardless of case, to a BizTalk Server group.</span></span> <span data-ttu-id="d356c-119">不支持将多个具有相同名称的资源添加到 BizTalk Server 组，即使 BizTalk Server 管理数据库存储配置为使用二进制排序规则并区分大小写的 SQL 服务器上。</span><span class="sxs-lookup"><span data-stu-id="d356c-119">Adding multiple resources with the same name to a BizTalk Server group is not supported, even when the BizTalk Server management database is housed on a SQL Server that is configured to use binary collation and supports case sensitivity.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d356c-120">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d356c-120">Next steps</span></span>
  
-   [<span data-ttu-id="d356c-121">管理 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="d356c-121">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)  
  
-   [<span data-ttu-id="d356c-122">管理预处理脚本和后期处理脚本</span><span class="sxs-lookup"><span data-stu-id="d356c-122">Managing Pre- and Post-processing Scripts</span></span>](../core/managing-pre-and-post-processing-scripts.md)  
  
-   [<span data-ttu-id="d356c-123">管理 .NET 程序集、证书和其他资源</span><span class="sxs-lookup"><span data-stu-id="d356c-123">Managing .NET Assemblies, Certificates, and Other Resources</span></span>](../core/managing-net-assemblies-certificates-and-other-resources.md)  
  
-   [<span data-ttu-id="d356c-124">刷新资源</span><span class="sxs-lookup"><span data-stu-id="d356c-124">Refresh a Resource</span></span>](../core/how-to-refresh-a-resource.md)