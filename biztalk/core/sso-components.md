---
title: SSO 组件 |Microsoft 文档
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
ms.openlocfilehash: c1111f1a0dfac47412ae28b58f93ddc51e1f562b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276469"
---
# <a name="sso-components"></a><span data-ttu-id="ec190-102">SSO 组件</span><span class="sxs-lookup"><span data-stu-id="ec190-102">SSO Components</span></span>
<span data-ttu-id="ec190-103">企业单一登录 (SSO) 服务的子服务如下所示：</span><span class="sxs-lookup"><span data-stu-id="ec190-103">The sub services of the Enterprise Single Sign-On (SSO) service are as follows:</span></span>  
  
-   <span data-ttu-id="ec190-104">**映射。**</span><span class="sxs-lookup"><span data-stu-id="ec190-104">**Mapping.**</span></span> <span data-ttu-id="ec190-105">此组件将 Windows 系统的用户帐户中的用户帐户映射后端系统中。</span><span class="sxs-lookup"><span data-stu-id="ec190-105">This component maps the user account in the Windows system to the user accounts in the back-end systems.</span></span>  
  
-   <span data-ttu-id="ec190-106">**查找。**</span><span class="sxs-lookup"><span data-stu-id="ec190-106">**Lookup.**</span></span> <span data-ttu-id="ec190-107">此组件后端系统中查找的 SSO 数据库中的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="ec190-107">This component looks up the user credentials in the SSO database in the back-end system.</span></span> <span data-ttu-id="ec190-108">这是 SSO 运行时组件。</span><span class="sxs-lookup"><span data-stu-id="ec190-108">This is the SSO runtime component.</span></span>  
  
-   <span data-ttu-id="ec190-109">**管理。**</span><span class="sxs-lookup"><span data-stu-id="ec190-109">**Administration.**</span></span> <span data-ttu-id="ec190-110">此组件管理关联应用程序和每个关联应用程序的映射。</span><span class="sxs-lookup"><span data-stu-id="ec190-110">This component manages the affiliate applications and the mappings for each affiliate application.</span></span>  
  
-   <span data-ttu-id="ec190-111">**机密。**</span><span class="sxs-lookup"><span data-stu-id="ec190-111">**Secret.**</span></span> <span data-ttu-id="ec190-112">此组件生成主密钥并将其分发给其他 SSO 服务器中，在系统中。</span><span class="sxs-lookup"><span data-stu-id="ec190-112">This component generates the master secret and distributes it to the other SSO servers in the system.</span></span> <span data-ttu-id="ec190-113">仅在充当主密钥服务器上单一登录服务器上活动。</span><span class="sxs-lookup"><span data-stu-id="ec190-113">It is only active on the Single Sign-On server that is acting as the master secret server.</span></span>  
  
-   <span data-ttu-id="ec190-114">**密码同步。**</span><span class="sxs-lookup"><span data-stu-id="ec190-114">**Password Synchronization.**</span></span> <span data-ttu-id="ec190-115">此组件，来简化管理 SSO 数据库中，并保持密码同步在用户的目录。</span><span class="sxs-lookup"><span data-stu-id="ec190-115">This component simplifies administration of the SSO database, and keeps passwords in sync across user directories.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec190-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec190-116">See Also</span></span>  
 <span data-ttu-id="ec190-117">[SSO 服务器](../core/sso-server.md) </span><span class="sxs-lookup"><span data-stu-id="ec190-117">[SSO Server](../core/sso-server.md) </span></span>  
 [<span data-ttu-id="ec190-118">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="ec190-118">Installing SSO</span></span>](../core/installing-sso.md)