---
title: 单一登录：Event 10685 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 810b37b5-51c4-4201-8d88-0bf7d9e16dae
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f73b44e334c60a59211b59a46f5c9a2dacffa8ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397401"
---
# <a name="single-sign-on-event-10685"></a><span data-ttu-id="5a1c1-102">单一登录：事件 10685</span><span class="sxs-lookup"><span data-stu-id="5a1c1-102">Single Sign-On: Event 10685</span></span>
## <a name="details"></a><span data-ttu-id="5a1c1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5a1c1-103">Details</span></span>  

|                 |                                                                                                      |
|-----------------|------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5a1c1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5a1c1-104">Product Name</span></span>   |                                      <span data-ttu-id="5a1c1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5a1c1-105">Enterprise Single Sign-On</span></span>                                       |
| <span data-ttu-id="5a1c1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5a1c1-106">Product Version</span></span> |                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                      |
|    <span data-ttu-id="5a1c1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5a1c1-107">Event ID</span></span>     |                                                <span data-ttu-id="5a1c1-108">10685</span><span class="sxs-lookup"><span data-stu-id="5a1c1-108">10685</span></span>                                                 |
|  <span data-ttu-id="5a1c1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5a1c1-109">Event Source</span></span>   |                                                <span data-ttu-id="5a1c1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5a1c1-110">ENTSSO</span></span>                                                |
|    <span data-ttu-id="5a1c1-111">组件</span><span class="sxs-lookup"><span data-stu-id="5a1c1-111">Component</span></span>    |                                                 <span data-ttu-id="5a1c1-112">N\A</span><span class="sxs-lookup"><span data-stu-id="5a1c1-112">N\A</span></span>                                                  |
|  <span data-ttu-id="5a1c1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5a1c1-113">Symbolic Name</span></span>  |                                     <span data-ttu-id="5a1c1-114">SSO_WARN_REPLAY_CANNOT_OPEN</span><span class="sxs-lookup"><span data-stu-id="5a1c1-114">SSO_WARN_REPLAY_CANNOT_OPEN</span></span>                                      |
|  <span data-ttu-id="5a1c1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5a1c1-115">Message Text</span></span>   | <span data-ttu-id="5a1c1-116">无法打开重播文件或进度 file.%r</span><span class="sxs-lookup"><span data-stu-id="5a1c1-116">Could not open the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="5a1c1-117">文件名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5a1c1-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="5a1c1-118">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="5a1c1-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="5a1c1-119">解释</span><span class="sxs-lookup"><span data-stu-id="5a1c1-119">Explanation</span></span>  
 <span data-ttu-id="5a1c1-120">此警告事件表明 SSO 已重建与 SSO 数据库的联系，但无法打开重播或进度文件。</span><span class="sxs-lookup"><span data-stu-id="5a1c1-120">This Warning event indicates that SSO has re-established contact with the SSO database, but was unable to open the replay or progress file.</span></span> <span data-ttu-id="5a1c1-121">如果 SSO 无法打开重播文件，它将继续进行到下一个重播文件。</span><span class="sxs-lookup"><span data-stu-id="5a1c1-121">If SSO cannot open a replay file, it will proceed to the next replay file.</span></span>  

 <span data-ttu-id="5a1c1-122">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="5a1c1-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="5a1c1-123">进度文件指示距离通过 SSO 能够读取与 SSO 数据库的重播文件中用例联系人愉悦再次通过播放重播文件。</span><span class="sxs-lookup"><span data-stu-id="5a1c1-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is lost again part-way through playing back of a replay file.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5a1c1-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="5a1c1-124">User Action</span></span>  
 <span data-ttu-id="5a1c1-125">若要解决此警告事件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5a1c1-125">To resolve this Warning event, do the following:</span></span>  

- <span data-ttu-id="5a1c1-126">应检查相关事件，以确定为何 SSO 无法与 SSO 数据库联系的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="5a1c1-126">You should check the System and Application Event logs for associated events to determine why SSO was unable to contact the SSO database.</span></span>  

  <span data-ttu-id="5a1c1-127">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="5a1c1-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="5a1c1-128">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="5a1c1-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="5a1c1-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="5a1c1-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
