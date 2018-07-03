---
title: 单一登录： 事件 10533 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31abd828-5f10-43f7-b99e-f3195250130c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2fd77728e459c544a9934e5d27f28a9ea092c67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008878"
---
# <a name="single-sign-on-event-10533"></a><span data-ttu-id="e3caa-102">单一登录： 事件 10533</span><span class="sxs-lookup"><span data-stu-id="e3caa-102">Single Sign-On: Event 10533</span></span>
## <a name="details"></a><span data-ttu-id="e3caa-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e3caa-103">Details</span></span>  

|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e3caa-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e3caa-104">Product Name</span></span>   |                                             <span data-ttu-id="e3caa-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e3caa-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="e3caa-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e3caa-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="e3caa-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e3caa-107">Event ID</span></span>     |                                                       <span data-ttu-id="e3caa-108">10533</span><span class="sxs-lookup"><span data-stu-id="e3caa-108">10533</span></span>                                                       |
|  <span data-ttu-id="e3caa-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e3caa-109">Event Source</span></span>   |                                                      <span data-ttu-id="e3caa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e3caa-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="e3caa-111">组件</span><span class="sxs-lookup"><span data-stu-id="e3caa-111">Component</span></span>    |                                                        <span data-ttu-id="e3caa-112">N\A</span><span class="sxs-lookup"><span data-stu-id="e3caa-112">N\A</span></span>                                                        |
|  <span data-ttu-id="e3caa-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e3caa-113">Symbolic Name</span></span>  |                                            <span data-ttu-id="e3caa-114">SSO_INFO_GOT_CURRENT_SECRET</span><span class="sxs-lookup"><span data-stu-id="e3caa-114">SSO_INFO_GOT_CURRENT_SECRET</span></span>                                            |
|  <span data-ttu-id="e3caa-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e3caa-115">Message Text</span></span>   | <span data-ttu-id="e3caa-116">从主密钥服务器获取最新密钥。%r</span><span class="sxs-lookup"><span data-stu-id="e3caa-116">Got the current secret from the master secret server.%r</span></span><br /><br /> <span data-ttu-id="e3caa-117">密钥服务器名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e3caa-117">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="e3caa-118">MSID: %2</span><span class="sxs-lookup"><span data-stu-id="e3caa-118">MSID: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="e3caa-119">解释</span><span class="sxs-lookup"><span data-stu-id="e3caa-119">Explanation</span></span>  
 <span data-ttu-id="e3caa-120">此信息事件表示 SSO 拥有最新的主密钥。</span><span class="sxs-lookup"><span data-stu-id="e3caa-120">This Information event indicates that SSO has the current master secret.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e3caa-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="e3caa-121">User Action</span></span>  

- <span data-ttu-id="e3caa-122">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="e3caa-122">No user action is necessary.</span></span>  

  <span data-ttu-id="e3caa-123">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="e3caa-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="e3caa-124">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="e3caa-124">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="e3caa-125">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="e3caa-125">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
