---
title: 单一登录： 事件 10683 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83cd1b96-cd79-4ddc-952b-94a7de216666
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c383a02400523686f00011c5eb6f71c9542ec5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271541"
---
# <a name="single-sign-on-event-10683"></a><span data-ttu-id="c69ea-102">单一登录： 事件 10683</span><span class="sxs-lookup"><span data-stu-id="c69ea-102">Single Sign-On: Event 10683</span></span>
## <a name="details"></a><span data-ttu-id="c69ea-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c69ea-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c69ea-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c69ea-104">Product Name</span></span>|<span data-ttu-id="c69ea-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c69ea-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="c69ea-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c69ea-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="c69ea-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c69ea-107">Event ID</span></span>|<span data-ttu-id="c69ea-108">10683</span><span class="sxs-lookup"><span data-stu-id="c69ea-108">10683</span></span>|  
|<span data-ttu-id="c69ea-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c69ea-109">Event Source</span></span>|<span data-ttu-id="c69ea-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c69ea-110">ENTSSO</span></span>|  
|<span data-ttu-id="c69ea-111">组件</span><span class="sxs-lookup"><span data-stu-id="c69ea-111">Component</span></span>|<span data-ttu-id="c69ea-112">N\A</span><span class="sxs-lookup"><span data-stu-id="c69ea-112">N\A</span></span>|  
|<span data-ttu-id="c69ea-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c69ea-113">Symbolic Name</span></span>|<span data-ttu-id="c69ea-114">SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD</span><span class="sxs-lookup"><span data-stu-id="c69ea-114">SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD</span></span>|  
|<span data-ttu-id="c69ea-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c69ea-115">Message Text</span></span>|<span data-ttu-id="c69ea-116">重播文件已删除，因为它太 old.%r</span><span class="sxs-lookup"><span data-stu-id="c69ea-116">A replay file was deleted because it was too old.%r</span></span><br /><span data-ttu-id="c69ea-117">重播文件： %1</span><span class="sxs-lookup"><span data-stu-id="c69ea-117">Replay File: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c69ea-118">解释</span><span class="sxs-lookup"><span data-stu-id="c69ea-118">Explanation</span></span>  
 <span data-ttu-id="c69ea-119">此警告事件表明重播文件因太旧而被删除。</span><span class="sxs-lookup"><span data-stu-id="c69ea-119">This Warning event indicates that the replay file was deleted because it was too old.</span></span> <span data-ttu-id="c69ea-120">ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="c69ea-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="c69ea-121">在这种情况下，密码更改存储在临时的加密文件中，在重新变为可用时重播回 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="c69ea-121">In this case the password changes are stored in a temporary encrypted file and are replayed back to the SSO database when it again becomes available.</span></span> <span data-ttu-id="c69ea-122">当要将文件重播回 SSO 数据库时，如果检测到文件太旧，则会放弃该文件。</span><span class="sxs-lookup"><span data-stu-id="c69ea-122">When it is time to replay the files back to the SSO database, if a file is detected that is too old, it is discarded.</span></span> <span data-ttu-id="c69ea-123">所有旧的密码更改将被丢弃 SSO 密码同步系统;`password sync age`参数确定密码的最大时间段更改请求和可以使用命令行工具控制， **ssoconfig-syncAge**或 SSO 管理 MMC。</span><span class="sxs-lookup"><span data-stu-id="c69ea-123">All old password changes are discarded by the SSO password sync system; the `password sync age` parameter determines the maximum age for password change requests and that can be controlled using the command line tools **ssoconfig –syncAge** or the SSO Admin MMC.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c69ea-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="c69ea-124">User Action</span></span>  
  
-   <span data-ttu-id="c69ea-125">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="c69ea-125">No user action is necessary.</span></span>  
  
 <span data-ttu-id="c69ea-126">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="c69ea-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="c69ea-127">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="c69ea-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="c69ea-128">密码同步</span><span class="sxs-lookup"><span data-stu-id="c69ea-128">Password Synchronization</span></span>](../core/password-synchronization2.md)