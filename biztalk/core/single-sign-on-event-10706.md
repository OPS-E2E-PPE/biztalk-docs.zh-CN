---
title: 单一登录： 事件 10706 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73db77e-5bb6-431c-a8ca-5682d7ab3d6a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9e56600b86856af6a9cdb14fd2a902b047e84b5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022451"
---
# <a name="single-sign-on-event-10706"></a><span data-ttu-id="6b88e-102">单一登录： 事件 10706</span><span class="sxs-lookup"><span data-stu-id="6b88e-102">Single Sign-On: Event 10706</span></span>
## <a name="details"></a><span data-ttu-id="6b88e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6b88e-103">Details</span></span>  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6b88e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6b88e-104">Product Name</span></span>   |                                                 <span data-ttu-id="6b88e-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="6b88e-105">Enterprise Single Sign-On</span></span>                                                 |
| <span data-ttu-id="6b88e-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="6b88e-106">Product Version</span></span> |                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                 |
|    <span data-ttu-id="6b88e-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6b88e-107">Event ID</span></span>     |                                                           <span data-ttu-id="6b88e-108">10706</span><span class="sxs-lookup"><span data-stu-id="6b88e-108">10706</span></span>                                                           |
|  <span data-ttu-id="6b88e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="6b88e-109">Event Source</span></span>   |                                                          <span data-ttu-id="6b88e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6b88e-110">ENTSSO</span></span>                                                           |
|    <span data-ttu-id="6b88e-111">组件</span><span class="sxs-lookup"><span data-stu-id="6b88e-111">Component</span></span>    |                                                            <span data-ttu-id="6b88e-112">N\A</span><span class="sxs-lookup"><span data-stu-id="6b88e-112">N\A</span></span>                                                            |
|  <span data-ttu-id="6b88e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="6b88e-113">Symbolic Name</span></span>  |                                                <span data-ttu-id="6b88e-114">SSO_WARN_PS_NO_GLOBAL_SYNC</span><span class="sxs-lookup"><span data-stu-id="6b88e-114">SSO_WARN_PS_NO_GLOBAL_SYNC</span></span>                                                 |
|  <span data-ttu-id="6b88e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="6b88e-115">Message Text</span></span>   | <span data-ttu-id="6b88e-116">组适配器要求全局标志允许密码同步。</span><span class="sxs-lookup"><span data-stu-id="6b88e-116">Group adapters require password sync to be allowed by the global flags.</span></span> <span data-ttu-id="6b88e-117">请检查全局标志。%r</span><span class="sxs-lookup"><span data-stu-id="6b88e-117">Check the global flags.%r</span></span><br /><br /> <span data-ttu-id="6b88e-118">适配器： %1</span><span class="sxs-lookup"><span data-stu-id="6b88e-118">Adapter: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="6b88e-119">解释</span><span class="sxs-lookup"><span data-stu-id="6b88e-119">Explanation</span></span>  
 <span data-ttu-id="6b88e-120">此警告事件表示，外部密码同步适配器请求密码同步，并且未设置全局标记。</span><span class="sxs-lookup"><span data-stu-id="6b88e-120">This Warning event indicates that password sync is requested by an external password sync adapter and neither of the global flags is set.</span></span> <span data-ttu-id="6b88e-121">有两个标志，允许将密码发送到外部系统： sso_flag_full_sync_from_windows_to_external; 另外，允许接收来自外部系统： SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB 的密码。</span><span class="sxs-lookup"><span data-stu-id="6b88e-121">There are two flags, one that allows sending of password to external system: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL and another that allows receiving of passwords from external systems SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB.</span></span>  

## <a name="user-action"></a><span data-ttu-id="6b88e-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="6b88e-122">User Action</span></span>  
 <span data-ttu-id="6b88e-123">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6b88e-123">To resolve this warning, do the following:</span></span>  

-   <span data-ttu-id="6b88e-124">使用 SSO Admin MMC 管理单元，(系统&#124;属性&#124;选项) 或命令行工具`ssomanage –enable winsync/extsync`来启用全局标志。</span><span class="sxs-lookup"><span data-stu-id="6b88e-124">Use the SSO Admin MMC Snap-In, (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  

## <a name="more-info"></a><span data-ttu-id="6b88e-125">详细信息</span><span class="sxs-lookup"><span data-stu-id="6b88e-125">More info</span></span>

- <span data-ttu-id="6b88e-126">**企业单一登录标志** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6b88e-126">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="6b88e-127">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="6b88e-127">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
