---
title: "管理主机和服务帐户 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, managing
- managing [user accounts]
- service accounts, security
- managing [hosts], security
- security, hosts
- managing [Windows groups]
- hosts, security
- security, service accounts
- Windows groups, managing
- user accounts, managing
ms.assetid: 25797571-f1f9-42a4-8fff-5b03076bbe36
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0099e683fba7c5f4e2400ad2f9ce005928b0a2aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-hosts-and-service-accounts"></a><span data-ttu-id="70a1f-102">管理主机和服务帐户</span><span class="sxs-lookup"><span data-stu-id="70a1f-102">Managing Hosts and Service Accounts</span></span>
<span data-ttu-id="70a1f-103">配置 BizTalk Server 后，必须对 Windows 组和用户帐户进行管理。</span><span class="sxs-lookup"><span data-stu-id="70a1f-103">After you configure BizTalk Server, you must manage Windows groups and user accounts.</span></span> <span data-ttu-id="70a1f-104">本部分提供有关如何管理 BizTalk Server 中的这些帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="70a1f-104">This section provides information about how to manage these accounts for BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70a1f-105">在多服务器 BizTalk Server 安装中，必须使用全局域组。</span><span class="sxs-lookup"><span data-stu-id="70a1f-105">For a multiserver installation of BizTalk Server you must use a Domain Global group.</span></span> <span data-ttu-id="70a1f-106">而在单服务器 BizTalk Server 安装中，既可以使用全局域组，也可以使用本地组。</span><span class="sxs-lookup"><span data-stu-id="70a1f-106">For a single server installation of BizTalk Server you can use either a Domain Global group or a local group.</span></span>  
  
 <span data-ttu-id="70a1f-107">要执行以下任务，您必须是 Windows 管理员：</span><span class="sxs-lookup"><span data-stu-id="70a1f-107">You must be a Windows administrator to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="70a1f-108">创建主机 Windows 组</span><span class="sxs-lookup"><span data-stu-id="70a1f-108">Create a host Windows group</span></span>  
  
-   <span data-ttu-id="70a1f-109">为每个主机实例创建服务帐户</span><span class="sxs-lookup"><span data-stu-id="70a1f-109">Create service accounts for each host instance</span></span>  
  
-   <span data-ttu-id="70a1f-110">向该主机的 Windows 组中添加服务帐户</span><span class="sxs-lookup"><span data-stu-id="70a1f-110">Add the service accounts to the host Windows group</span></span>  
  
-   <span data-ttu-id="70a1f-111">修改与该主机相关联的 Windows 组</span><span class="sxs-lookup"><span data-stu-id="70a1f-111">Modify the Windows group associated with the host</span></span>  
  
 <span data-ttu-id="70a1f-112">有关完整列表和组和 BizTalk Server 中其关联的用户帐户的说明，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="70a1f-112">For a complete list and description of the groups and their affiliated user accounts in the BizTalk Server, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="70a1f-113">最低安全用户权限来执行管理任务的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。</span><span class="sxs-lookup"><span data-stu-id="70a1f-113">For more information the minimum security user rights for administrative tasks, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="70a1f-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="70a1f-114">In This Section</span></span>  
  
-   [<span data-ttu-id="70a1f-115">如何创建服务帐户的新主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="70a1f-115">How to Create Service Accounts for New Hosts and Host Instances</span></span>](../core/how-to-create-service-accounts-for-new-hosts-and-host-instances.md)  
  
-   [<span data-ttu-id="70a1f-116">如何更改服务帐户和密码</span><span class="sxs-lookup"><span data-stu-id="70a1f-116">How to Change Service Accounts and Passwords</span></span>](../core/how-to-change-service-accounts-and-passwords.md)