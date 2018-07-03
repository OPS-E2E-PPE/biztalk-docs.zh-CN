---
title: 单一登录： 事件 10693 |Microsoft Docs
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
ms.openlocfilehash: 8f9dd254fd81d54f0c60a2ea8b0a143e94ddd516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009478"
---
# <a name="single-sign-on-event-10693"></a><span data-ttu-id="13e62-102">单一登录： 事件 10693</span><span class="sxs-lookup"><span data-stu-id="13e62-102">Single Sign-On: Event 10693</span></span>
## <a name="details"></a><span data-ttu-id="13e62-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="13e62-103">Details</span></span>  

|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="13e62-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="13e62-104">Product Name</span></span>   |                                       <span data-ttu-id="13e62-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="13e62-105">Enterprise Single Sign-On</span></span>                                        |
| <span data-ttu-id="13e62-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="13e62-106">Product Version</span></span> |                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                       |
|    <span data-ttu-id="13e62-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="13e62-107">Event ID</span></span>     |                                                 <span data-ttu-id="13e62-108">10693</span><span class="sxs-lookup"><span data-stu-id="13e62-108">10693</span></span>                                                  |
|  <span data-ttu-id="13e62-109">事件源</span><span class="sxs-lookup"><span data-stu-id="13e62-109">Event Source</span></span>   |                                                 <span data-ttu-id="13e62-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="13e62-110">ENTSSO</span></span>                                                 |
|    <span data-ttu-id="13e62-111">组件</span><span class="sxs-lookup"><span data-stu-id="13e62-111">Component</span></span>    |                                                  <span data-ttu-id="13e62-112">N\A</span><span class="sxs-lookup"><span data-stu-id="13e62-112">N\A</span></span>                                                   |
|  <span data-ttu-id="13e62-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="13e62-113">Symbolic Name</span></span>  |                                    <span data-ttu-id="13e62-114">SSO_WARNING_REPLAY_CANNOT_CREATE</span><span class="sxs-lookup"><span data-stu-id="13e62-114">SSO_WARNING_REPLAY_CANNOT_CREATE</span></span>                                    |
|  <span data-ttu-id="13e62-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="13e62-115">Message Text</span></span>   | <span data-ttu-id="13e62-116">无法创建重播文件或进度文件。%r</span><span class="sxs-lookup"><span data-stu-id="13e62-116">Could not create the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="13e62-117">文件名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="13e62-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="13e62-118">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="13e62-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="13e62-119">解释</span><span class="sxs-lookup"><span data-stu-id="13e62-119">Explanation</span></span>  
 <span data-ttu-id="13e62-120">此警告事件表明到 SSO 数据库的连接丢失时 SSO 无法创建重播文件和\或进度文件。</span><span class="sxs-lookup"><span data-stu-id="13e62-120">This Warning event indicates that SSO was unable to create a replay and\or progress file when connection to the SSO database was lost.</span></span>  

 <span data-ttu-id="13e62-121">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="13e62-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="13e62-122">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="13e62-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="13e62-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="13e62-123">User Action</span></span>  
 <span data-ttu-id="13e62-124">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="13e62-124">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="13e62-125">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="13e62-125">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="13e62-126">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="13e62-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="13e62-127">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="13e62-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="13e62-128">密码同步</span><span class="sxs-lookup"><span data-stu-id="13e62-128">Password Synchronization</span></span>](../core/password-synchronization2.md)
