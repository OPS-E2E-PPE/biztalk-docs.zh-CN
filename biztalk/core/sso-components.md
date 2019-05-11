---
title: SSO 组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- passwords, synchronizing [SSO]
- SSO, components
- SSO, password synchronization
- SSO, sub-services
ms.assetid: e29e68df-f770-4220-a9f8-cb9323403017
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e7e00ad4dfb82d2c6e16c45a09c4f452b33081b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401762"
---
# <a name="sso-components"></a><span data-ttu-id="0fbf6-102">SSO 组件</span><span class="sxs-lookup"><span data-stu-id="0fbf6-102">SSO Components</span></span>
<span data-ttu-id="0fbf6-103">企业单一登录 (SSO) 服务的子服务如下所示：</span><span class="sxs-lookup"><span data-stu-id="0fbf6-103">The sub services of the Enterprise Single Sign-On (SSO) service are as follows:</span></span>  
  
-   <span data-ttu-id="0fbf6-104">**映射。**</span><span class="sxs-lookup"><span data-stu-id="0fbf6-104">**Mapping.**</span></span> <span data-ttu-id="0fbf6-105">此组件将用户帐户在 Windows 系统中的用户帐户映射的后端系统中。</span><span class="sxs-lookup"><span data-stu-id="0fbf6-105">This component maps the user account in the Windows system to the user accounts in the back-end systems.</span></span>  
  
-   <span data-ttu-id="0fbf6-106">**查找。**</span><span class="sxs-lookup"><span data-stu-id="0fbf6-106">**Lookup.**</span></span> <span data-ttu-id="0fbf6-107">此组件将在后端系统中查找 SSO 数据库中的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="0fbf6-107">This component looks up the user credentials in the SSO database in the back-end system.</span></span> <span data-ttu-id="0fbf6-108">这是 SSO 运行时组件。</span><span class="sxs-lookup"><span data-stu-id="0fbf6-108">This is the SSO runtime component.</span></span>  
  
-   <span data-ttu-id="0fbf6-109">**管理。**</span><span class="sxs-lookup"><span data-stu-id="0fbf6-109">**Administration.**</span></span> <span data-ttu-id="0fbf6-110">此组件管理关联应用程序和每个关联应用程序的映射。</span><span class="sxs-lookup"><span data-stu-id="0fbf6-110">This component manages the affiliate applications and the mappings for each affiliate application.</span></span>  
  
-   <span data-ttu-id="0fbf6-111">**Secret.**</span><span class="sxs-lookup"><span data-stu-id="0fbf6-111">**Secret.**</span></span> <span data-ttu-id="0fbf6-112">此组件生成主密钥，并在系统中将其分发给其他 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="0fbf6-112">This component generates the master secret and distributes it to the other SSO servers in the system.</span></span> <span data-ttu-id="0fbf6-113">它只是活动的单一登录服务器充当在主密钥服务器上。</span><span class="sxs-lookup"><span data-stu-id="0fbf6-113">It is only active on the Single Sign-On server that is acting as the master secret server.</span></span>  
  
-   <span data-ttu-id="0fbf6-114">**密码同步。**</span><span class="sxs-lookup"><span data-stu-id="0fbf6-114">**Password Synchronization.**</span></span> <span data-ttu-id="0fbf6-115">此组件可以简化管理 SSO 数据库中，并保留密码各个用户目录间保持同步。</span><span class="sxs-lookup"><span data-stu-id="0fbf6-115">This component simplifies administration of the SSO database, and keeps passwords in sync across user directories.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fbf6-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fbf6-116">See Also</span></span>  
 <span data-ttu-id="0fbf6-117">[SSO Server](../core/sso-server.md) </span><span class="sxs-lookup"><span data-stu-id="0fbf6-117">[SSO Server](../core/sso-server.md) </span></span>  
 [<span data-ttu-id="0fbf6-118">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="0fbf6-118">Installing SSO</span></span>](../core/installing-sso.md)