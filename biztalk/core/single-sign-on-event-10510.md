---
title: 单一登录：Event 10510 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4553ad4c-9553-4b8b-b3a3-72aed2a61202
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a3ac20c725492ebd6f7867cdf3c11be3ab7fdab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393936"
---
# <a name="single-sign-on-event-10510"></a><span data-ttu-id="22344-102">单一登录：事件 10510</span><span class="sxs-lookup"><span data-stu-id="22344-102">Single Sign-On: Event 10510</span></span>
## <a name="details"></a><span data-ttu-id="22344-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="22344-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="22344-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="22344-104">Product Name</span></span>   |                 <span data-ttu-id="22344-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="22344-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="22344-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="22344-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="22344-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="22344-107">Event ID</span></span>     |                           <span data-ttu-id="22344-108">10510</span><span class="sxs-lookup"><span data-stu-id="22344-108">10510</span></span>                            |
|  <span data-ttu-id="22344-109">事件源</span><span class="sxs-lookup"><span data-stu-id="22344-109">Event Source</span></span>   |                           <span data-ttu-id="22344-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="22344-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="22344-111">组件</span><span class="sxs-lookup"><span data-stu-id="22344-111">Component</span></span>    |                            <span data-ttu-id="22344-112">N\A</span><span class="sxs-lookup"><span data-stu-id="22344-112">N\A</span></span>                             |
|  <span data-ttu-id="22344-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="22344-113">Symbolic Name</span></span>  |                  <span data-ttu-id="22344-114">SSO_INFO_DLL_LOAD_FAILED</span><span class="sxs-lookup"><span data-stu-id="22344-114">SSO_INFO_DLL_LOAD_FAILED</span></span>                  |
|  <span data-ttu-id="22344-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="22344-115">Message Text</span></span>   |   <span data-ttu-id="22344-116">未能加载 %1。</span><span class="sxs-lookup"><span data-stu-id="22344-116">Failed to load %1.</span></span> <span data-ttu-id="22344-117">检查此文件可用。</span><span class="sxs-lookup"><span data-stu-id="22344-117">Check that this file is available.</span></span>    |

## <a name="explanation"></a><span data-ttu-id="22344-118">解释</span><span class="sxs-lookup"><span data-stu-id="22344-118">Explanation</span></span>  
 <span data-ttu-id="22344-119">此信息事件表明 SSO 服务无法加载 DLL。</span><span class="sxs-lookup"><span data-stu-id="22344-119">This Information event indicates that the SSO service has failed to load the DLL.</span></span>  

## <a name="user-action"></a><span data-ttu-id="22344-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="22344-120">User Action</span></span>  
 <span data-ttu-id="22344-121">若要解决此事件，请执行一个或多个以下操作：</span><span class="sxs-lookup"><span data-stu-id="22344-121">To resolve this event, do one or more of the following:</span></span>  

- <span data-ttu-id="22344-122">验证 DLL 位于 SSO 安装目录，通常 C:\Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="22344-122">Verify the DLL is located in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On.</span></span> <span data-ttu-id="22344-123">SSO 安装目录中可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="22344-123">Your SSO installation directory may be different.</span></span>  

- <span data-ttu-id="22344-124">如果单个 DLL 已丢失或损坏，尝试将其替换为，然后重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="22344-124">If the single DLL is missing or corrupted, attempt to replace it and then restart the service.</span></span>  

  <span data-ttu-id="22344-125">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="22344-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="22344-126">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="22344-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
