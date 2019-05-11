---
title: 如何创建服务帐户为新主机和主机实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Configuration Manager, service accounts
- Windows groups, service accounts
- Configuration Manager
- service accounts, Windows groups
- hosts, service accounts
- service accounts, hosts
- service accounts, Configuration Manager
- service accounts, creating
- creating, service accounts
ms.assetid: cef97f4a-8db1-41b6-9614-608c2fbf59a9
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 983cbb2b21b2a9027830f9bad326798b84c0f2bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385405"
---
# <a name="how-to-create-service-accounts-for-new-hosts-and-host-instances"></a><span data-ttu-id="54e75-102">如何创建服务帐户为新主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="54e75-102">How to Create Service Accounts for New Hosts and Host Instances</span></span>
<span data-ttu-id="54e75-103">安装和配置 BizTalk Server 的单台计算机上时，Configuration Manager 会配置必要的 Windows 组和用户帐户。</span><span class="sxs-lookup"><span data-stu-id="54e75-103">The Configuration Manager configures the necessary Windows groups and user accounts when you install and configure BizTalk Server on a single computer.</span></span>  
  
 <span data-ttu-id="54e75-104">必须手动创建 Windows 组和用户帐户，并在运行 Configuration Manager 之前的用户帐户添加到域环境中的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="54e75-104">You must manually create Windows groups and user accounts, and add the user accounts to the Windows groups in a domain environment before running the Configuration Manager.</span></span> <span data-ttu-id="54e75-105">有关详细信息，请参阅[域组](../core/domain-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="54e75-105">For more information, see [Domain Groups](../core/domain-groups.md).</span></span>  
  
 <span data-ttu-id="54e75-106">创建新的主机或主机实例前，必须执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="54e75-106">You must perform the following procedure before creating a new host or host instance.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="54e75-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="54e75-107">Prerequisites</span></span>  
 <span data-ttu-id="54e75-108">您必须为要执行此过程的 Administrators 或 Domain Admins 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="54e75-108">You must be logged on as a member of Administrators or Domain Admins group to perform this procedure.</span></span>  
  
### <a name="to-create-service-accounts-for-new-hosts-or-host-instances"></a><span data-ttu-id="54e75-109">若要创建新主机或主机实例服务帐户</span><span class="sxs-lookup"><span data-stu-id="54e75-109">To create service accounts for new hosts or host instances</span></span>  
  
1.  <span data-ttu-id="54e75-110">您将创建的新主机创建主机 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="54e75-110">Create a host Windows group for the new host that you will create.</span></span> <span data-ttu-id="54e75-111">有关创建新的主机的详细信息，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)。</span><span class="sxs-lookup"><span data-stu-id="54e75-111">For more information about creating a new host, see [How to Create a New Host](../core/how-to-create-a-new-host.md).</span></span>  
  
2.  <span data-ttu-id="54e75-112">创建将添加到新主机的每个主机实例的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="54e75-112">Create service accounts for each host instance that will be added to the new host.</span></span> <span data-ttu-id="54e75-113">有关创建新的主机实例的详细信息，请参阅[如何将主机实例添加](../core/how-to-add-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="54e75-113">For more information about creating a new host instance, see [How to Add a Host Instance](../core/how-to-add-a-host-instance.md).</span></span>  
  
3.  <span data-ttu-id="54e75-114">将服务帐户添加到主机 Windows 组中，根据需要。</span><span class="sxs-lookup"><span data-stu-id="54e75-114">Add the service accounts to the host Windows group as needed.</span></span> <span data-ttu-id="54e75-115">有关必须向其添加服务帐户的 Windows 组的信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="54e75-115">For information about the Windows groups to which you must add the service account, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
4.  <span data-ttu-id="54e75-116">使用 Windows 组和服务帐户时创建的主机和主机实例。</span><span class="sxs-lookup"><span data-stu-id="54e75-116">Use the Windows group and service account when creating the host and host instances.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54e75-117">未指定\<*计算机名*\>\ 作为具有本地组的单个计算机设置中的前缀。</span><span class="sxs-lookup"><span data-stu-id="54e75-117">Do not specify \<*computer name*\>\ as the prefix in a single computer setup with local groups.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54e75-118">如果使用域组，必须指定\<*域 NetBIOS 名称*\>\ 作为主机 Windows 组名的前缀。</span><span class="sxs-lookup"><span data-stu-id="54e75-118">If you are using a Domain group, you must specify \<*Domain NetBIOS Name*\>\ as the prefix for the host Windows Group name.</span></span> <span data-ttu-id="54e75-119">例如 CONTOSO\btssvc。</span><span class="sxs-lookup"><span data-stu-id="54e75-119">For example, CONTOSO\btssvc.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e75-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="54e75-120">See Also</span></span>  
 <span data-ttu-id="54e75-121">[管理主机和服务帐户](../core/managing-hosts-and-service-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="54e75-121">[Managing Hosts and Service Accounts](../core/managing-hosts-and-service-accounts.md) </span></span>  
 <span data-ttu-id="54e75-122">[管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="54e75-122">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 <span data-ttu-id="54e75-123">[如何管理 BizTalk Server Administrators 组](../core/how-to-manage-the-biztalk-server-administrators-group.md) </span><span class="sxs-lookup"><span data-stu-id="54e75-123">[How to Manage the BizTalk Server Administrators Group](../core/how-to-manage-the-biztalk-server-administrators-group.md) </span></span>  
 [<span data-ttu-id="54e75-124">管理 Windows 组和用户帐户的最佳做法</span><span class="sxs-lookup"><span data-stu-id="54e75-124">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)