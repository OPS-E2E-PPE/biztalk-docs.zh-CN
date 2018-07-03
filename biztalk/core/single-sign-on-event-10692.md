---
title: 单一登录： 事件 10692 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78a476ca-32eb-4f37-a807-25850503db6e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37148a774504599b99665b57691316c35d0783bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987278"
---
# <a name="single-sign-on-event-10692"></a><span data-ttu-id="7786e-102">单一登录： 事件 10692</span><span class="sxs-lookup"><span data-stu-id="7786e-102">Single Sign-On: Event 10692</span></span>
## <a name="details"></a><span data-ttu-id="7786e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7786e-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7786e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7786e-104">Product Name</span></span>   |                                                                                                                      <span data-ttu-id="7786e-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7786e-105">Enterprise Single Sign-On</span></span>                                                                                                                      |
| <span data-ttu-id="7786e-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="7786e-106">Product Version</span></span> |                                                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                      |
|    <span data-ttu-id="7786e-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7786e-107">Event ID</span></span>     |                                                                                                                                <span data-ttu-id="7786e-108">10692</span><span class="sxs-lookup"><span data-stu-id="7786e-108">10692</span></span>                                                                                                                                |
|  <span data-ttu-id="7786e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7786e-109">Event Source</span></span>   |                                                                                                                               <span data-ttu-id="7786e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7786e-110">ENTSSO</span></span>                                                                                                                                |
|    <span data-ttu-id="7786e-111">组件</span><span class="sxs-lookup"><span data-stu-id="7786e-111">Component</span></span>    |                                                                                                                                 <span data-ttu-id="7786e-112">N\A</span><span class="sxs-lookup"><span data-stu-id="7786e-112">N\A</span></span>                                                                                                                                 |
|  <span data-ttu-id="7786e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7786e-113">Symbolic Name</span></span>  |                                                                                                                    <span data-ttu-id="7786e-114">SSO_WARN_REPLAY_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="7786e-114">SSO_WARN_REPLAY_ACCESS_DENIED</span></span>                                                                                                                    |
|  <span data-ttu-id="7786e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7786e-115">Message Text</span></span>   | <span data-ttu-id="7786e-116">无法重播外部密码更改，因为原始调用方不再是适配器访问帐户的成员。%r</span><span class="sxs-lookup"><span data-stu-id="7786e-116">The external password change cannot be replayed because the original caller is no longer a member of the access account for the adapter.%r</span></span><br /><br /> <span data-ttu-id="7786e-117">重播文件: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7786e-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="7786e-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7786e-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="7786e-119">原始调用方: %3 %r</span><span class="sxs-lookup"><span data-stu-id="7786e-119">Original Caller: %3%r</span></span><br /><br /> <span data-ttu-id="7786e-120">访问帐户： %4</span><span class="sxs-lookup"><span data-stu-id="7786e-120">Access Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="7786e-121">解释</span><span class="sxs-lookup"><span data-stu-id="7786e-121">Explanation</span></span>  
 <span data-ttu-id="7786e-122">此警告事件表明，SSO 已与 SSO 数据库重新建立了联系，但无法（在 SSO 数据库中）作出重播文件中指定的更改，因为最初指定该更改的帐户不再有效。</span><span class="sxs-lookup"><span data-stu-id="7786e-122">This Warning event indicates that SSO has re-established contact with the SSO database, but was unable to make a change (in the SSO database) specified in the replay file because the account that originally specified the change is no longer valid.</span></span>  

 <span data-ttu-id="7786e-123">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="7786e-123">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="7786e-124">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="7786e-124">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7786e-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="7786e-125">User Action</span></span>  
 <span data-ttu-id="7786e-126">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7786e-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="7786e-127">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="7786e-127">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="7786e-128">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="7786e-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="7786e-129">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="7786e-129">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="7786e-130">密码同步</span><span class="sxs-lookup"><span data-stu-id="7786e-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
