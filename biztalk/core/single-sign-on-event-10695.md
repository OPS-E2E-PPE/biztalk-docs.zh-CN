---
title: 单一登录： 事件 10695 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02c5dc1d-5626-4d24-ac4f-fcd2ae61cd98
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 742d4f802aed2b497a32b20b007c5bac489a8169
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010286"
---
# <a name="single-sign-on-event-10695"></a><span data-ttu-id="15f22-102">单一登录： 事件 10695</span><span class="sxs-lookup"><span data-stu-id="15f22-102">Single Sign-On: Event 10695</span></span>
## <a name="details"></a><span data-ttu-id="15f22-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="15f22-103">Details</span></span>  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="15f22-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="15f22-104">Product Name</span></span>   |                                                 <span data-ttu-id="15f22-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="15f22-105">Enterprise Single Sign-On</span></span>                                                 |
| <span data-ttu-id="15f22-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="15f22-106">Product Version</span></span> |                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                 |
|    <span data-ttu-id="15f22-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="15f22-107">Event ID</span></span>     |                                                           <span data-ttu-id="15f22-108">10695</span><span class="sxs-lookup"><span data-stu-id="15f22-108">10695</span></span>                                                           |
|  <span data-ttu-id="15f22-109">事件源</span><span class="sxs-lookup"><span data-stu-id="15f22-109">Event Source</span></span>   |                                                          <span data-ttu-id="15f22-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="15f22-110">ENTSSO</span></span>                                                           |
|    <span data-ttu-id="15f22-111">组件</span><span class="sxs-lookup"><span data-stu-id="15f22-111">Component</span></span>    |                                                            <span data-ttu-id="15f22-112">N\A</span><span class="sxs-lookup"><span data-stu-id="15f22-112">N\A</span></span>                                                            |
|  <span data-ttu-id="15f22-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="15f22-113">Symbolic Name</span></span>  |                                           <span data-ttu-id="15f22-114">SSO_ERROR_REPLAY_INCORRECT_FILE_NAME</span><span class="sxs-lookup"><span data-stu-id="15f22-114">SSO_ERROR_REPLAY_INCORRECT_FILE_NAME</span></span>                                            |
|  <span data-ttu-id="15f22-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="15f22-115">Message Text</span></span>   | <span data-ttu-id="15f22-116">在重播或进度 file.%r 中检测到损坏。</span><span class="sxs-lookup"><span data-stu-id="15f22-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="15f22-117">文件名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="15f22-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="15f22-118">解密文件的名称： %2</span><span class="sxs-lookup"><span data-stu-id="15f22-118">Decrypted File Name: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="15f22-119">解释</span><span class="sxs-lookup"><span data-stu-id="15f22-119">Explanation</span></span>  
 <span data-ttu-id="15f22-120">此错误事件表示 SSO 已重建与 SSO 数据库的联系，但无法读取重播文件由于损坏问题。</span><span class="sxs-lookup"><span data-stu-id="15f22-120">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="15f22-121">如果 SSO 无法打开重播文件，它将继续进行到下一个重播文件 （如果有）。</span><span class="sxs-lookup"><span data-stu-id="15f22-121">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="15f22-122">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="15f22-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="15f22-123">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="15f22-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="15f22-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="15f22-124">User Action</span></span>  
 <span data-ttu-id="15f22-125">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="15f22-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="15f22-126">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="15f22-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="15f22-127">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="15f22-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="15f22-128">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="15f22-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="15f22-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="15f22-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
