---
title: 管理主机和服务帐户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0f33a484d67981bb72908243b82e7835e0390e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016111"
---
# <a name="managing-hosts-and-service-accounts"></a><span data-ttu-id="10f9b-102">管理主机和服务帐户</span><span class="sxs-lookup"><span data-stu-id="10f9b-102">Managing Hosts and Service Accounts</span></span>
<span data-ttu-id="10f9b-103">配置 BizTalk Server 后，必须对 Windows 组和用户帐户进行管理。</span><span class="sxs-lookup"><span data-stu-id="10f9b-103">After you configure BizTalk Server, you must manage Windows groups and user accounts.</span></span> <span data-ttu-id="10f9b-104">本部分提供有关如何管理 BizTalk Server 中的这些帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="10f9b-104">This section provides information about how to manage these accounts for BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10f9b-105">在多服务器 BizTalk Server 安装中，必须使用全局域组。</span><span class="sxs-lookup"><span data-stu-id="10f9b-105">For a multiserver installation of BizTalk Server you must use a Domain Global group.</span></span> <span data-ttu-id="10f9b-106">而在单服务器 BizTalk Server 安装中，既可以使用全局域组，也可以使用本地组。</span><span class="sxs-lookup"><span data-stu-id="10f9b-106">For a single server installation of BizTalk Server you can use either a Domain Global group or a local group.</span></span>  
  
 <span data-ttu-id="10f9b-107">要执行以下任务，您必须是 Windows 管理员：</span><span class="sxs-lookup"><span data-stu-id="10f9b-107">You must be a Windows administrator to perform the following tasks:</span></span>  
  
- <span data-ttu-id="10f9b-108">创建主机 Windows 组</span><span class="sxs-lookup"><span data-stu-id="10f9b-108">Create a host Windows group</span></span>  
  
- <span data-ttu-id="10f9b-109">为每个主机实例创建服务帐户</span><span class="sxs-lookup"><span data-stu-id="10f9b-109">Create service accounts for each host instance</span></span>  
  
- <span data-ttu-id="10f9b-110">向该主机的 Windows 组中添加服务帐户</span><span class="sxs-lookup"><span data-stu-id="10f9b-110">Add the service accounts to the host Windows group</span></span>  
  
- <span data-ttu-id="10f9b-111">修改与该主机相关联的 Windows 组</span><span class="sxs-lookup"><span data-stu-id="10f9b-111">Modify the Windows group associated with the host</span></span>  
  
  <span data-ttu-id="10f9b-112">有关完整列表和组和 BizTalk Server 中其关联的用户帐户的说明，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="10f9b-112">For a complete list and description of the groups and their affiliated user accounts in the BizTalk Server, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
  <span data-ttu-id="10f9b-113">最低安全用户权限来执行管理任务的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。</span><span class="sxs-lookup"><span data-stu-id="10f9b-113">For more information the minimum security user rights for administrative tasks, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10f9b-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="10f9b-114">In This Section</span></span>  
  
-   [<span data-ttu-id="10f9b-115">如何创建服务帐户为新主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="10f9b-115">How to Create Service Accounts for New Hosts and Host Instances</span></span>](../core/how-to-create-service-accounts-for-new-hosts-and-host-instances.md)  
  
-   [<span data-ttu-id="10f9b-116">如何更改服务帐户和密码</span><span class="sxs-lookup"><span data-stu-id="10f9b-116">How to Change Service Accounts and Passwords</span></span>](../core/how-to-change-service-accounts-and-passwords.md)