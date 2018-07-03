---
title: 单一登录： 事件 10741 |Microsoft Docs
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
ms.openlocfilehash: 1901ad4c58f3056b74f50fead72637bc9bb8b62e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006830"
---
# <a name="single-sign-on-event-10741"></a><span data-ttu-id="163c8-102">单一登录： 事件 10741</span><span class="sxs-lookup"><span data-stu-id="163c8-102">Single Sign-On: Event 10741</span></span>
## <a name="details"></a><span data-ttu-id="163c8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="163c8-103">Details</span></span>  

|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  <span data-ttu-id="163c8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="163c8-104">Product Name</span></span>   |                                 <span data-ttu-id="163c8-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="163c8-105">Enterprise Single Sign-On</span></span>                                 |
| <span data-ttu-id="163c8-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="163c8-106">Product Version</span></span> |                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    <span data-ttu-id="163c8-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="163c8-107">Event ID</span></span>     |                                           <span data-ttu-id="163c8-108">10741</span><span class="sxs-lookup"><span data-stu-id="163c8-108">10741</span></span>                                           |
|  <span data-ttu-id="163c8-109">事件源</span><span class="sxs-lookup"><span data-stu-id="163c8-109">Event Source</span></span>   |                                          <span data-ttu-id="163c8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="163c8-110">ENTSSO</span></span>                                           |
|    <span data-ttu-id="163c8-111">组件</span><span class="sxs-lookup"><span data-stu-id="163c8-111">Component</span></span>    |                                            <span data-ttu-id="163c8-112">N\A</span><span class="sxs-lookup"><span data-stu-id="163c8-112">N\A</span></span>                                            |
|  <span data-ttu-id="163c8-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="163c8-113">Symbolic Name</span></span>  |                                <span data-ttu-id="163c8-114">SSO_WARN_SAVING_REPLAY_FILE</span><span class="sxs-lookup"><span data-stu-id="163c8-114">SSO_WARN_SAVING_REPLAY_FILE</span></span>                                |
|  <span data-ttu-id="163c8-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="163c8-115">Message Text</span></span>   | <span data-ttu-id="163c8-116">正在保存重播文件或进度文件。%r</span><span class="sxs-lookup"><span data-stu-id="163c8-116">Saving replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="163c8-117">保存的文件: %1 %r</span><span class="sxs-lookup"><span data-stu-id="163c8-117">Saved File: %1%r</span></span><br /><br /> <span data-ttu-id="163c8-118">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="163c8-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="163c8-119">解释</span><span class="sxs-lookup"><span data-stu-id="163c8-119">Explanation</span></span>  
 <span data-ttu-id="163c8-120">此警告事件表明 SSO 正在保存重播文件或进度文件。</span><span class="sxs-lookup"><span data-stu-id="163c8-120">This Warning event indicates that SSO is saving a replay or progress file.</span></span>  

 <span data-ttu-id="163c8-121">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="163c8-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="163c8-122">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="163c8-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="163c8-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="163c8-123">User Action</span></span>  

- <span data-ttu-id="163c8-124">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="163c8-124">No user action is necessary.</span></span>  

  <span data-ttu-id="163c8-125">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="163c8-125">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="163c8-126">密码同步</span><span class="sxs-lookup"><span data-stu-id="163c8-126">Password Synchronization</span></span>](../core/password-synchronization2.md)
