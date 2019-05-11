---
title: 单一登录：事件 10741 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58b6b093-d136-498f-a3b5-c413150da956
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2150f33b90137d5f5e1258a829901426a45d7856
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291737"
---
# <a name="single-sign-on-event-10741"></a><span data-ttu-id="5a67c-102">单一登录：事件 10741</span><span class="sxs-lookup"><span data-stu-id="5a67c-102">Single Sign-On: Event 10741</span></span>
## <a name="details"></a><span data-ttu-id="5a67c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5a67c-103">Details</span></span>  

|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5a67c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5a67c-104">Product Name</span></span>   |                                 <span data-ttu-id="5a67c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5a67c-105">Enterprise Single Sign-On</span></span>                                 |
| <span data-ttu-id="5a67c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5a67c-106">Product Version</span></span> |                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    <span data-ttu-id="5a67c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5a67c-107">Event ID</span></span>     |                                           <span data-ttu-id="5a67c-108">10741</span><span class="sxs-lookup"><span data-stu-id="5a67c-108">10741</span></span>                                           |
|  <span data-ttu-id="5a67c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5a67c-109">Event Source</span></span>   |                                          <span data-ttu-id="5a67c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5a67c-110">ENTSSO</span></span>                                           |
|    <span data-ttu-id="5a67c-111">组件</span><span class="sxs-lookup"><span data-stu-id="5a67c-111">Component</span></span>    |                                            <span data-ttu-id="5a67c-112">N\A</span><span class="sxs-lookup"><span data-stu-id="5a67c-112">N\A</span></span>                                            |
|  <span data-ttu-id="5a67c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5a67c-113">Symbolic Name</span></span>  |                                <span data-ttu-id="5a67c-114">SSO_WARN_SAVING_REPLAY_FILE</span><span class="sxs-lookup"><span data-stu-id="5a67c-114">SSO_WARN_SAVING_REPLAY_FILE</span></span>                                |
|  <span data-ttu-id="5a67c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5a67c-115">Message Text</span></span>   | <span data-ttu-id="5a67c-116">正在保存重播或进度 file.%r</span><span class="sxs-lookup"><span data-stu-id="5a67c-116">Saving replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="5a67c-117">保存的文件: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5a67c-117">Saved File: %1%r</span></span><br /><br /> <span data-ttu-id="5a67c-118">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="5a67c-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="5a67c-119">解释</span><span class="sxs-lookup"><span data-stu-id="5a67c-119">Explanation</span></span>  
 <span data-ttu-id="5a67c-120">此警告事件表明 SSO 正在保存重播或进度文件。</span><span class="sxs-lookup"><span data-stu-id="5a67c-120">This Warning event indicates that SSO is saving a replay or progress file.</span></span>  

 <span data-ttu-id="5a67c-121">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="5a67c-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="5a67c-122">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="5a67c-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5a67c-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="5a67c-123">User Action</span></span>  

- <span data-ttu-id="5a67c-124">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="5a67c-124">No user action is necessary.</span></span>  

  <span data-ttu-id="5a67c-125">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="5a67c-125">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="5a67c-126">密码同步</span><span class="sxs-lookup"><span data-stu-id="5a67c-126">Password Synchronization</span></span>](../core/password-synchronization2.md)
