---
title: "企业单一登录 (SSO) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- SSO
ms.assetid: beab96f7-f026-4ae1-8462-a165ad76bbec
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6cbc5f514d13cd8457cd9417be5ea5b78408e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="enterprise-single-sign-on-sso"></a><span data-ttu-id="d88fc-102">企业单一登录 (SSO)</span><span class="sxs-lookup"><span data-stu-id="d88fc-102">Enterprise Single Sign-On (SSO)</span></span>
<span data-ttu-id="d88fc-103">使用企业单一登录 (SSO) 提供的服务，可以跨本地和网络边界（包括域边界）存储和传输加密的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="d88fc-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local and network boundaries, including domain boundaries.</span></span> <span data-ttu-id="d88fc-104">SSO 将凭据存储在 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="d88fc-104">SSO stores the credentials in the SSO database.</span></span> <span data-ttu-id="d88fc-105">由于 SSO 提供了通用的单一登录解决方案，因此中间件应用程序和自定义适配器可以利用 SSO 来跨环境安全地存储和传输用户凭据。</span><span class="sxs-lookup"><span data-stu-id="d88fc-105">Because SSO provides a generic single sign-on solution, middleware applications and custom adapters can leverage SSO to securely store and transmit user credentials across the environment.</span></span> <span data-ttu-id="d88fc-106">最终用户不必为不同的应用程序记住不同的凭据。</span><span class="sxs-lookup"><span data-stu-id="d88fc-106">End users do not have to remember different credentials for different applications.</span></span>  
  
 <span data-ttu-id="d88fc-107">单一登录系统由以下部分组成：SSO 数据库、主密钥服务器以及一个或多个单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="d88fc-107">The Single Sign-On system consists of an SSO database, a master secret server, and one or more Single Sign-On servers.</span></span>  
  
 <span data-ttu-id="d88fc-108">SSO 系统包含*affiliate 应用程序*管理员定义的。</span><span class="sxs-lookup"><span data-stu-id="d88fc-108">The SSO system contains *affiliate applications* that an administrator defines.</span></span> <span data-ttu-id="d88fc-109">*Affiliate 应用程序*是表示系统或如主机、 后端系统或业务线应用程序的子系统的逻辑实体连接到使用企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="d88fc-109">An *affiliate application* is a logical entity that represents a system or sub-system such as a host, back-end system, or line of business application to which you are connecting using Enterprise Single Sign-On.</span></span> <span data-ttu-id="d88fc-110">每个关联应用程序都具有多个用户映射；例如，关联应用程序具有 Active Directory 中的用户凭据与其对应的 RACF 凭据之间的映射。</span><span class="sxs-lookup"><span data-stu-id="d88fc-110">Each affiliate application has multiple user mappings; for example, it has the mappings between the credentials for a user in Active Directory and their corresponding RACF credentials.</span></span>  
  
 <span data-ttu-id="d88fc-111">SSO 数据库是存储有关关联应用程序，以及所有关联的所有应用程序的加密的用户凭据的信息的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="d88fc-111">The SSO database is the SQL Server database that stores the information about the affiliate applications, as well as all of the encrypted user credentials to all the affiliate applications.</span></span>  
  
 <span data-ttu-id="d88fc-112">*主密钥服务器*是企业单一登录服务器，它将存储主密钥。</span><span class="sxs-lookup"><span data-stu-id="d88fc-112">The *master secret server* is the Enterprise Single Sign-On server that stores the master secret.</span></span> <span data-ttu-id="d88fc-113">系统中的其他所有单一登录服务器都从主密钥服务器中获取主密钥。</span><span class="sxs-lookup"><span data-stu-id="d88fc-113">All other Single Sign-On servers in the system get the master secret from the master secret server.</span></span>  
  
 <span data-ttu-id="d88fc-114">SSO 系统还包含一个或多个 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="d88fc-114">The SSO system also contains one or more SSO Servers.</span></span> <span data-ttu-id="d88fc-115">这些服务器在 Microsoft Windows 凭据与后端凭据之间进行映射，并在 SSO 数据库中查找凭据。</span><span class="sxs-lookup"><span data-stu-id="d88fc-115">These servers do the mapping between the Microsoft Windows and back-end credentials, and look up the credentials in the SSO database.</span></span> <span data-ttu-id="d88fc-116">管理员可使用这些服务器来维护 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="d88fc-116">Administrators use them to maintain the SSO system.</span></span>  
  
 <span data-ttu-id="d88fc-117">有关更完整查看在企业单一登录，请参阅[了解 SSO](../core/understanding-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="d88fc-117">For more a complete look at Enterprise Single Sign-On, see [Understanding SSO](../core/understanding-sso.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d88fc-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d88fc-118">See Also</span></span>  
 [<span data-ttu-id="d88fc-119">运行时体系结构</span><span class="sxs-lookup"><span data-stu-id="d88fc-119">Runtime Architecture</span></span>](../core/runtime-architecture.md)