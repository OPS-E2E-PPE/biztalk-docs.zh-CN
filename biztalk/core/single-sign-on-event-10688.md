---
title: 单一登录： 事件 10688 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63fe4ac5-dc1d-4d5a-8ce3-40ed4556afcf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0efe057472366b713b00573a36fa15c0b092ec2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975902"
---
# <a name="single-sign-on-event-10688"></a><span data-ttu-id="27abc-102">单一登录： 事件 10688</span><span class="sxs-lookup"><span data-stu-id="27abc-102">Single Sign-On: Event 10688</span></span>
## <a name="details"></a><span data-ttu-id="27abc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="27abc-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="27abc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="27abc-104">Product Name</span></span>   |                         <span data-ttu-id="27abc-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="27abc-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="27abc-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="27abc-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="27abc-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="27abc-107">Event ID</span></span>     |                                   <span data-ttu-id="27abc-108">10688</span><span class="sxs-lookup"><span data-stu-id="27abc-108">10688</span></span>                                   |
|  <span data-ttu-id="27abc-109">事件源</span><span class="sxs-lookup"><span data-stu-id="27abc-109">Event Source</span></span>   |                                  <span data-ttu-id="27abc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="27abc-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="27abc-111">组件</span><span class="sxs-lookup"><span data-stu-id="27abc-111">Component</span></span>    |                                    <span data-ttu-id="27abc-112">N\A</span><span class="sxs-lookup"><span data-stu-id="27abc-112">N\A</span></span>                                    |
|  <span data-ttu-id="27abc-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="27abc-113">Symbolic Name</span></span>  |                   <span data-ttu-id="27abc-114">SSO_ERROR_REPLAY_FILE_UNEXPECTED_DATA</span><span class="sxs-lookup"><span data-stu-id="27abc-114">SSO_ERROR_REPLAY_FILE_UNEXPECTED_DATA</span></span>                   |
|  <span data-ttu-id="27abc-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="27abc-115">Message Text</span></span>   | <span data-ttu-id="27abc-116">在重播 file.%r 中检测到损坏。</span><span class="sxs-lookup"><span data-stu-id="27abc-116">Corruption was detected in the replay file.%r</span></span><br /><br /> <span data-ttu-id="27abc-117">重播文件： %1</span><span class="sxs-lookup"><span data-stu-id="27abc-117">Replay File: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="27abc-118">解释</span><span class="sxs-lookup"><span data-stu-id="27abc-118">Explanation</span></span>  
 <span data-ttu-id="27abc-119">此错误事件表示 SSO 已重建与 SSO 数据库的联系，但无法读取重播文件由于损坏问题。</span><span class="sxs-lookup"><span data-stu-id="27abc-119">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="27abc-120">如果 SSO 无法打开重播文件，它将继续进行到下一个重播文件 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="27abc-120">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="27abc-121">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="27abc-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="27abc-122">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="27abc-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="27abc-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="27abc-123">User Action</span></span>  
 <span data-ttu-id="27abc-124">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="27abc-124">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="27abc-125">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="27abc-125">Check System and Application event logs for associated events.</span></span>  

- <span data-ttu-id="27abc-126">删除重播文件。</span><span class="sxs-lookup"><span data-stu-id="27abc-126">Delete the replay file.</span></span>  

  <span data-ttu-id="27abc-127">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="27abc-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="27abc-128">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="27abc-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="27abc-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="27abc-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
