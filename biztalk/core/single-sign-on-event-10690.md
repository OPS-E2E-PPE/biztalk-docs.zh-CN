---
title: 单一登录： 事件 10690 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0998f8dc-47de-4dc3-8905-3844177a7c54
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bab02c03fc93560fa881f46decfaa9a10ff9950
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015142"
---
# <a name="single-sign-on-event-10690"></a><span data-ttu-id="584a2-102">单一登录： 事件 10690</span><span class="sxs-lookup"><span data-stu-id="584a2-102">Single Sign-On: Event 10690</span></span>
## <a name="details"></a><span data-ttu-id="584a2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="584a2-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="584a2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="584a2-104">Product Name</span></span>   |                         <span data-ttu-id="584a2-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="584a2-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="584a2-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="584a2-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="584a2-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="584a2-107">Event ID</span></span>     |                                   <span data-ttu-id="584a2-108">10690</span><span class="sxs-lookup"><span data-stu-id="584a2-108">10690</span></span>                                   |
|  <span data-ttu-id="584a2-109">事件源</span><span class="sxs-lookup"><span data-stu-id="584a2-109">Event Source</span></span>   |                                  <span data-ttu-id="584a2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="584a2-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="584a2-111">组件</span><span class="sxs-lookup"><span data-stu-id="584a2-111">Component</span></span>    |                                    <span data-ttu-id="584a2-112">N\A</span><span class="sxs-lookup"><span data-stu-id="584a2-112">N\A</span></span>                                    |
|  <span data-ttu-id="584a2-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="584a2-113">Symbolic Name</span></span>  |                 <span data-ttu-id="584a2-114">SSO_ERROR_REPLAY_INCORRECT_RECORD_NUMBER</span><span class="sxs-lookup"><span data-stu-id="584a2-114">SSO_ERROR_REPLAY_INCORRECT_RECORD_NUMBER</span></span>                  |
|  <span data-ttu-id="584a2-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="584a2-115">Message Text</span></span>   | <span data-ttu-id="584a2-116">在重播 file.%r 中检测到损坏。</span><span class="sxs-lookup"><span data-stu-id="584a2-116">Corruption was detected in the replay file.%r</span></span><br /><br /> <span data-ttu-id="584a2-117">重播文件： %1</span><span class="sxs-lookup"><span data-stu-id="584a2-117">Replay File: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="584a2-118">解释</span><span class="sxs-lookup"><span data-stu-id="584a2-118">Explanation</span></span>  
 <span data-ttu-id="584a2-119">此错误事件表示 SSO 已重建与 SSO 数据库的联系，但无法读取重播文件由于损坏问题。</span><span class="sxs-lookup"><span data-stu-id="584a2-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="584a2-120">如果 SSO 无法打开重播文件，它将继续进行到下一个重播文件 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="584a2-120">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="584a2-121">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="584a2-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="584a2-122">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="584a2-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="584a2-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="584a2-123">User Action</span></span>  
 <span data-ttu-id="584a2-124">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="584a2-124">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="584a2-125">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="584a2-125">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="584a2-126">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="584a2-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="584a2-127">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="584a2-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="584a2-128">密码同步</span><span class="sxs-lookup"><span data-stu-id="584a2-128">Password Synchronization</span></span>](../core/password-synchronization2.md)
