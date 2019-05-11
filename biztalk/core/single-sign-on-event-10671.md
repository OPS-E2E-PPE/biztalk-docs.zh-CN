---
title: 单一登录：Event 10671 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c5564f-6412-4e83-9bec-03264e992ebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84f3b434cc328b9356e3f5a7db380c92366c210c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397514"
---
# <a name="single-sign-on-event-10671"></a><span data-ttu-id="d4c1d-102">单一登录：事件 10671</span><span class="sxs-lookup"><span data-stu-id="d4c1d-102">Single Sign-On: Event 10671</span></span>
## <a name="details"></a><span data-ttu-id="d4c1d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d4c1d-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d4c1d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d4c1d-104">Product Name</span></span>   |                                                                                                                                                                                  <span data-ttu-id="d4c1d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d4c1d-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="d4c1d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d4c1d-106">Product Version</span></span> |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    <span data-ttu-id="d4c1d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d4c1d-107">Event ID</span></span>     |                                                                                                                                                                                            <span data-ttu-id="d4c1d-108">10671</span><span class="sxs-lookup"><span data-stu-id="d4c1d-108">10671</span></span>                                                                                                                                                                                            |
|  <span data-ttu-id="d4c1d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d4c1d-109">Event Source</span></span>   |                                                                                                                                                                                           <span data-ttu-id="d4c1d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d4c1d-110">ENTSSO</span></span>                                                                                                                                                                                            |
|    <span data-ttu-id="d4c1d-111">组件</span><span class="sxs-lookup"><span data-stu-id="d4c1d-111">Component</span></span>    |                                                                                                                                                                                             <span data-ttu-id="d4c1d-112">N\A</span><span class="sxs-lookup"><span data-stu-id="d4c1d-112">N\A</span></span>                                                                                                                                                                                             |
|  <span data-ttu-id="d4c1d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d4c1d-113">Symbolic Name</span></span>  |                                                                                                                                                                         <span data-ttu-id="d4c1d-114">SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="d4c1d-114">SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="d4c1d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d4c1d-115">Message Text</span></span>   | <span data-ttu-id="d4c1d-116">Windows 密码更改将导致对同一外部 system.%r 上的多个帐户的更改</span><span class="sxs-lookup"><span data-stu-id="d4c1d-116">A Windows password change will cause changes to more than one account on the same external system.%r</span></span><br /><br /> <span data-ttu-id="d4c1d-117">这允许，因为此外部系统的适配器配置为允许映射 conflicts.%r</span><span class="sxs-lookup"><span data-stu-id="d4c1d-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="d4c1d-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d4c1d-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="d4c1d-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="d4c1d-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="d4c1d-120">Windows 帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="d4c1d-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="d4c1d-121">外部帐户 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="d4c1d-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="d4c1d-122">外部帐户 2: %5</span><span class="sxs-lookup"><span data-stu-id="d4c1d-122">External Account 2: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="d4c1d-123">解释</span><span class="sxs-lookup"><span data-stu-id="d4c1d-123">Explanation</span></span>  
 <span data-ttu-id="d4c1d-124">此信息事件表明 Windows 密码更改将会对多个帐户的更改导致同一外部系统上。</span><span class="sxs-lookup"><span data-stu-id="d4c1d-124">This Information event indicates that a Windows password change will cause changes to more than one account on the same external system.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d4c1d-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="d4c1d-125">User Action</span></span>  

-   <span data-ttu-id="d4c1d-126">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="d4c1d-126">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="d4c1d-127">详细信息</span><span class="sxs-lookup"><span data-stu-id="d4c1d-127">More info</span></span>

- <span data-ttu-id="d4c1d-128">**密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="d4c1d-128">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="d4c1d-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="d4c1d-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
