---
title: "运行方式配置文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98ac0a0c-91d8-4d12-aa40-2ad2e29ec784
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69fa6c9401f606619b2fb8d22d95ded48c18a092
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-as-profiles"></a><span data-ttu-id="e7e38-102">运行方式配置文件</span><span class="sxs-lookup"><span data-stu-id="e7e38-102">Run As Profiles</span></span>
<span data-ttu-id="e7e38-103">首次导入 BizTalk Server 核心库管理包，将创建两个新运行方式配置文件：</span><span class="sxs-lookup"><span data-stu-id="e7e38-103">When the BizTalk Server Core Library Management Pack is first imported, it creates two new Run As Profiles:</span></span>  
  
-   <span data-ttu-id="e7e38-104">**BizTalk Server 发现帐户**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-104">**BizTalk Server Discovery Account**.</span></span> <span data-ttu-id="e7e38-105">此配置文件是与 BizTalk Server 角色组件的所有发现相关联。</span><span class="sxs-lookup"><span data-stu-id="e7e38-105">This profile is associated with all discoveries of BizTalk Server role components.</span></span>  
  
-   <span data-ttu-id="e7e38-106">**BizTalk Server 监视帐户**。</span><span class="sxs-lookup"><span data-stu-id="e7e38-106">**BizTalk Server Monitoring Account**.</span></span> <span data-ttu-id="e7e38-107">此配置文件与所有监视器和任务相关联。</span><span class="sxs-lookup"><span data-stu-id="e7e38-107">This profile is associated with all monitors and tasks.</span></span>  
  
 <span data-ttu-id="e7e38-108">默认情况下，所有发现、 监视器和任务在 BizTalk Server 管理包默认为使用"默认操作帐户"运行方式配置文件中定义的帐户中定义。</span><span class="sxs-lookup"><span data-stu-id="e7e38-108">By default, all discoveries, monitors, and tasks defined in the BizTalk Server Management Packs default to using the accounts defined in the “Default Action Account” Run As Profile.</span></span>  <span data-ttu-id="e7e38-109">如果给定系统的默认操作帐户没有发现或监视 BizTalk 的必要权限，然后这些系统可绑定到 BizTalk Server 运行方式配置文件，它们有权访问 BizTalk Server 中更具体的凭据。</span><span class="sxs-lookup"><span data-stu-id="e7e38-109">If the default action account for a given system does not have the necessary permissions to discover or monitor BizTalk, then those systems can be bound to more specific credentials in the BizTalk Server Run As Profiles, which do have access to BizTalk Server.</span></span>  
  
 <span data-ttu-id="e7e38-110">若要为 BizTalk Server 中配置运行方式配置文件的一般步骤如下：</span><span class="sxs-lookup"><span data-stu-id="e7e38-110">The following are the generic steps to configure Run As Profiles for BizTalk Server:</span></span>  
  
### <a name="to-configure-run-as-profiles"></a><span data-ttu-id="e7e38-111">若要配置运行方式配置文件</span><span class="sxs-lookup"><span data-stu-id="e7e38-111">To configure Run As profiles</span></span>  
  
1.  <span data-ttu-id="e7e38-112">标识默认操作帐户其中具有权限不足以监视 BizTalk Server 的目标计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="e7e38-112">Identify the name(s) of the target computer(s) where the default action account has insufficient rights to monitor BizTalk Server.</span></span>  
  
2.  <span data-ttu-id="e7e38-113">对于每个系统创建或使用一组现有凭据至少具有中论述的 BizTalk Server 特权[低特权环境](../technical-guides/low-privilege-environments.md)本管理包指南的一部分。</span><span class="sxs-lookup"><span data-stu-id="e7e38-113">For each system create or use an existing set of credentials that have at least the BizTalk Server privileges discussed in the [Low-Privilege Environments](../technical-guides/low-privilege-environments.md) section of this management pack guide.</span></span>  
  
3.  <span data-ttu-id="e7e38-114">对于在步骤 2 中标识的凭据的每组，请确保管理组中存在相应运行方式帐户。</span><span class="sxs-lookup"><span data-stu-id="e7e38-114">For each set of credentials identified in step 2, make sure that a corresponding Run As Account exists in the management group.</span></span> <span data-ttu-id="e7e38-115">如有必要，请创建运行方式帐户。</span><span class="sxs-lookup"><span data-stu-id="e7e38-115">Create the Run As Account if it is necessary.</span></span>  
  
4.  <span data-ttu-id="e7e38-116">在上设置的目标和运行方式帐户之间的映射**运行方式帐户**的每个运行方式配置文件的选项卡。</span><span class="sxs-lookup"><span data-stu-id="e7e38-116">Set up the mappings between the targets and the Run As Account(s) on the **Run As Accounts** tab of each of the Run As Profiles.</span></span>