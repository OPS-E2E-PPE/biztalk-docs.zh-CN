---
title: 单一登录： 事件 10699 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff26533-e4d7-47b5-92d5-bd8c72fab89a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3802f04d2adf7d95a6ff10ae208acabbc1acf8ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983366"
---
# <a name="single-sign-on-event-10699"></a><span data-ttu-id="de432-102">单一登录： 事件 10699</span><span class="sxs-lookup"><span data-stu-id="de432-102">Single Sign-On: Event 10699</span></span>
## <a name="details"></a><span data-ttu-id="de432-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="de432-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="de432-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="de432-104">Product Name</span></span>   |                                                                                                       <span data-ttu-id="de432-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="de432-105">Enterprise Single Sign-On</span></span>                                                                                                       |
| <span data-ttu-id="de432-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="de432-106">Product Version</span></span> |                                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                       |
|    <span data-ttu-id="de432-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="de432-107">Event ID</span></span>     |                                                                                                                 <span data-ttu-id="de432-108">10699</span><span class="sxs-lookup"><span data-stu-id="de432-108">10699</span></span>                                                                                                                 |
|  <span data-ttu-id="de432-109">事件源</span><span class="sxs-lookup"><span data-stu-id="de432-109">Event Source</span></span>   |                                                                                                                <span data-ttu-id="de432-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="de432-110">ENTSSO</span></span>                                                                                                                 |
|    <span data-ttu-id="de432-111">组件</span><span class="sxs-lookup"><span data-stu-id="de432-111">Component</span></span>    |                                                                                                                  <span data-ttu-id="de432-112">N\A</span><span class="sxs-lookup"><span data-stu-id="de432-112">N\A</span></span>                                                                                                                  |
|  <span data-ttu-id="de432-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="de432-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="de432-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY</span><span class="sxs-lookup"><span data-stu-id="de432-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY</span></span>                                                                                           |
|  <span data-ttu-id="de432-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="de432-115">Message Text</span></span>   | <span data-ttu-id="de432-116">从适配器（从重播文件）接收到一个外部密码更改。%r</span><span class="sxs-lookup"><span data-stu-id="de432-116">An external password change was received from an adapter (from replay file).%r</span></span><br /><br /> <span data-ttu-id="de432-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="de432-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="de432-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="de432-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="de432-119">外部帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="de432-119">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="de432-120">客户端用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="de432-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="de432-121">记录号： %5</span><span class="sxs-lookup"><span data-stu-id="de432-121">Record Number: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="de432-122">解释</span><span class="sxs-lookup"><span data-stu-id="de432-122">Explanation</span></span>  
 <span data-ttu-id="de432-123">此信息性事件表示，从适配器接收到一个外部密码更改，此项更改记录在一个重播文件中。</span><span class="sxs-lookup"><span data-stu-id="de432-123">This Information event indicates that an external password change was received from an adapter that was recorded to a replay file.</span></span> <span data-ttu-id="de432-124">SSO 正在重播来自重播文件的已存储外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="de432-124">SSO is replaying the stored external password changes from the replay file.</span></span>  

 <span data-ttu-id="de432-125">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="de432-125">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="de432-126">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="de432-126">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="de432-127">用户操作</span><span class="sxs-lookup"><span data-stu-id="de432-127">User Action</span></span>  

- <span data-ttu-id="de432-128">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="de432-128">No user action is necessary.</span></span>  

  <span data-ttu-id="de432-129">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="de432-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="de432-130">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="de432-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="de432-131">密码同步</span><span class="sxs-lookup"><span data-stu-id="de432-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
