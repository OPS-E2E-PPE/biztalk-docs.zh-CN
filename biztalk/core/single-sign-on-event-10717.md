---
title: 单一登录：Event 10717 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14691e0f-a399-4b4d-9dd5-516bf8d3a167
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c47ff4ceb707d1cbd353f88c9335d226a9a0158d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397170"
---
# <a name="single-sign-on-event-10717"></a><span data-ttu-id="929b6-102">单一登录：事件 10717</span><span class="sxs-lookup"><span data-stu-id="929b6-102">Single Sign-On: Event 10717</span></span>
## <a name="details"></a><span data-ttu-id="929b6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="929b6-103">Details</span></span>  

|                 |                                                                                                                                                  |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="929b6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="929b6-104">Product Name</span></span>   |                                                            <span data-ttu-id="929b6-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="929b6-105">Enterprise Single Sign-On</span></span>                                                             |
| <span data-ttu-id="929b6-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="929b6-106">Product Version</span></span> |                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                            |
|    <span data-ttu-id="929b6-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="929b6-107">Event ID</span></span>     |                                                                      <span data-ttu-id="929b6-108">10717</span><span class="sxs-lookup"><span data-stu-id="929b6-108">10717</span></span>                                                                       |
|  <span data-ttu-id="929b6-109">事件源</span><span class="sxs-lookup"><span data-stu-id="929b6-109">Event Source</span></span>   |                                                                      <span data-ttu-id="929b6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="929b6-110">ENTSSO</span></span>                                                                      |
|    <span data-ttu-id="929b6-111">组件</span><span class="sxs-lookup"><span data-stu-id="929b6-111">Component</span></span>    |                                                                       <span data-ttu-id="929b6-112">N\A</span><span class="sxs-lookup"><span data-stu-id="929b6-112">N\A</span></span>                                                                        |
|  <span data-ttu-id="929b6-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="929b6-113">Symbolic Name</span></span>  |                                                         <span data-ttu-id="929b6-114">SSO_ERROR_NEW_REPLAY_DIR_FAILED</span><span class="sxs-lookup"><span data-stu-id="929b6-114">SSO_ERROR_NEW_REPLAY_DIR_FAILED</span></span>                                                          |
|  <span data-ttu-id="929b6-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="929b6-115">Message Text</span></span>   | <span data-ttu-id="929b6-116">无法创建重播文件 directory.%r</span><span class="sxs-lookup"><span data-stu-id="929b6-116">Failed to create the replay files directory.%r</span></span><br /><br /> <span data-ttu-id="929b6-117">客户端用户: %1 %r</span><span class="sxs-lookup"><span data-stu-id="929b6-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="929b6-118">重播文件目录: %2 %r</span><span class="sxs-lookup"><span data-stu-id="929b6-118">Replay Files Directory: %2%r</span></span><br /><br /> <span data-ttu-id="929b6-119">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="929b6-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="929b6-120">解释</span><span class="sxs-lookup"><span data-stu-id="929b6-120">Explanation</span></span>  
 <span data-ttu-id="929b6-121">此错误事件表示无法创建重播文件目录。</span><span class="sxs-lookup"><span data-stu-id="929b6-121">This Error event indicates that a replay files directory could not be created.</span></span>  

 <span data-ttu-id="929b6-122">SSO 服务从密码同步适配器接收密码更改，则这些模块存储在 SSO 数据库中。</span><span class="sxs-lookup"><span data-stu-id="929b6-122">When password changes are received by the SSO service from a password sync adapter, they are stored in the SSO database.</span></span> <span data-ttu-id="929b6-123">如果 SSO 数据库暂时不可用，密码更改存储在本地重播文件中。</span><span class="sxs-lookup"><span data-stu-id="929b6-123">If the SSO database is temporarily unavailable, the password changes are stored locally in replay files.</span></span> <span data-ttu-id="929b6-124">重播文件存储在重播文件目录。</span><span class="sxs-lookup"><span data-stu-id="929b6-124">Replay files are stored in the replay files directory.</span></span>  

## <a name="user-action"></a><span data-ttu-id="929b6-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="929b6-125">User Action</span></span>  
 <span data-ttu-id="929b6-126">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="929b6-126">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="929b6-127">检查重播文件目录，如果不存在，尝试手动与 SSO 服务使用相同的服务帐户创建它。</span><span class="sxs-lookup"><span data-stu-id="929b6-127">Check the replay files directory, if one does not exist, attempt to create it manually using the same service account as the SSO service.</span></span> <span data-ttu-id="929b6-128">如果无法创建重播文件目录使用与 SSO 服务相同的帐户，则检查该帐户的权限。</span><span class="sxs-lookup"><span data-stu-id="929b6-128">If you cannot create a replay files directory using the same account as the SSO service, check permissions for that account.</span></span>  

  <span data-ttu-id="929b6-129">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="929b6-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="929b6-130">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="929b6-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="929b6-131">密码同步</span><span class="sxs-lookup"><span data-stu-id="929b6-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
