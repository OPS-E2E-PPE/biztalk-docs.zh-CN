---
title: SSO 部署概述 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, deploying example
- SSO, deploying
- deploying, SSO
- SSO, multiple computers
- examples, deploying
ms.assetid: 6eccee26-c392-41fe-97fb-3afe1685540f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c98a12c11ae735945f4e69631e7211c05c0b9186
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022363"
---
# <a name="sso-deployment-overview"></a><span data-ttu-id="aefa9-102">SSO 部署概述</span><span class="sxs-lookup"><span data-stu-id="aefa9-102">SSO Deployment Overview</span></span>
<span data-ttu-id="aefa9-103">本示例中的系统部署在三个域中，包含以下计算机：</span><span class="sxs-lookup"><span data-stu-id="aefa9-103">The system in this example is deployed over three domains, containing the following computers:</span></span>  
  
 <span data-ttu-id="aefa9-104">**域 ORCH.com**</span><span class="sxs-lookup"><span data-stu-id="aefa9-104">**Domain ORCH.com**</span></span>  
  
- <span data-ttu-id="aefa9-105">ORCH 域控制器</span><span class="sxs-lookup"><span data-stu-id="aefa9-105">ORCH domain controller</span></span>  
  
- <span data-ttu-id="aefa9-106">HIS1，HISSO 服务器</span><span class="sxs-lookup"><span data-stu-id="aefa9-106">HIS1, the HISSO server</span></span>  
  
- <span data-ttu-id="aefa9-107">HIS2，主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="aefa9-107">HIS2, the Master Secret Server</span></span>  
  
- <span data-ttu-id="aefa9-108">HIS3，管理数据库</span><span class="sxs-lookup"><span data-stu-id="aefa9-108">HIS3, the Admin database</span></span>  
  
  <span data-ttu-id="aefa9-109">**域 SQL.com**</span><span class="sxs-lookup"><span data-stu-id="aefa9-109">**Domain SQL.com**</span></span>  
  
- <span data-ttu-id="aefa9-110">SQL 域控制器</span><span class="sxs-lookup"><span data-stu-id="aefa9-110">SQL domain controller</span></span>  
  
- <span data-ttu-id="aefa9-111">SQL2，SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="aefa9-111">SQL2, the SSO database</span></span>  
  
  <span data-ttu-id="aefa9-112">**域 HIS.com**</span><span class="sxs-lookup"><span data-stu-id="aefa9-112">**Domain HIS.com**</span></span>  
  
- <span data-ttu-id="aefa9-113">HIS 域控制器</span><span class="sxs-lookup"><span data-stu-id="aefa9-113">HIS domain controller</span></span>  
  
- <span data-ttu-id="aefa9-114">HIS4 数据库</span><span class="sxs-lookup"><span data-stu-id="aefa9-114">HIS4 database</span></span>  
  
  <span data-ttu-id="aefa9-115">定义此部署的要点如下：</span><span class="sxs-lookup"><span data-stu-id="aefa9-115">The key points defining this deployment are as follows:</span></span>  
  
- <span data-ttu-id="aefa9-116">域 ORCH.com 和域 SQL.com 具有双向选择信任关系。</span><span class="sxs-lookup"><span data-stu-id="aefa9-116">Domain ORCH.com and domain SQL.com have a two-way selective trust relationship.</span></span>  
  
- <span data-ttu-id="aefa9-117">域 ORCH.com 配置为本机 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 功能级别。</span><span class="sxs-lookup"><span data-stu-id="aefa9-117">Domain ORCH.com is configured as native [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] functional level.</span></span>  
  
- <span data-ttu-id="aefa9-118">所有 SSO 服务都以 ORCH.com 域用户帐户 (Orch\SSOSvcUser) 运行。</span><span class="sxs-lookup"><span data-stu-id="aefa9-118">All SSO services are running on an ORCH.com domain user account (Orch\SSOSvcUser).</span></span> <span data-ttu-id="aefa9-119">该用户被配置为具有对 SQL.com 域中的 SQL2 计算机的访问权限。</span><span class="sxs-lookup"><span data-stu-id="aefa9-119">The user is configured to have access permission on the SQL2 machine in the SQL.com domain.</span></span> <span data-ttu-id="aefa9-120">为该用户配置在 ORCH.com 域中的协议转换和约束委托。</span><span class="sxs-lookup"><span data-stu-id="aefa9-120">The user is configured for protocol transition and constrain delegation within the ORCH.com domain.</span></span>  
  
- <span data-ttu-id="aefa9-121">设置另外一个 ORCH.com 域用户 (Orch\TestAppUser) 来运行测试程序。</span><span class="sxs-lookup"><span data-stu-id="aefa9-121">Another ORCH.com domain user (Orch\TestAppUser) is set for running test programs.</span></span> <span data-ttu-id="aefa9-122">并为该用户配置协议转换和约束委托。</span><span class="sxs-lookup"><span data-stu-id="aefa9-122">This user is also configured for protocol transition and constrain delegation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aefa9-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="aefa9-123">See Also</span></span>  
 [<span data-ttu-id="aefa9-124">部署过程</span><span class="sxs-lookup"><span data-stu-id="aefa9-124">Deployment Process</span></span>](../core/deployment-process.md)