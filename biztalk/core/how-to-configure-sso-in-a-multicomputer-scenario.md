---
title: 如何在多计算机方案中配置 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09bdaefef80a0a3e975c9d63e1844475ae698c4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386212"
---
# <a name="how-to-configure-sso-in-a-multicomputer-scenario"></a><span data-ttu-id="9dba7-102">如何在多计算机方案中配置 SSO</span><span class="sxs-lookup"><span data-stu-id="9dba7-102">How to Configure SSO in a Multicomputer Scenario</span></span>
<span data-ttu-id="9dba7-103">本部分包含有关在包含三台计算机方案中配置企业单一登录 (SSO) 的说明。</span><span class="sxs-lookup"><span data-stu-id="9dba7-103">This section contains instructions for configuring Enterprise Single Sign-On (SSO) in a three-computer scenario.</span></span>  
  
 <span data-ttu-id="9dba7-104">在以下方案中，计算机 A 是主密钥服务器，计算机 B 是单一登录服务器，计算机 C 存放 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="9dba7-104">In the following scenario, computer A is the master secret server, computer B is the Single Sign-On server, and computer C holds the SSO database.</span></span> <span data-ttu-id="9dba7-105">计算机 B 可充当运行时服务器，为管理服务器 （SSO 管理辅助服务使用此服务器用于管理 SSO 数据库），或映射服务器 （管理和数据的 SSO 客户端辅助服务使用此服务器来管理映射）。</span><span class="sxs-lookup"><span data-stu-id="9dba7-105">Computer B can act as a runtime server, as an administration server (administration sub services of SSO use this server for managing the SSO database), or as a mapping server (administration and client sub services of SSO use this server to manage mappings).</span></span>  
  
 <span data-ttu-id="9dba7-106">如果你想要将更多 SSO 服务器添加到你的环境，请按照配置计算机 B 的步骤任何新的 SSO 服务器将指向现有的 SSO 数据库，并且不能在主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="9dba7-106">If you want to add more SSO servers to your environment, follow the steps for configuring computer B. Any new SSO servers will point to the existing SSO database, and cannot be the master secret server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9dba7-107">建议你从单一登录服务器和 SSO 数据库的其他计算机上配置主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="9dba7-107">It is recommended that you configure the master secret server on a different computer from the Single Sign-On server and the SSO database.</span></span>  
  
### <a name="to-configure-the-master-secret-server-and-create-the-sso-database-on-computer-a"></a><span data-ttu-id="9dba7-108">若要配置主密钥服务器和计算机 A 上创建 SSO 数据库</span><span class="sxs-lookup"><span data-stu-id="9dba7-108">To configure the master secret server and create the SSO database on Computer A</span></span>  
  
1.  <span data-ttu-id="9dba7-109">执行自定义安装的 BizTalk Server 中，并只安装企业单一登录主密钥服务器组件。</span><span class="sxs-lookup"><span data-stu-id="9dba7-109">Perform a custom installation of BizTalk Server, and install only the Enterprise Single Sign-On Master Secret Server component.</span></span>  
  
2.  <span data-ttu-id="9dba7-110">运行配置向导来配置 SSO 主密钥服务器上。</span><span class="sxs-lookup"><span data-stu-id="9dba7-110">Run the Configuration Wizard to configure SSO on the master secret server.</span></span> <span data-ttu-id="9dba7-111">上**配置问题**页上，选择选项**创建新的 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="9dba7-111">On the **Configuration Questions** page, select the option to **Create a new SSO system**.</span></span>  
  
3.  <span data-ttu-id="9dba7-112">上**Windows 帐户**页上，指定用于 SSO 服务的服务帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="9dba7-112">On the **Windows Accounts** page, specify the service account credentials for the SSO service.</span></span> <span data-ttu-id="9dba7-113">这必须是 SSO Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="9dba7-113">This must be a member of the SSO Administrators group.</span></span>  
  
4.  <span data-ttu-id="9dba7-114">上**数据库配置**页上，指定 SQL Server （计算机 C） 的位置和 SSO 数据库 (SSODB) 的名称。</span><span class="sxs-lookup"><span data-stu-id="9dba7-114">On the **Database Configurations** page, specify the location of the SQL Server (computer C) and the name of the SSO database (SSODB).</span></span>  
  
5.  <span data-ttu-id="9dba7-115">指定要备份主密钥的选项。</span><span class="sxs-lookup"><span data-stu-id="9dba7-115">Specify the options to back up the Master Secret.</span></span>  
  
6.  <span data-ttu-id="9dba7-116">完成配置。</span><span class="sxs-lookup"><span data-stu-id="9dba7-116">Complete the configuration.</span></span>  
  
### <a name="to-configure-the-sso-server-on-computer-b"></a><span data-ttu-id="9dba7-117">若要在计算机 B 上配置的 SSO 服务器</span><span class="sxs-lookup"><span data-stu-id="9dba7-117">To configure the SSO server on Computer B</span></span>  
  
1.  <span data-ttu-id="9dba7-118">在计算机 b。 上安装企业单一登录</span><span class="sxs-lookup"><span data-stu-id="9dba7-118">Install Enterprise Single Sign-On on Computer B.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9dba7-119">这可以是在 BizTalk Server 或 Host Integration Server 计算机、 Web 服务器或仅 SSO 服务器 （SSO 运行时组件）。</span><span class="sxs-lookup"><span data-stu-id="9dba7-119">This can be a BizTalk Server or Host Integration Server computer, a Web server, or an SSO-only server (SSO runtime components).</span></span>  
  
2.  <span data-ttu-id="9dba7-120">运行配置向导以配置 SSO。</span><span class="sxs-lookup"><span data-stu-id="9dba7-120">Run the Configuration Wizard to configure SSO.</span></span> <span data-ttu-id="9dba7-121">上**配置问题**页上，选择选项**加入现有 SSO 系统**。</span><span class="sxs-lookup"><span data-stu-id="9dba7-121">On the **Configuration Questions** page, select the option to **Join an existing SSO system**.</span></span>  
  
3.  <span data-ttu-id="9dba7-122">上**Windows 帐户**页上，指定用于 SSO 服务的服务帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="9dba7-122">On the **Windows Accounts** page, specify the service account credentials for the SSO service.</span></span> <span data-ttu-id="9dba7-123">这必须是 SSO Administrators 组的成员。</span><span class="sxs-lookup"><span data-stu-id="9dba7-123">This must be a member of the SSO Administrators group.</span></span>  
  
4.  <span data-ttu-id="9dba7-124">上**数据库配置**页上，指向 SQL Server （计算机 C） 的位置和 SSO 数据库 (SSODB) 的名称。</span><span class="sxs-lookup"><span data-stu-id="9dba7-124">On the **Database Configurations** page, point to the location of the SQL Server (computer C) and the name of the SSO database (SSODB).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dba7-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="9dba7-125">See Also</span></span>  
 <span data-ttu-id="9dba7-126">[如何群集主密钥服务器](../core/how-to-cluster-the-master-secret-server1.md) </span><span class="sxs-lookup"><span data-stu-id="9dba7-126">[How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md) </span></span>  
 [<span data-ttu-id="9dba7-127">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="9dba7-127">Installing SSO</span></span>](../core/installing-sso.md)