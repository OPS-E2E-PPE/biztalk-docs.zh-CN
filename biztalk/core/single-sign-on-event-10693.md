---
title: 单一登录：Event 10693 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 672bac7d-0ccc-4a42-a49d-57e387f4cf3a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cef53efa210d38d145dd4859fd3363e853a71fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397356"
---
# <a name="single-sign-on-event-10693"></a><span data-ttu-id="676cc-102">单一登录：事件 10693</span><span class="sxs-lookup"><span data-stu-id="676cc-102">Single Sign-On: Event 10693</span></span>
## <a name="details"></a><span data-ttu-id="676cc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="676cc-103">Details</span></span>  

|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="676cc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="676cc-104">Product Name</span></span>   |                                       <span data-ttu-id="676cc-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="676cc-105">Enterprise Single Sign-On</span></span>                                        |
| <span data-ttu-id="676cc-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="676cc-106">Product Version</span></span> |                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                       |
|    <span data-ttu-id="676cc-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="676cc-107">Event ID</span></span>     |                                                 <span data-ttu-id="676cc-108">10693</span><span class="sxs-lookup"><span data-stu-id="676cc-108">10693</span></span>                                                  |
|  <span data-ttu-id="676cc-109">事件源</span><span class="sxs-lookup"><span data-stu-id="676cc-109">Event Source</span></span>   |                                                 <span data-ttu-id="676cc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="676cc-110">ENTSSO</span></span>                                                 |
|    <span data-ttu-id="676cc-111">组件</span><span class="sxs-lookup"><span data-stu-id="676cc-111">Component</span></span>    |                                                  <span data-ttu-id="676cc-112">N\A</span><span class="sxs-lookup"><span data-stu-id="676cc-112">N\A</span></span>                                                   |
|  <span data-ttu-id="676cc-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="676cc-113">Symbolic Name</span></span>  |                                    <span data-ttu-id="676cc-114">SSO_WARNING_REPLAY_CANNOT_CREATE</span><span class="sxs-lookup"><span data-stu-id="676cc-114">SSO_WARNING_REPLAY_CANNOT_CREATE</span></span>                                    |
|  <span data-ttu-id="676cc-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="676cc-115">Message Text</span></span>   | <span data-ttu-id="676cc-116">无法创建重播文件或进度 file.%r</span><span class="sxs-lookup"><span data-stu-id="676cc-116">Could not create the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="676cc-117">文件名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="676cc-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="676cc-118">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="676cc-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="676cc-119">解释</span><span class="sxs-lookup"><span data-stu-id="676cc-119">Explanation</span></span>  
 <span data-ttu-id="676cc-120">此警告事件表示 SSO 无法与 SSO 数据库的连接丢失时创建重播和 \ 或进度文件。</span><span class="sxs-lookup"><span data-stu-id="676cc-120">This Warning event indicates that SSO was unable to create a replay and\or progress file when connection to the SSO database was lost.</span></span>  

 <span data-ttu-id="676cc-121">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="676cc-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="676cc-122">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="676cc-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="676cc-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="676cc-123">User Action</span></span>  
 <span data-ttu-id="676cc-124">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="676cc-124">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="676cc-125">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="676cc-125">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="676cc-126">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="676cc-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="676cc-127">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="676cc-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="676cc-128">密码同步</span><span class="sxs-lookup"><span data-stu-id="676cc-128">Password Synchronization</span></span>](../core/password-synchronization2.md)
