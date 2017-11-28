---
title: "如何在多计算机方案中配置 SSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, SSO
- SSO database, clustering
- clustering, Master Secret server
- SSO, configuring
- configuring, Master Secret server
- Master Secret server, clustering
- clustering, SSO database
- Master Secret server, configuring
- SSO, multiple computers
ms.assetid: 4511a03d-96f2-45f0-9891-e8b3e253499c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45bfa58c1fc11a76109f56938b8e1b43790935f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-sso-in-a-multicomputer-scenario"></a><span data-ttu-id="0fcc7-102">如何在多计算机方案中配置 SSO</span><span class="sxs-lookup"><span data-stu-id="0fcc7-102">How to Configure SSO in a Multicomputer Scenario</span></span>
<span data-ttu-id="0fcc7-103">本部分提供了在使用三台计算机的情况下配置企业单一登录 (SSO) 的说明。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-103">This section contains instructions for configuring Enterprise Single Sign-On (SSO) in a three-computer scenario.</span></span>  
  
 <span data-ttu-id="0fcc7-104">在下面的方案中，计算机 A 是主密钥服务器，计算机 B 是单一登录服务器，计算机 C 存放 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-104">In the following scenario, computer A is the master secret server, computer B is the Single Sign-On server, and computer C holds the SSO database.</span></span> <span data-ttu-id="0fcc7-105">计算机 B 可充当运行时服务器、管理服务器（SSO 的管理辅助服务使用此服务器来管理 SSO 数据库）或映射服务器（SSO 的管理和客户端辅助服务使用此服务器来管理映射）。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-105">Computer B can act as a runtime server, as an administration server (administration sub services of SSO use this server for managing the SSO database), or as a mapping server (administration and client sub services of SSO use this server to manage mappings).</span></span>  
  
 <span data-ttu-id="0fcc7-106">如果要向环境中添加更多 SSO 服务器，则按照配置计算机 B 的步骤进行操作。所有新的 SSO 服务器都将指向现有的 SSO 数据库，并且不能用作主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-106">If you want to add more SSO servers to your environment, follow the steps for configuring computer B. Any new SSO servers will point to the existing SSO database, and cannot be the master secret server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fcc7-107">建议您在单一登录服务器和 SSO 数据库所在的计算机以外的其他计算机上配置主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-107">It is recommended that you configure the master secret server on a different computer from the Single Sign-On server and the SSO database.</span></span>  
  
### <a name="to-configure-the-master-secret-server-and-create-the-sso-database-on-computer-a"></a><span data-ttu-id="0fcc7-108">在计算机 A 上配置主密钥服务器并创建 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-108">To configure the master secret server and create the SSO database on Computer A</span></span>  
  
1.  <span data-ttu-id="0fcc7-109">执行 BizTalk Server 的自定义安装，并且仅安装企业单一登录主密钥服务器组件。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-109">Perform a custom installation of BizTalk Server, and install only the Enterprise Single Sign-On Master Secret Server component.</span></span>  
  
2.  <span data-ttu-id="0fcc7-110">运行配置向导以在主密钥服务器上配置 SSO。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-110">Run the Configuration Wizard to configure SSO on the master secret server.</span></span> <span data-ttu-id="0fcc7-111">上**配置问题**页上，选择该选项以**创建新的 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-111">On the **Configuration Questions** page, select the option to **Create a new SSO system**.</span></span>  
  
3.  <span data-ttu-id="0fcc7-112">上**Windows 帐户**页上，指定 SSO 服务的服务帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-112">On the **Windows Accounts** page, specify the service account credentials for the SSO service.</span></span> <span data-ttu-id="0fcc7-113">此帐户必须为 SSO Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-113">This must be a member of the SSO Administrators group.</span></span>  
  
4.  <span data-ttu-id="0fcc7-114">上**数据库配置**页上，指定 SQL Server （计算机 C） 的位置和 SSO 数据库 (SSODB) 的名称。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-114">On the **Database Configurations** page, specify the location of the SQL Server (computer C) and the name of the SSO database (SSODB).</span></span>  
  
5.  <span data-ttu-id="0fcc7-115">指定用于备份主密钥的选项。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-115">Specify the options to back up the Master Secret.</span></span>  
  
6.  <span data-ttu-id="0fcc7-116">完成配置。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-116">Complete the configuration.</span></span>  
  
### <a name="to-configure-the-sso-server-on-computer-b"></a><span data-ttu-id="0fcc7-117">在计算机 B 上配置 SSO 服务器</span><span class="sxs-lookup"><span data-stu-id="0fcc7-117">To configure the SSO server on Computer B</span></span>  
  
1.  <span data-ttu-id="0fcc7-118">在计算机 B 上安装企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-118">Install Enterprise Single Sign-On on Computer B.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0fcc7-119">此计算机可以是 BizTalk Server 计算机、Host Integration Server 计算机或 Web 服务器，也可以仅是 SSO 服务器（SSO 运行时组件）。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-119">This can be a BizTalk Server or Host Integration Server computer, a Web server, or an SSO-only server (SSO runtime components).</span></span>  
  
2.  <span data-ttu-id="0fcc7-120">运行配置向导以配置 SSO。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-120">Run the Configuration Wizard to configure SSO.</span></span> <span data-ttu-id="0fcc7-121">上**配置问题**页上，选择该选项以**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-121">On the **Configuration Questions** page, select the option to **Join an existing SSO system**.</span></span>  
  
3.  <span data-ttu-id="0fcc7-122">上**Windows 帐户**页上，指定 SSO 服务的服务帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-122">On the **Windows Accounts** page, specify the service account credentials for the SSO service.</span></span> <span data-ttu-id="0fcc7-123">此帐户必须为 SSO Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-123">This must be a member of the SSO Administrators group.</span></span>  
  
4.  <span data-ttu-id="0fcc7-124">上**数据库配置**页上，指向 SQL Server （计算机 C） 的位置和 SSO 数据库 (SSODB) 的名称。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-124">On the **Database Configurations** page, point to the location of the SQL Server (computer C) and the name of the SSO database (SSODB).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fcc7-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0fcc7-125">See Also</span></span>  
 <span data-ttu-id="0fcc7-126">[如何安装群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md) </span><span class="sxs-lookup"><span data-stu-id="0fcc7-126">[How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md) </span></span>  
 [<span data-ttu-id="0fcc7-127">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="0fcc7-127">Installing SSO</span></span>](../core/installing-sso.md)