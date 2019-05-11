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
ms.openlocfilehash: 527929bbd78c463bf5ef7eb97bc3bcc06d16fe0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65326683"
---
# <a name="managing-hosts-and-service-accounts"></a><span data-ttu-id="0908a-102">管理主机和服务帐户</span><span class="sxs-lookup"><span data-stu-id="0908a-102">Managing Hosts and Service Accounts</span></span>
<span data-ttu-id="0908a-103">配置 BizTalk Server 后，你必须管理 Windows 组和用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0908a-103">After you configure BizTalk Server, you must manage Windows groups and user accounts.</span></span> <span data-ttu-id="0908a-104">本部分提供有关如何为 BizTalk Server 管理这些帐户的信息。</span><span class="sxs-lookup"><span data-stu-id="0908a-104">This section provides information about how to manage these accounts for BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0908a-105">对于多服务器安装 BizTalk Server 必须使用全局域组。</span><span class="sxs-lookup"><span data-stu-id="0908a-105">For a multiserver installation of BizTalk Server you must use a Domain Global group.</span></span> <span data-ttu-id="0908a-106">有关在单一服务器上安装 BizTalk Server 可以使用全局域组或本地组。</span><span class="sxs-lookup"><span data-stu-id="0908a-106">For a single server installation of BizTalk Server you can use either a Domain Global group or a local group.</span></span>  
  
 <span data-ttu-id="0908a-107">您必须是 Windows 管理员，才能执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="0908a-107">You must be a Windows administrator to perform the following tasks:</span></span>  
  
- <span data-ttu-id="0908a-108">创建主机 Windows 组</span><span class="sxs-lookup"><span data-stu-id="0908a-108">Create a host Windows group</span></span>  
  
- <span data-ttu-id="0908a-109">创建每个主机实例服务帐户</span><span class="sxs-lookup"><span data-stu-id="0908a-109">Create service accounts for each host instance</span></span>  
  
- <span data-ttu-id="0908a-110">将服务帐户添加到主机 Windows 组</span><span class="sxs-lookup"><span data-stu-id="0908a-110">Add the service accounts to the host Windows group</span></span>  
  
- <span data-ttu-id="0908a-111">修改与主机相关联的 Windows 组</span><span class="sxs-lookup"><span data-stu-id="0908a-111">Modify the Windows group associated with the host</span></span>  
  
  <span data-ttu-id="0908a-112">有关完整列表和组和 BizTalk Server 中其关联的用户帐户的说明，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0908a-112">For a complete list and description of the groups and their affiliated user accounts in the BizTalk Server, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
  <span data-ttu-id="0908a-113">最低安全用户权限来执行管理任务的详细信息，请参阅[最低安全用户权限](../core/minimum-security-user-rights.md)。</span><span class="sxs-lookup"><span data-stu-id="0908a-113">For more information the minimum security user rights for administrative tasks, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0908a-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="0908a-114">In This Section</span></span>  
  
-   [<span data-ttu-id="0908a-115">如何创建服务帐户为新主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="0908a-115">How to Create Service Accounts for New Hosts and Host Instances</span></span>](../core/how-to-create-service-accounts-for-new-hosts-and-host-instances.md)  
  
-   [<span data-ttu-id="0908a-116">如何更改服务帐户和密码</span><span class="sxs-lookup"><span data-stu-id="0908a-116">How to Change Service Accounts and Passwords</span></span>](../core/how-to-change-service-accounts-and-passwords.md)