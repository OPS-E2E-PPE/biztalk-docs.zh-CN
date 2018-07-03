---
title: 单一登录： 事件 10698 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f467934d-fef5-4962-a341-18f272d84108
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aacd272480ddb58de38960ae8dc1a744815ced64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966470"
---
# <a name="single-sign-on-event-10698"></a><span data-ttu-id="b58c8-102">单一登录： 事件 10698</span><span class="sxs-lookup"><span data-stu-id="b58c8-102">Single Sign-On: Event 10698</span></span>
## <a name="details"></a><span data-ttu-id="b58c8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b58c8-103">Details</span></span>  

|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  <span data-ttu-id="b58c8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b58c8-104">Product Name</span></span>   |                      <span data-ttu-id="b58c8-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b58c8-105">Enterprise Single Sign-On</span></span>                       |
| <span data-ttu-id="b58c8-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b58c8-106">Product Version</span></span> |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    <span data-ttu-id="b58c8-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b58c8-107">Event ID</span></span>     |                                <span data-ttu-id="b58c8-108">10698</span><span class="sxs-lookup"><span data-stu-id="b58c8-108">10698</span></span>                                 |
|  <span data-ttu-id="b58c8-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b58c8-109">Event Source</span></span>   |                                <span data-ttu-id="b58c8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b58c8-110">ENTSSO</span></span>                                |
|    <span data-ttu-id="b58c8-111">组件</span><span class="sxs-lookup"><span data-stu-id="b58c8-111">Component</span></span>    |                                 <span data-ttu-id="b58c8-112">N\A</span><span class="sxs-lookup"><span data-stu-id="b58c8-112">N\A</span></span>                                  |
|  <span data-ttu-id="b58c8-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b58c8-113">Symbolic Name</span></span>  |                     <span data-ttu-id="b58c8-114">SSO_INFO_REPLAY_FILE_DELETED</span><span class="sxs-lookup"><span data-stu-id="b58c8-114">SSO_INFO_REPLAY_FILE_DELETED</span></span>                     |
|  <span data-ttu-id="b58c8-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b58c8-115">Message Text</span></span>   | <span data-ttu-id="b58c8-116">重播或进度文件已 deleted.%r</span><span class="sxs-lookup"><span data-stu-id="b58c8-116">The replay or progress file was deleted.%r</span></span><br /><br /> <span data-ttu-id="b58c8-117">文件名称： %1</span><span class="sxs-lookup"><span data-stu-id="b58c8-117">File Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="b58c8-118">解释</span><span class="sxs-lookup"><span data-stu-id="b58c8-118">Explanation</span></span>  
 <span data-ttu-id="b58c8-119">此信息事件表明 SSO 已删除重播和 \ 或进度文件。</span><span class="sxs-lookup"><span data-stu-id="b58c8-119">This Information event indicates that SSO has deleted a replay and\or progress file.</span></span>  

 <span data-ttu-id="b58c8-120">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="b58c8-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="b58c8-121">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="b58c8-121">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="b58c8-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="b58c8-122">User Action</span></span>  

- <span data-ttu-id="b58c8-123">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="b58c8-123">No user action is necessary.</span></span>  

  <span data-ttu-id="b58c8-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="b58c8-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="b58c8-125">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="b58c8-125">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="b58c8-126">密码同步</span><span class="sxs-lookup"><span data-stu-id="b58c8-126">Password Synchronization</span></span>](../core/password-synchronization2.md)
