---
title: 单一登录： 事件 10671 |Microsoft Docs
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
ms.openlocfilehash: f321a971f89c535da26604c3e03a2b62ebf060e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000070"
---
# <a name="single-sign-on-event-10671"></a><span data-ttu-id="21c8b-102">单一登录： 事件 10671</span><span class="sxs-lookup"><span data-stu-id="21c8b-102">Single Sign-On: Event 10671</span></span>
## <a name="details"></a><span data-ttu-id="21c8b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="21c8b-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="21c8b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="21c8b-104">Product Name</span></span>   |                                                                                                                                                                                  <span data-ttu-id="21c8b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="21c8b-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="21c8b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="21c8b-106">Product Version</span></span> |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    <span data-ttu-id="21c8b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="21c8b-107">Event ID</span></span>     |                                                                                                                                                                                            <span data-ttu-id="21c8b-108">10671</span><span class="sxs-lookup"><span data-stu-id="21c8b-108">10671</span></span>                                                                                                                                                                                            |
|  <span data-ttu-id="21c8b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="21c8b-109">Event Source</span></span>   |                                                                                                                                                                                           <span data-ttu-id="21c8b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="21c8b-110">ENTSSO</span></span>                                                                                                                                                                                            |
|    <span data-ttu-id="21c8b-111">组件</span><span class="sxs-lookup"><span data-stu-id="21c8b-111">Component</span></span>    |                                                                                                                                                                                             <span data-ttu-id="21c8b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="21c8b-112">N\A</span></span>                                                                                                                                                                                             |
|  <span data-ttu-id="21c8b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="21c8b-113">Symbolic Name</span></span>  |                                                                                                                                                                         <span data-ttu-id="21c8b-114">SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="21c8b-114">SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="21c8b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="21c8b-115">Message Text</span></span>   | <span data-ttu-id="21c8b-116">Windows 密码更改将导致更改同一外部系统上的多个帐户。%r</span><span class="sxs-lookup"><span data-stu-id="21c8b-116">A Windows password change will cause changes to more than one account on the same external system.%r</span></span><br /><br /> <span data-ttu-id="21c8b-117">这是允许的，因为此外部系统的适配器配置为允许映射冲突。%r</span><span class="sxs-lookup"><span data-stu-id="21c8b-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="21c8b-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="21c8b-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="21c8b-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="21c8b-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="21c8b-120">Windows 帐户: %3 %r</span><span class="sxs-lookup"><span data-stu-id="21c8b-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="21c8b-121">外部帐户 1: %4 %r</span><span class="sxs-lookup"><span data-stu-id="21c8b-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="21c8b-122">外部帐户 2: %5</span><span class="sxs-lookup"><span data-stu-id="21c8b-122">External Account 2: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="21c8b-123">解释</span><span class="sxs-lookup"><span data-stu-id="21c8b-123">Explanation</span></span>  
 <span data-ttu-id="21c8b-124">此信息事件表示 Windows 密码更改将更改同一外部系统上的多个帐户。</span><span class="sxs-lookup"><span data-stu-id="21c8b-124">This Information event indicates that a Windows password change will cause changes to more than one account on the same external system.</span></span>  

## <a name="user-action"></a><span data-ttu-id="21c8b-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="21c8b-125">User Action</span></span>  

-   <span data-ttu-id="21c8b-126">不需要用户进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="21c8b-126">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="21c8b-127">详细信息</span><span class="sxs-lookup"><span data-stu-id="21c8b-127">More info</span></span>

- <span data-ttu-id="21c8b-128">**密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="21c8b-128">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="21c8b-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="21c8b-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
