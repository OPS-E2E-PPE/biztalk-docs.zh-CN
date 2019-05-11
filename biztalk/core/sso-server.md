---
title: SSO Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, tasks
- Master Secret server, SSO
- servers, SSO
- SSO, servers
- SSO, Master Secret server
ms.assetid: 40240d6b-b7d1-48fb-b750-be0e380d52e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a17d3ad69ab18e9d1916f5a7cf2907021d7d54c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398980"
---
# <a name="sso-server"></a><span data-ttu-id="ad2c7-102">SSO 服务器</span><span class="sxs-lookup"><span data-stu-id="ad2c7-102">SSO Server</span></span>
<span data-ttu-id="ad2c7-103">企业单一登录 (SSO) 服务器可以执行任何以下任务：</span><span class="sxs-lookup"><span data-stu-id="ad2c7-103">The Enterprise Single Sign-On (SSO) server can perform any of the following tasks:</span></span>  
  
-   <span data-ttu-id="ad2c7-104">**主密钥服务器的功能。**</span><span class="sxs-lookup"><span data-stu-id="ad2c7-104">**Functions as the master secret server.**</span></span> <span data-ttu-id="ad2c7-105">主密钥服务器保留持久化的副本的主密钥，或密钥，用于加密在 SSO 系统中的所有凭据。</span><span class="sxs-lookup"><span data-stu-id="ad2c7-105">The master secret server holds a persisted copy of the master secret, or key, used to encrypt all the credentials in the SSO system.</span></span> <span data-ttu-id="ad2c7-106">尽管在主密钥服务器可充当用于查找和管理的服务器，建议使用此服务器仅充当主密钥服务器出于安全原因。</span><span class="sxs-lookup"><span data-stu-id="ad2c7-106">Though the master secret server can act as a server for lookups and administration, it is recommended to use this server to act only as a master secret server for security reasons.</span></span> <span data-ttu-id="ad2c7-107">主密钥服务器执行这些函数的详细信息，请参阅[主密钥服务器](../core/master-secret-server.md)。</span><span class="sxs-lookup"><span data-stu-id="ad2c7-107">For more information about the functions the master secret server performs, see [Master Secret Server](../core/master-secret-server.md).</span></span>  
  
-   <span data-ttu-id="ad2c7-108">**执行管理操作。**</span><span class="sxs-lookup"><span data-stu-id="ad2c7-108">**Performs administrative operations.**</span></span> <span data-ttu-id="ad2c7-109">SSO 管理员可以使用任何单一登录服务器来执行管理任务，例如管理关联应用程序设置的用户凭据，以及管理用户映射。</span><span class="sxs-lookup"><span data-stu-id="ad2c7-109">SSO administrators can use any of the Single Sign-On Servers to perform administrative tasks such as managing affiliate applications, setting user credentials, and managing user mappings.</span></span>  
  
-   <span data-ttu-id="ad2c7-110">**执行查找操作。**</span><span class="sxs-lookup"><span data-stu-id="ad2c7-110">**Performs lookup operations.**</span></span> <span data-ttu-id="ad2c7-111">SSO 服务器使用的运行时组件要查找的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="ad2c7-111">The SSO server uses the runtime component to look up the user credentials.</span></span>  
  
-   <span data-ttu-id="ad2c7-112">**颁发并兑换票证。**</span><span class="sxs-lookup"><span data-stu-id="ad2c7-112">**Issues and Redeems Tickets.**</span></span> <span data-ttu-id="ad2c7-113">SSO 服务器还颁发并兑换 SSO 票证。</span><span class="sxs-lookup"><span data-stu-id="ad2c7-113">The SSO server also issues and redeems SSO tickets.</span></span>  
  
-   <span data-ttu-id="ad2c7-114">**密码同步。**</span><span class="sxs-lookup"><span data-stu-id="ad2c7-114">**Password Synchronization.**</span></span> <span data-ttu-id="ad2c7-115">您可以创建和管理 SSO 服务器上的密码同步适配器。</span><span class="sxs-lookup"><span data-stu-id="ad2c7-115">You can create and manage password synchronization adapters on the SSO Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad2c7-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad2c7-116">See Also</span></span>  
 <span data-ttu-id="ad2c7-117">[使用 SSO](../core/using-sso.md) </span><span class="sxs-lookup"><span data-stu-id="ad2c7-117">[Using SSO](../core/using-sso.md) </span></span>  
 [<span data-ttu-id="ad2c7-118">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="ad2c7-118">Installing SSO</span></span>](../core/installing-sso.md)