---
title: 单一登录： 事件 10697 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4263ecbd-939e-4374-b0b6-aada3b2af900
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991d17351ddbaa998c0f7c90774e1615f3bc472e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980398"
---
# <a name="single-sign-on-event-10697"></a><span data-ttu-id="81e84-102">单一登录： 事件 10697</span><span class="sxs-lookup"><span data-stu-id="81e84-102">Single Sign-On: Event 10697</span></span>
## <a name="details"></a><span data-ttu-id="81e84-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="81e84-103">Details</span></span>  

|                 |                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="81e84-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="81e84-104">Product Name</span></span>   |                                           <span data-ttu-id="81e84-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="81e84-105">Enterprise Single Sign-On</span></span>                                           |
| <span data-ttu-id="81e84-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="81e84-106">Product Version</span></span> |                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                           |
|    <span data-ttu-id="81e84-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="81e84-107">Event ID</span></span>     |                                                     <span data-ttu-id="81e84-108">10697</span><span class="sxs-lookup"><span data-stu-id="81e84-108">10697</span></span>                                                     |
|  <span data-ttu-id="81e84-109">事件源</span><span class="sxs-lookup"><span data-stu-id="81e84-109">Event Source</span></span>   |                                                    <span data-ttu-id="81e84-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="81e84-110">ENTSSO</span></span>                                                     |
|    <span data-ttu-id="81e84-111">组件</span><span class="sxs-lookup"><span data-stu-id="81e84-111">Component</span></span>    |                                                      <span data-ttu-id="81e84-112">N\A</span><span class="sxs-lookup"><span data-stu-id="81e84-112">N\A</span></span>                                                      |
|  <span data-ttu-id="81e84-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="81e84-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="81e84-114">SSO_ERROR_PROGRESS_FILE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="81e84-114">SSO_ERROR_PROGRESS_FILE_MISMATCH</span></span>                                        |
|  <span data-ttu-id="81e84-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="81e84-115">Message Text</span></span>   | <span data-ttu-id="81e84-116">检测到进度文件已损坏。%r</span><span class="sxs-lookup"><span data-stu-id="81e84-116">Corruption was detected in the progress file.%r</span></span><br /><br /> <span data-ttu-id="81e84-117">重播文件: %1 %r</span><span class="sxs-lookup"><span data-stu-id="81e84-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="81e84-118">其他数据： %2</span><span class="sxs-lookup"><span data-stu-id="81e84-118">Additional Data: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="81e84-119">解释</span><span class="sxs-lookup"><span data-stu-id="81e84-119">Explanation</span></span>  
 <span data-ttu-id="81e84-120">此错误事件表示 SSO 已重建与 SSO 数据库的联系，但是无法打开该进程文件，因为与相应的重播文件不匹配。</span><span class="sxs-lookup"><span data-stu-id="81e84-120">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to open the progress file because of a mismatch with the corresponding replay file.</span></span> <span data-ttu-id="81e84-121">如果 SSO 无法打开进度文件，则将在第一个重播文件的开始记录处启动。</span><span class="sxs-lookup"><span data-stu-id="81e84-121">If SSO cannot open a progress file, it will start at the beginning record of the first replay file.</span></span>  

 <span data-ttu-id="81e84-122">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="81e84-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="81e84-123">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="81e84-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="81e84-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="81e84-124">User Action</span></span>  
 <span data-ttu-id="81e84-125">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81e84-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="81e84-126">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="81e84-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="81e84-127">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="81e84-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="81e84-128">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="81e84-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="81e84-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="81e84-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
