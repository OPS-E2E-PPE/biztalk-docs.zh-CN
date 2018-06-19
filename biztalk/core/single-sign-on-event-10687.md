---
title: 单一登录： 事件 10687 |Microsoft 文档
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
ms.openlocfilehash: 368e9bbad42e49ebd71bc1a581b0fb18bbcc2d5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270509"
---
# <a name="single-sign-on-event-10687"></a><span data-ttu-id="b8734-102">单一登录： 事件 10687</span><span class="sxs-lookup"><span data-stu-id="b8734-102">Single Sign-On: Event 10687</span></span>
## <a name="details"></a><span data-ttu-id="b8734-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b8734-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8734-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b8734-104">Product Name</span></span>|<span data-ttu-id="b8734-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b8734-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="b8734-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b8734-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="b8734-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b8734-107">Event ID</span></span>|<span data-ttu-id="b8734-108">10687</span><span class="sxs-lookup"><span data-stu-id="b8734-108">10687</span></span>|  
|<span data-ttu-id="b8734-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b8734-109">Event Source</span></span>|<span data-ttu-id="b8734-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b8734-110">ENTSSO</span></span>|  
|<span data-ttu-id="b8734-111">组件</span><span class="sxs-lookup"><span data-stu-id="b8734-111">Component</span></span>|<span data-ttu-id="b8734-112">N\A</span><span class="sxs-lookup"><span data-stu-id="b8734-112">N\A</span></span>|  
|<span data-ttu-id="b8734-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b8734-113">Symbolic Name</span></span>|<span data-ttu-id="b8734-114">SSO_INFO_REPLAY_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="b8734-114">SSO_INFO_REPLAY_COMPLETE</span></span>|  
|<span data-ttu-id="b8734-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b8734-115">Message Text</span></span>|<span data-ttu-id="b8734-116">重播存储的外部密码更改已完成。%r</span><span class="sxs-lookup"><span data-stu-id="b8734-116">Replay of stored external password changes completed.%r</span></span><br /><br /> <span data-ttu-id="b8734-117">重播文件: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b8734-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="b8734-118">其他数据： %2</span><span class="sxs-lookup"><span data-stu-id="b8734-118">Additional Data: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b8734-119">解释</span><span class="sxs-lookup"><span data-stu-id="b8734-119">Explanation</span></span>  
 <span data-ttu-id="b8734-120">此信息事件表示 SSO 已完成重播存储的外部密码更改文件。</span><span class="sxs-lookup"><span data-stu-id="b8734-120">This Information event indicates that SSO has completed replaying the stored external password changes file.</span></span> <span data-ttu-id="b8734-121">ENTSSO server 无法与 SSO 数据库取得联系时，密码同步将使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="b8734-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b8734-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="b8734-122">User Action</span></span>  
  
-   <span data-ttu-id="b8734-123">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="b8734-123">No user action is necessary.</span></span>  
  
 <span data-ttu-id="b8734-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="b8734-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="b8734-125">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="b8734-125">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="b8734-126">密码同步</span><span class="sxs-lookup"><span data-stu-id="b8734-126">Password Synchronization</span></span>](../core/password-synchronization2.md)