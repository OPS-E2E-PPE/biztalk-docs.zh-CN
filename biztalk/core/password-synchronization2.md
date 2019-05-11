---
title: 密码 Synchronization2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, passwords
- passwords, synchronizing [SSO]
- managing [SSO], synchronizing passwords
- Password Synchronization [SSO]
- Password Synchronization [SSO], about Password Synchronization
- SSO database, passwords
ms.assetid: 6d4970e0-ac73-4fca-ab8f-6c8a6f3a6ec0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ade05264bd65fc43c240ba377f4e99f26167bf3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394983"
---
# <a name="password-synchronization"></a><span data-ttu-id="e7ddd-102">密码同步</span><span class="sxs-lookup"><span data-stu-id="e7ddd-102">Password Synchronization</span></span>
<span data-ttu-id="e7ddd-103">密码同步的目的是为了简化管理的 SSO 数据库中，并以使密码各个用户目录间保持同步。</span><span class="sxs-lookup"><span data-stu-id="e7ddd-103">The purpose of Password Synchronization is to simplify administration of the SSO database, and to keep passwords in sync across user directories.</span></span>  
  
 <span data-ttu-id="e7ddd-104">这两项任务完成通过使用密码同步适配器，并在本部分中的主题介绍用于创建和管理这些适配器的命令行实用程序。</span><span class="sxs-lookup"><span data-stu-id="e7ddd-104">These two tasks are accomplished through the use of password synchronization adapters, and the topics in this section describe the command line utility for creating and managing those adapters.</span></span>  
  
 <span data-ttu-id="e7ddd-105">有三种类型的密码同步子功能。</span><span class="sxs-lookup"><span data-stu-id="e7ddd-105">There are three types of password synchronization sub-features.</span></span>  
  
 <span data-ttu-id="e7ddd-106">第一种类型是**外部到 Windows** (可以使用例如，Active Directory 到 RACF)。</span><span class="sxs-lookup"><span data-stu-id="e7ddd-106">The first type is **Windows to External** (for example, Active Directory to RACF).</span></span> <span data-ttu-id="e7ddd-107">在此方案中，捕获并发送到企业 SSO 服务器分配给从域控制器接收密码更改将 Windows 用户的密码更改。</span><span class="sxs-lookup"><span data-stu-id="e7ddd-107">In this scenario, a Windows user's password change is captured and sent to the Enterprise SSO Server assigned to receive password changes from domain controllers.</span></span> <span data-ttu-id="e7ddd-108">这会将转发到外部系统密码更改和 SSO 数据库中的映射与外部系统上所做的更改保持同步。</span><span class="sxs-lookup"><span data-stu-id="e7ddd-108">This then forwards the password change to an external system and the mapping in the SSO database is kept in sync with the change made on the external system.</span></span>  
  
 <span data-ttu-id="e7ddd-109">第二个类型是**外部到 Windows-完全同步**。</span><span class="sxs-lookup"><span data-stu-id="e7ddd-109">The second type is **External to Windows - Full synchronization**.</span></span> <span data-ttu-id="e7ddd-110">在此方案中，密码是捕获外部系统，发送到企业单一登录服务器分配来执行密码同步，然后更新 SSO 数据库中的密码，并还会更新在活动中的 Windows 用户的密码目录。</span><span class="sxs-lookup"><span data-stu-id="e7ddd-110">In this scenario, a password is captured on the External system and sent to the Enterprise Single Sign-On server assigned for Password Synchronization which then updates the password in the SSO database, and also updates the Windows user's password in Active Directory.</span></span>  
  
 <span data-ttu-id="e7ddd-111">第三种类型是**外部到 Windows-部分同步**。</span><span class="sxs-lookup"><span data-stu-id="e7ddd-111">The third type is **External to Windows - Partial synchronization**.</span></span> <span data-ttu-id="e7ddd-112">在此方案中密码被捕获外部系统，并发送到指定用来更新 SSO 数据库中的密码的密码同步的企业单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="e7ddd-112">In this scenario a password is captured on the External system and sent to the Enterprise Single Sign-On server assigned for Password Synchronization which then updates the password in the SSO database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7ddd-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="e7ddd-113">In This Section</span></span>  
  
-   [<span data-ttu-id="e7ddd-114">如何安装密码同步</span><span class="sxs-lookup"><span data-stu-id="e7ddd-114">How to Install Password Synchronization</span></span>](../core/how-to-install-password-synchronization.md)  
  
-   [<span data-ttu-id="e7ddd-115">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="e7ddd-115">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  
  
-   [<span data-ttu-id="e7ddd-116">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="e7ddd-116">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="e7ddd-117">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="e7ddd-117">How to Manage Password Synchronization</span></span>](../core/how-to-manage-password-synchronization.md)