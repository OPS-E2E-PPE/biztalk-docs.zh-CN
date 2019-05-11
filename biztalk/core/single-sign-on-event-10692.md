---
title: 单一登录：Event 10692 | Microsoft Docs
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
ms.openlocfilehash: fdfd3359baec8f4dbecaaafc6acd0e614956ffcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397354"
---
# <a name="single-sign-on-event-10692"></a><span data-ttu-id="b1005-102">单一登录：事件 10692</span><span class="sxs-lookup"><span data-stu-id="b1005-102">Single Sign-On: Event 10692</span></span>
## <a name="details"></a><span data-ttu-id="b1005-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b1005-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b1005-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b1005-104">Product Name</span></span>   |                                                                                                                      <span data-ttu-id="b1005-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b1005-105">Enterprise Single Sign-On</span></span>                                                                                                                      |
| <span data-ttu-id="b1005-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b1005-106">Product Version</span></span> |                                                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                      |
|    <span data-ttu-id="b1005-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b1005-107">Event ID</span></span>     |                                                                                                                                <span data-ttu-id="b1005-108">10692</span><span class="sxs-lookup"><span data-stu-id="b1005-108">10692</span></span>                                                                                                                                |
|  <span data-ttu-id="b1005-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b1005-109">Event Source</span></span>   |                                                                                                                               <span data-ttu-id="b1005-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b1005-110">ENTSSO</span></span>                                                                                                                                |
|    <span data-ttu-id="b1005-111">组件</span><span class="sxs-lookup"><span data-stu-id="b1005-111">Component</span></span>    |                                                                                                                                 <span data-ttu-id="b1005-112">N\A</span><span class="sxs-lookup"><span data-stu-id="b1005-112">N\A</span></span>                                                                                                                                 |
|  <span data-ttu-id="b1005-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b1005-113">Symbolic Name</span></span>  |                                                                                                                    <span data-ttu-id="b1005-114">SSO_WARN_REPLAY_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="b1005-114">SSO_WARN_REPLAY_ACCESS_DENIED</span></span>                                                                                                                    |
|  <span data-ttu-id="b1005-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b1005-115">Message Text</span></span>   | <span data-ttu-id="b1005-116">无法重播外部密码更改，因为原始调用方不再是 adapter.%r 访问帐户的成员</span><span class="sxs-lookup"><span data-stu-id="b1005-116">The external password change cannot be replayed because the original caller is no longer a member of the access account for the adapter.%r</span></span><br /><br /> <span data-ttu-id="b1005-117">重播文件: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b1005-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="b1005-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="b1005-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="b1005-119">原始调用方: %3 %r</span><span class="sxs-lookup"><span data-stu-id="b1005-119">Original Caller: %3%r</span></span><br /><br /> <span data-ttu-id="b1005-120">访问帐户： %4</span><span class="sxs-lookup"><span data-stu-id="b1005-120">Access Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="b1005-121">解释</span><span class="sxs-lookup"><span data-stu-id="b1005-121">Explanation</span></span>  
 <span data-ttu-id="b1005-122">此警告事件表明 SSO 已重建与 SSO 数据库的联系，但无法进行更改 （在 SSO 数据库中） 中指定重播文件由于最初指定该更改的帐户将不再有效。</span><span class="sxs-lookup"><span data-stu-id="b1005-122">This Warning event indicates that SSO has re-established contact with the SSO database, but was unable to make a change (in the SSO database) specified in the replay file because the account that originally specified the change is no longer valid.</span></span>  

 <span data-ttu-id="b1005-123">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="b1005-123">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="b1005-124">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="b1005-124">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="b1005-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="b1005-125">User Action</span></span>  
 <span data-ttu-id="b1005-126">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b1005-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="b1005-127">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="b1005-127">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="b1005-128">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="b1005-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="b1005-129">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="b1005-129">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="b1005-130">密码同步</span><span class="sxs-lookup"><span data-stu-id="b1005-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
