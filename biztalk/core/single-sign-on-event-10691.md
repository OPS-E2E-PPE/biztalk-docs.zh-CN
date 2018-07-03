---
title: 单一登录： 事件 10691 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fcefb49-c068-41e9-850d-99864c0899bf
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69acc99acd002f23d3d6e02430d58fb88f9651a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009894"
---
# <a name="single-sign-on-event-10691"></a><span data-ttu-id="b0057-102">单一登录： 事件 10691</span><span class="sxs-lookup"><span data-stu-id="b0057-102">Single Sign-On: Event 10691</span></span>
## <a name="details"></a><span data-ttu-id="b0057-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b0057-103">Details</span></span>  

|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b0057-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b0057-104">Product Name</span></span>   |                                          <span data-ttu-id="b0057-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b0057-105">Enterprise Single Sign-On</span></span>                                          |
| <span data-ttu-id="b0057-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b0057-106">Product Version</span></span> |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                          |
|    <span data-ttu-id="b0057-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b0057-107">Event ID</span></span>     |                                                    <span data-ttu-id="b0057-108">10691</span><span class="sxs-lookup"><span data-stu-id="b0057-108">10691</span></span>                                                    |
|  <span data-ttu-id="b0057-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b0057-109">Event Source</span></span>   |                                                   <span data-ttu-id="b0057-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b0057-110">ENTSSO</span></span>                                                    |
|    <span data-ttu-id="b0057-111">组件</span><span class="sxs-lookup"><span data-stu-id="b0057-111">Component</span></span>    |                                                     <span data-ttu-id="b0057-112">N\A</span><span class="sxs-lookup"><span data-stu-id="b0057-112">N\A</span></span>                                                     |
|  <span data-ttu-id="b0057-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b0057-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="b0057-114">SSO_ERROR_REPLAY_FILE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="b0057-114">SSO_ERROR_REPLAY_FILE_MISMATCH</span></span>                                        |
|  <span data-ttu-id="b0057-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b0057-115">Message Text</span></span>   | <span data-ttu-id="b0057-116">在重播 file.%r 中检测到损坏。</span><span class="sxs-lookup"><span data-stu-id="b0057-116">Corruption was detected in the replay file.%r</span></span><br /><br /> <span data-ttu-id="b0057-117">重播文件: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b0057-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="b0057-118">其他数据： %2</span><span class="sxs-lookup"><span data-stu-id="b0057-118">Additional Data: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="b0057-119">解释</span><span class="sxs-lookup"><span data-stu-id="b0057-119">Explanation</span></span>  
 <span data-ttu-id="b0057-120">此错误事件表示 SSO 已重建与 SSO 数据库的联系，但不能与相应的进度文件中打开重播文件由于不匹配。</span><span class="sxs-lookup"><span data-stu-id="b0057-120">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to open the replay file because of a mismatch with the corresponding progress file.</span></span> <span data-ttu-id="b0057-121">如果 SSO 无法打开重播文件，它将继续进行到下一个重播文件 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="b0057-121">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="b0057-122">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="b0057-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="b0057-123">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="b0057-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="b0057-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="b0057-124">User Action</span></span>  
 <span data-ttu-id="b0057-125">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b0057-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="b0057-126">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="b0057-126">Check System and Application event logs for associated events.</span></span>  

- <span data-ttu-id="b0057-127">删除重播文件。</span><span class="sxs-lookup"><span data-stu-id="b0057-127">Delete the replay file.</span></span>  

  <span data-ttu-id="b0057-128">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="b0057-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="b0057-129">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="b0057-129">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="b0057-130">密码同步</span><span class="sxs-lookup"><span data-stu-id="b0057-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
