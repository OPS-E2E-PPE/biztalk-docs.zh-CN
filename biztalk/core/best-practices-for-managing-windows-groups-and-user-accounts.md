---
title: 管理 Windows 组和用户帐户的最佳实践 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, Windows groups
- authenticating, best practices
- Windows groups, security
- best practices, user accounts
- best practices, security
- security, best practices
- user accounts, security
- authenticating, security
- Windows groups, best practices
- best practices, authenticating
- user accounts, best practices
- hosts, security
- hosts, best practices
- best practices, hosts
ms.assetid: 0c4a141e-97ce-434a-8e45-a56c634bbd6c
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6720135f15b2c6d50bb193cd6e533e5b06f71961
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358205"
---
# <a name="best-practices-for-managing-windows-groups-and-user-accounts"></a><span data-ttu-id="45379-102">管理 Windows 组和用户帐户的最佳实践</span><span class="sxs-lookup"><span data-stu-id="45379-102">Best Practices for Managing Windows Groups and User Accounts</span></span>
<span data-ttu-id="45379-103">本部分包含最佳实践和管理安全性的 Windows 组和用户帐户的提示。</span><span class="sxs-lookup"><span data-stu-id="45379-103">This section contains best practices and tips for managing security for Windows groups and user accounts.</span></span>  
  
-   <span data-ttu-id="45379-104">**使用具有主机实例所需的最小特权的服务帐户**</span><span class="sxs-lookup"><span data-stu-id="45379-104">**Use service accounts with minimum privileges necessary for host instances**</span></span>  
  
     <span data-ttu-id="45379-105">若要帮助确保 BizTalk Server 环境的安全性，我们建议使用具有运行主机实例所需的最小特权的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="45379-105">To help ensure the security of your BizTalk Server environment, we recommend that you use service accounts with the minimum privileges necessary to run host instances.</span></span> <span data-ttu-id="45379-106">有关服务帐户需要的最小特权的详细信息，请参阅[访问控制和数据安全性](../core/access-control-and-data-security.md)。</span><span class="sxs-lookup"><span data-stu-id="45379-106">For more information about the minimum privileges that service accounts require, see [Access Control and Data Security](../core/access-control-and-data-security.md).</span></span>  
  
-   <span data-ttu-id="45379-107">**受信任的身份验证和非信任主机使用不同的用户组**</span><span class="sxs-lookup"><span data-stu-id="45379-107">**Use different user groups for authentication trusted and non-trusted hosts**</span></span>  
  
     <span data-ttu-id="45379-108">若要确保不受信任的主机具有较少的权限不是身份验证受信任的主机，必须为每个主机使用不同的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="45379-108">To ensure that non-authentication trusted hosts have fewer privileges than authentication trusted hosts, you must use different service accounts for each host.</span></span>  
  
-   <span data-ttu-id="45379-109">**为每个 BizTalk 主机使用不同的用户组**</span><span class="sxs-lookup"><span data-stu-id="45379-109">**Use a different user group for each BizTalk Host**</span></span>  
  
     <span data-ttu-id="45379-110">为获得最佳的主机之间的安全边界，我们建议你使用不同的 Windows 用户组每个 BizTalk 主机对 BizTalk 组中。</span><span class="sxs-lookup"><span data-stu-id="45379-110">To maximize the security boundary between hosts, we recommend that you use a different Windows user group for each BizTalk Host in your BizTalk group.</span></span>  
  
-   <span data-ttu-id="45379-111">**从 BizTalk Server Administrators 组中删除安装用户**</span><span class="sxs-lookup"><span data-stu-id="45379-111">**Remove the installation user from the BizTalk Server Administrators group**</span></span>  
  
     <span data-ttu-id="45379-112">当使用本地组，一台计算机上安装 BizTalk Server 时，执行交互式安装的 BizTalk Server 的用户是自动添加到 BizTalk Server Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="45379-112">When you install BizTalk Server on a single computer with local groups, the user performing an interactive installation of BizTalk Server is automatically added to the BizTalk Server Administrators group.</span></span> <span data-ttu-id="45379-113">这允许该用户就可以使用 Configuration Manager 中配置 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="45379-113">This allows that user to configure BizTalk Server with the Configuration Manager.</span></span>  
  
     <span data-ttu-id="45379-114">如果安装 BizTalk Server 的用户不管理 BizTalk Server，我们建议配置 BizTalk Server 后，从 BizTalk Server Administrators 组删除此用户。</span><span class="sxs-lookup"><span data-stu-id="45379-114">If the user who installs BizTalk Server will not be administering BizTalk Server, we recommend that you remove this user from the BizTalk Server Administrators group after BizTalk Server is configured.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45379-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="45379-115">See Also</span></span>  
 [<span data-ttu-id="45379-116">管理 BizTalk Server 安全性</span><span class="sxs-lookup"><span data-stu-id="45379-116">Managing BizTalk Server Security</span></span>](../core/managing-biztalk-server-security.md)