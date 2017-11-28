---
title: "密码 Synchronization2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, passwords
- passwords, synchronizing [SSO]
- managing [SSO], synchronizing passwords
- Password Synchronization [SSO]
- Password Synchronization [SSO], about Password Synchronization
- SSO database, passwords
ms.assetid: 6d4970e0-ac73-4fca-ab8f-6c8a6f3a6ec0
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9c12bc9ff5190fe0a76c92b1cfee2233b9d206a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="password-synchronization"></a><span data-ttu-id="b08da-102">密码同步</span><span class="sxs-lookup"><span data-stu-id="b08da-102">Password Synchronization</span></span>
<span data-ttu-id="b08da-103">密码同步的用途是简化 SSO 数据库的管理，使密码在用户目录中保持同步。</span><span class="sxs-lookup"><span data-stu-id="b08da-103">The purpose of Password Synchronization is to simplify administration of the SSO database, and to keep passwords in sync across user directories.</span></span>  
  
 <span data-ttu-id="b08da-104">这两个任务是通过使用密码同步适配器来实现的，本部分中的主题介绍了用于创建和管理这些适配器的命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="b08da-104">These two tasks are accomplished through the use of password synchronization adapters, and the topics in this section describe the command line utility for creating and managing those adapters.</span></span>  
  
 <span data-ttu-id="b08da-105">有三种类型的密码同步子功能。</span><span class="sxs-lookup"><span data-stu-id="b08da-105">There are three types of password synchronization sub-features.</span></span>  
  
 <span data-ttu-id="b08da-106">第一种类型是**到外部的 Windows** (例如，到 RACF 的 Active Directory)。</span><span class="sxs-lookup"><span data-stu-id="b08da-106">The first type is **Windows to External** (for example, Active Directory to RACF).</span></span> <span data-ttu-id="b08da-107">在此方案中，将捕获对 Windows 用户的密码所做的更改，并将其发送到指定用来从域控制器接收密码更改的企业 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="b08da-107">In this scenario, a Windows user's password change is captured and sent to the Enterprise SSO Server assigned to receive password changes from domain controllers.</span></span> <span data-ttu-id="b08da-108">然后，该服务器将密码更改转发到外部系统，SSO 数据库中的映射会与外部系统中所做的更改保持同步。</span><span class="sxs-lookup"><span data-stu-id="b08da-108">This then forwards the password change to an external system and the mapping in the SSO database is kept in sync with the change made on the external system.</span></span>  
  
 <span data-ttu-id="b08da-109">第二种类型是**Windows-完全同步到外部**。</span><span class="sxs-lookup"><span data-stu-id="b08da-109">The second type is **External to Windows - Full synchronization**.</span></span> <span data-ttu-id="b08da-110">在此方案中，将捕获外部系统中的密码，并将其发送到指定用来执行密码同步的企业单一登录服务器，随后该服务器将更新 SSO 数据库中的密码，并同时更新 Active Directory 中 Windows 用户的密码。</span><span class="sxs-lookup"><span data-stu-id="b08da-110">In this scenario, a password is captured on the External system and sent to the Enterprise Single Sign-On server assigned for Password Synchronization which then updates the password in the SSO database, and also updates the Windows user's password in Active Directory.</span></span>  
  
 <span data-ttu-id="b08da-111">第三种类型是**外部的 Windows-部分同步**。</span><span class="sxs-lookup"><span data-stu-id="b08da-111">The third type is **External to Windows - Partial synchronization**.</span></span> <span data-ttu-id="b08da-112">在此方案中，将捕获外部系统中的密码，并将其发送到指定用来执行密码同步的企业单一登录服务器，随后该服务器将更新 SSO 数据库中的密码。</span><span class="sxs-lookup"><span data-stu-id="b08da-112">In this scenario a password is captured on the External system and sent to the Enterprise Single Sign-On server assigned for Password Synchronization which then updates the password in the SSO database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b08da-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="b08da-113">In This Section</span></span>  
  
-   [<span data-ttu-id="b08da-114">如何安装密码同步</span><span class="sxs-lookup"><span data-stu-id="b08da-114">How to Install Password Synchronization</span></span>](../core/how-to-install-password-synchronization.md)  
  
-   [<span data-ttu-id="b08da-115">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="b08da-115">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  
  
-   [<span data-ttu-id="b08da-116">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="b08da-116">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="b08da-117">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="b08da-117">How to Manage Password Synchronization</span></span>](../core/how-to-manage-password-synchronization.md)