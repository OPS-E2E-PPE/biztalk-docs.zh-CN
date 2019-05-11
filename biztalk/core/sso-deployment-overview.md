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
ms.openlocfilehash: c942bf7f7fd0853164e2cf2b8fdadbfced2fe33d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401754"
---
# <a name="sso-deployment-overview"></a><span data-ttu-id="571b7-102">SSO 部署概述</span><span class="sxs-lookup"><span data-stu-id="571b7-102">SSO Deployment Overview</span></span>
<span data-ttu-id="571b7-103">在此示例中的系统部署在三个域，其中包含以下计算机：</span><span class="sxs-lookup"><span data-stu-id="571b7-103">The system in this example is deployed over three domains, containing the following computers:</span></span>  
  
 <span data-ttu-id="571b7-104">**域 ORCH.com**</span><span class="sxs-lookup"><span data-stu-id="571b7-104">**Domain ORCH.com**</span></span>  
  
- <span data-ttu-id="571b7-105">ORCH 域控制器</span><span class="sxs-lookup"><span data-stu-id="571b7-105">ORCH domain controller</span></span>  
  
- <span data-ttu-id="571b7-106">HIS1，HISSO 服务器</span><span class="sxs-lookup"><span data-stu-id="571b7-106">HIS1, the HISSO server</span></span>  
  
- <span data-ttu-id="571b7-107">HIS2，主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="571b7-107">HIS2, the Master Secret Server</span></span>  
  
- <span data-ttu-id="571b7-108">在 HIS3，管理数据库</span><span class="sxs-lookup"><span data-stu-id="571b7-108">HIS3, the Admin database</span></span>  
  
  <span data-ttu-id="571b7-109">**Domain SQL.com**</span><span class="sxs-lookup"><span data-stu-id="571b7-109">**Domain SQL.com**</span></span>  
  
- <span data-ttu-id="571b7-110">SQL 域控制器</span><span class="sxs-lookup"><span data-stu-id="571b7-110">SQL domain controller</span></span>  
  
- <span data-ttu-id="571b7-111">SQL2，SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="571b7-111">SQL2, the SSO database</span></span>  
  
  <span data-ttu-id="571b7-112">**域 HIS.com**</span><span class="sxs-lookup"><span data-stu-id="571b7-112">**Domain HIS.com**</span></span>  
  
- <span data-ttu-id="571b7-113">他的域控制器</span><span class="sxs-lookup"><span data-stu-id="571b7-113">HIS domain controller</span></span>  
  
- <span data-ttu-id="571b7-114">HIS4 数据库</span><span class="sxs-lookup"><span data-stu-id="571b7-114">HIS4 database</span></span>  
  
  <span data-ttu-id="571b7-115">定义此部署的关键点是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="571b7-115">The key points defining this deployment are as follows:</span></span>  
  
- <span data-ttu-id="571b7-116">域 ORCH.com 和域 SQL.com 具有双向选择信任关系。</span><span class="sxs-lookup"><span data-stu-id="571b7-116">Domain ORCH.com and domain SQL.com have a two-way selective trust relationship.</span></span>  
  
- <span data-ttu-id="571b7-117">域 ORCH.com 配置为本机[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]功能级别。</span><span class="sxs-lookup"><span data-stu-id="571b7-117">Domain ORCH.com is configured as native [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] functional level.</span></span>  
  
- <span data-ttu-id="571b7-118">所有 SSO 服务在 ORCH.com 域用户帐户 (Orch\SSOSvcUser) 都运行。</span><span class="sxs-lookup"><span data-stu-id="571b7-118">All SSO services are running on an ORCH.com domain user account (Orch\SSOSvcUser).</span></span> <span data-ttu-id="571b7-119">用户配置为在 SQL.com 域的 SQL2 计算机上具有访问权限。</span><span class="sxs-lookup"><span data-stu-id="571b7-119">The user is configured to have access permission on the SQL2 machine in the SQL.com domain.</span></span> <span data-ttu-id="571b7-120">用户配置的协议转换和约束委派在 ORCH.com 域中。</span><span class="sxs-lookup"><span data-stu-id="571b7-120">The user is configured for protocol transition and constrain delegation within the ORCH.com domain.</span></span>  
  
- <span data-ttu-id="571b7-121">另一个 ORCH.com 域用户 (Orch\TestAppUser) 来运行测试程序设置。</span><span class="sxs-lookup"><span data-stu-id="571b7-121">Another ORCH.com domain user (Orch\TestAppUser) is set for running test programs.</span></span> <span data-ttu-id="571b7-122">此用户也被配置为协议转换和约束委派。</span><span class="sxs-lookup"><span data-stu-id="571b7-122">This user is also configured for protocol transition and constrain delegation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="571b7-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="571b7-123">See Also</span></span>  
 [<span data-ttu-id="571b7-124">部署过程</span><span class="sxs-lookup"><span data-stu-id="571b7-124">Deployment Process</span></span>](../core/deployment-process.md)