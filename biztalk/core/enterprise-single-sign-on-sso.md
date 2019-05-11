---
title: 企业单一登录 (SSO) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- SSO
ms.assetid: beab96f7-f026-4ae1-8462-a165ad76bbec
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dee56153e9eca7112ac0323bbfd604c3d062e86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349290"
---
# <a name="enterprise-single-sign-on-sso"></a><span data-ttu-id="f98df-102">企业单一登录 (SSO)</span><span class="sxs-lookup"><span data-stu-id="f98df-102">Enterprise Single Sign-On (SSO)</span></span>
<span data-ttu-id="f98df-103">企业单一登录 (SSO) 提供的服务来存储和传输加密用户凭据跨本地和网络边界，其中包括域边界。</span><span class="sxs-lookup"><span data-stu-id="f98df-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local and network boundaries, including domain boundaries.</span></span> <span data-ttu-id="f98df-104">SSO 将凭据存储在 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="f98df-104">SSO stores the credentials in the SSO database.</span></span> <span data-ttu-id="f98df-105">由于 SSO 提供了一个泛型单一登录解决方案，中间件应用程序和自定义适配器可以利用 SSO 来安全地存储和传输整个环境的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="f98df-105">Because SSO provides a generic single sign-on solution, middleware applications and custom adapters can leverage SSO to securely store and transmit user credentials across the environment.</span></span> <span data-ttu-id="f98df-106">最终用户无需记住的不同应用程序不同的凭据。</span><span class="sxs-lookup"><span data-stu-id="f98df-106">End users do not have to remember different credentials for different applications.</span></span>  
  
 <span data-ttu-id="f98df-107">单一登录系统包含 SSO 数据库、 主密钥服务器和一个或多个单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="f98df-107">The Single Sign-On system consists of an SSO database, a master secret server, and one or more Single Sign-On servers.</span></span>  
  
 <span data-ttu-id="f98df-108">SSO 系统包含*关联应用程序*管理员定义的。</span><span class="sxs-lookup"><span data-stu-id="f98df-108">The SSO system contains *affiliate applications* that an administrator defines.</span></span> <span data-ttu-id="f98df-109">*关联应用程序*是表示系统或如主机、 后端系统或业务线应用程序的子系统的逻辑实体连接到使用企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="f98df-109">An *affiliate application* is a logical entity that represents a system or sub-system such as a host, back-end system, or line of business application to which you are connecting using Enterprise Single Sign-On.</span></span> <span data-ttu-id="f98df-110">每个关联应用程序具有多个用户映射;例如，它具有在 Active Directory 中用户的凭据和其对应的 RACF 凭据之间的映射。</span><span class="sxs-lookup"><span data-stu-id="f98df-110">Each affiliate application has multiple user mappings; for example, it has the mappings between the credentials for a user in Active Directory and their corresponding RACF credentials.</span></span>  
  
 <span data-ttu-id="f98df-111">SSO 数据库是存储有关关联应用程序，以及所有关联的所有应用程序的加密的用户凭据的信息的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="f98df-111">The SSO database is the SQL Server database that stores the information about the affiliate applications, as well as all of the encrypted user credentials to all the affiliate applications.</span></span>  
  
 <span data-ttu-id="f98df-112">*主密钥服务器*是存储主密钥的企业单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="f98df-112">The *master secret server* is the Enterprise Single Sign-On server that stores the master secret.</span></span> <span data-ttu-id="f98df-113">中的所有其他单一登录服务器系统从主密钥服务器获取主密钥。</span><span class="sxs-lookup"><span data-stu-id="f98df-113">All other Single Sign-On servers in the system get the master secret from the master secret server.</span></span>  
  
 <span data-ttu-id="f98df-114">SSO 系统还包含一个或多个 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="f98df-114">The SSO system also contains one or more SSO Servers.</span></span> <span data-ttu-id="f98df-115">这些服务器的 Microsoft Windows 和后端凭据之间进行映射，并查找 SSO 数据库中的凭据。</span><span class="sxs-lookup"><span data-stu-id="f98df-115">These servers do the mapping between the Microsoft Windows and back-end credentials, and look up the credentials in the SSO database.</span></span> <span data-ttu-id="f98df-116">管理员使用它们来维护 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="f98df-116">Administrators use them to maintain the SSO system.</span></span>  
  
 <span data-ttu-id="f98df-117">完整信息在企业单一登录，请参阅[了解 SSO](../core/understanding-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="f98df-117">For more a complete look at Enterprise Single Sign-On, see [Understanding SSO](../core/understanding-sso.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f98df-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f98df-118">See Also</span></span>  
 [<span data-ttu-id="f98df-119">运行时体系结构</span><span class="sxs-lookup"><span data-stu-id="f98df-119">Runtime Architecture</span></span>](../core/runtime-architecture.md)