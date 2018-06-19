---
title: 如何创建服务帐户的新主机和主机实例 |Microsoft 文档
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
ms.openlocfilehash: 5d4887d78466340b12b95ed43d27523955ab0689
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969372"
---
# <a name="how-to-create-service-accounts-for-new-hosts-and-host-instances"></a><span data-ttu-id="706ce-102">如何为新主机和主机实例创建服务帐户</span><span class="sxs-lookup"><span data-stu-id="706ce-102">How to Create Service Accounts for New Hosts and Host Instances</span></span>
<span data-ttu-id="706ce-103">在单台计算机上安装和配置 BizTalk Server 时，配置管理器将配置必需的 Windows 组和用户帐户。</span><span class="sxs-lookup"><span data-stu-id="706ce-103">The Configuration Manager configures the necessary Windows groups and user accounts when you install and configure BizTalk Server on a single computer.</span></span>  
  
 <span data-ttu-id="706ce-104">必须手动创建 Windows 组和用户帐户，并将用户帐户添加到域环境中的 Windows 组，然后才能运行配置管理器。</span><span class="sxs-lookup"><span data-stu-id="706ce-104">You must manually create Windows groups and user accounts, and add the user accounts to the Windows groups in a domain environment before running the Configuration Manager.</span></span> <span data-ttu-id="706ce-105">有关详细信息，请参阅[域组](../core/domain-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="706ce-105">For more information, see [Domain Groups](../core/domain-groups.md).</span></span>  
  
 <span data-ttu-id="706ce-106">在创建新主机或主机实例前，必须先执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="706ce-106">You must perform the following procedure before creating a new host or host instance.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="706ce-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="706ce-107">Prerequisites</span></span>  
 <span data-ttu-id="706ce-108">必须以 Administrators 组或域 Admins 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="706ce-108">You must be logged on as a member of Administrators or Domain Admins group to perform this procedure.</span></span>  
  
### <a name="to-create-service-accounts-for-new-hosts-or-host-instances"></a><span data-ttu-id="706ce-109">为新主机或主机实例创建服务帐户</span><span class="sxs-lookup"><span data-stu-id="706ce-109">To create service accounts for new hosts or host instances</span></span>  
  
1.  <span data-ttu-id="706ce-110">为您将要创建的新主机创建主机 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="706ce-110">Create a host Windows group for the new host that you will create.</span></span> <span data-ttu-id="706ce-111">有关创建新的主机的详细信息，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)。</span><span class="sxs-lookup"><span data-stu-id="706ce-111">For more information about creating a new host, see [How to Create a New Host](../core/how-to-create-a-new-host.md).</span></span>  
  
2.  <span data-ttu-id="706ce-112">为将要添加到新主机中的每个主机实例创建服务帐户。</span><span class="sxs-lookup"><span data-stu-id="706ce-112">Create service accounts for each host instance that will be added to the new host.</span></span> <span data-ttu-id="706ce-113">有关创建新的主机实例的详细信息，请参阅[如何添加一个主机实例](../core/how-to-add-a-host-instance.md)。</span><span class="sxs-lookup"><span data-stu-id="706ce-113">For more information about creating a new host instance, see [How to Add a Host Instance](../core/how-to-add-a-host-instance.md).</span></span>  
  
3.  <span data-ttu-id="706ce-114">可根据需要向该主机的 Windows 组中添加服务帐户。</span><span class="sxs-lookup"><span data-stu-id="706ce-114">Add the service accounts to the host Windows group as needed.</span></span> <span data-ttu-id="706ce-115">您必须将服务帐户添加到其中的 Windows 组有关的信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="706ce-115">For information about the Windows groups to which you must add the service account, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
4.  <span data-ttu-id="706ce-116">在创建主机和主机实例时，可使用 Windows 组和服务帐户。</span><span class="sxs-lookup"><span data-stu-id="706ce-116">Use the Windows group and service account when creating the host and host instances.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="706ce-117">未指定\<*计算机名称*\>\ 作为单个计算机的设置与本地组中的前缀。</span><span class="sxs-lookup"><span data-stu-id="706ce-117">Do not specify \<*computer name*\>\ as the prefix in a single computer setup with local groups.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="706ce-118">如果你正在使用域组，你必须指定\<*域 NetBIOS 名称*\>\ 作为主机 Windows 组名的前缀。</span><span class="sxs-lookup"><span data-stu-id="706ce-118">If you are using a Domain group, you must specify \<*Domain NetBIOS Name*\>\ as the prefix for the host Windows Group name.</span></span> <span data-ttu-id="706ce-119">例如 CONTOSO\btssvc。</span><span class="sxs-lookup"><span data-stu-id="706ce-119">For example, CONTOSO\btssvc.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="706ce-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="706ce-120">See Also</span></span>  
 <span data-ttu-id="706ce-121">[管理主机和服务帐户](../core/managing-hosts-and-service-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="706ce-121">[Managing Hosts and Service Accounts](../core/managing-hosts-and-service-accounts.md) </span></span>  
 <span data-ttu-id="706ce-122">[管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="706ce-122">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 <span data-ttu-id="706ce-123">[如何管理 BizTalk Server Administrators 组](../core/how-to-manage-the-biztalk-server-administrators-group.md) </span><span class="sxs-lookup"><span data-stu-id="706ce-123">[How to Manage the BizTalk Server Administrators Group](../core/how-to-manage-the-biztalk-server-administrators-group.md) </span></span>  
 [<span data-ttu-id="706ce-124">管理 Windows 组和用户帐户的最佳做法</span><span class="sxs-lookup"><span data-stu-id="706ce-124">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)