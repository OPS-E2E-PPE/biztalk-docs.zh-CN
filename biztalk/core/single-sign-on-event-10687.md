---
title: 单一登录：Event 10687 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b3fe2c-a7ba-47e1-a753-4eaa64b01a60
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77412a149c79e508c03b245cba04a76c87542936
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397393"
---
# <a name="single-sign-on-event-10687"></a><span data-ttu-id="864f9-102">单一登录：事件 10687</span><span class="sxs-lookup"><span data-stu-id="864f9-102">Single Sign-On: Event 10687</span></span>
## <a name="details"></a><span data-ttu-id="864f9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="864f9-103">Details</span></span>  

|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="864f9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="864f9-104">Product Name</span></span>   |                                               <span data-ttu-id="864f9-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="864f9-105">Enterprise Single Sign-On</span></span>                                               |
| <span data-ttu-id="864f9-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="864f9-106">Product Version</span></span> |                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    <span data-ttu-id="864f9-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="864f9-107">Event ID</span></span>     |                                                         <span data-ttu-id="864f9-108">10687</span><span class="sxs-lookup"><span data-stu-id="864f9-108">10687</span></span>                                                         |
|  <span data-ttu-id="864f9-109">事件源</span><span class="sxs-lookup"><span data-stu-id="864f9-109">Event Source</span></span>   |                                                        <span data-ttu-id="864f9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="864f9-110">ENTSSO</span></span>                                                         |
|    <span data-ttu-id="864f9-111">组件</span><span class="sxs-lookup"><span data-stu-id="864f9-111">Component</span></span>    |                                                          <span data-ttu-id="864f9-112">N\A</span><span class="sxs-lookup"><span data-stu-id="864f9-112">N\A</span></span>                                                          |
|  <span data-ttu-id="864f9-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="864f9-113">Symbolic Name</span></span>  |                                               <span data-ttu-id="864f9-114">SSO_INFO_REPLAY_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="864f9-114">SSO_INFO_REPLAY_COMPLETE</span></span>                                                |
|  <span data-ttu-id="864f9-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="864f9-115">Message Text</span></span>   | <span data-ttu-id="864f9-116">重播存储的外部密码更改 completed.%r</span><span class="sxs-lookup"><span data-stu-id="864f9-116">Replay of stored external password changes completed.%r</span></span><br /><br /> <span data-ttu-id="864f9-117">重播文件: %1 %r</span><span class="sxs-lookup"><span data-stu-id="864f9-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="864f9-118">其他数据： %2</span><span class="sxs-lookup"><span data-stu-id="864f9-118">Additional Data: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="864f9-119">解释</span><span class="sxs-lookup"><span data-stu-id="864f9-119">Explanation</span></span>  
 <span data-ttu-id="864f9-120">此信息事件表明 SSO 已完成重播存储的外部密码更改文件。</span><span class="sxs-lookup"><span data-stu-id="864f9-120">This Information event indicates that SSO has completed replaying the stored external password changes file.</span></span> <span data-ttu-id="864f9-121">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="864f9-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="864f9-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="864f9-122">User Action</span></span>  

- <span data-ttu-id="864f9-123">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="864f9-123">No user action is necessary.</span></span>  

  <span data-ttu-id="864f9-124">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="864f9-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="864f9-125">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="864f9-125">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="864f9-126">密码同步</span><span class="sxs-lookup"><span data-stu-id="864f9-126">Password Synchronization</span></span>](../core/password-synchronization2.md)
