---
title: 单一登录：Event 10686 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3e71f2a-e51d-4736-b06a-117142d30dae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90306488cb77f40458cf0fccacae9050807a2e3d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397379"
---
# <a name="single-sign-on-event-10686"></a><span data-ttu-id="c59dd-102">单一登录：事件 10686</span><span class="sxs-lookup"><span data-stu-id="c59dd-102">Single Sign-On: Event 10686</span></span>
## <a name="details"></a><span data-ttu-id="c59dd-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c59dd-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="c59dd-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c59dd-104">Product Name</span></span>   |                         <span data-ttu-id="c59dd-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c59dd-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="c59dd-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c59dd-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="c59dd-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c59dd-107">Event ID</span></span>     |                                   <span data-ttu-id="c59dd-108">10686</span><span class="sxs-lookup"><span data-stu-id="c59dd-108">10686</span></span>                                   |
|  <span data-ttu-id="c59dd-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c59dd-109">Event Source</span></span>   |                                  <span data-ttu-id="c59dd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c59dd-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="c59dd-111">组件</span><span class="sxs-lookup"><span data-stu-id="c59dd-111">Component</span></span>    |                                    <span data-ttu-id="c59dd-112">N\A</span><span class="sxs-lookup"><span data-stu-id="c59dd-112">N\A</span></span>                                    |
|  <span data-ttu-id="c59dd-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c59dd-113">Symbolic Name</span></span>  |                          <span data-ttu-id="c59dd-114">SSO_INFO_REPLAY_STARTED</span><span class="sxs-lookup"><span data-stu-id="c59dd-114">SSO_INFO_REPLAY_STARTED</span></span>                          |
|  <span data-ttu-id="c59dd-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c59dd-115">Message Text</span></span>   | <span data-ttu-id="c59dd-116">正在重播存储的外部密码 changes.%r</span><span class="sxs-lookup"><span data-stu-id="c59dd-116">Replaying stored external password changes.%r</span></span><br /><br /> <span data-ttu-id="c59dd-117">重播文件： %1</span><span class="sxs-lookup"><span data-stu-id="c59dd-117">Replay File: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="c59dd-118">解释</span><span class="sxs-lookup"><span data-stu-id="c59dd-118">Explanation</span></span>  
 <span data-ttu-id="c59dd-119">此信息事件表明 SSO 正在重播存储的外部密码更改文件。</span><span class="sxs-lookup"><span data-stu-id="c59dd-119">This Information event indicates that SSO is replaying the stored external password changes file.</span></span> <span data-ttu-id="c59dd-120">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="c59dd-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c59dd-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="c59dd-121">User Action</span></span>  

- <span data-ttu-id="c59dd-122">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="c59dd-122">No user action is necessary.</span></span>  

  <span data-ttu-id="c59dd-123">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="c59dd-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="c59dd-124">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="c59dd-124">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="c59dd-125">密码同步</span><span class="sxs-lookup"><span data-stu-id="c59dd-125">Password Synchronization</span></span>](../core/password-synchronization2.md)
