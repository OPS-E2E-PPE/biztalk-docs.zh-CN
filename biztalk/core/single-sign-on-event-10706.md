---
title: 单一登录：Event 10706 | Microsoft Docs
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
ms.openlocfilehash: 7484ddf2b669976919b493230995c4ba233b3662
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397271"
---
# <a name="single-sign-on-event-10706"></a><span data-ttu-id="cf2b5-102">单一登录：事件 10706</span><span class="sxs-lookup"><span data-stu-id="cf2b5-102">Single Sign-On: Event 10706</span></span>
## <a name="details"></a><span data-ttu-id="cf2b5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cf2b5-103">Details</span></span>  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cf2b5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cf2b5-104">Product Name</span></span>   |                                                 <span data-ttu-id="cf2b5-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="cf2b5-105">Enterprise Single Sign-On</span></span>                                                 |
| <span data-ttu-id="cf2b5-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="cf2b5-106">Product Version</span></span> |                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                 |
|    <span data-ttu-id="cf2b5-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cf2b5-107">Event ID</span></span>     |                                                           <span data-ttu-id="cf2b5-108">10706</span><span class="sxs-lookup"><span data-stu-id="cf2b5-108">10706</span></span>                                                           |
|  <span data-ttu-id="cf2b5-109">事件源</span><span class="sxs-lookup"><span data-stu-id="cf2b5-109">Event Source</span></span>   |                                                          <span data-ttu-id="cf2b5-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cf2b5-110">ENTSSO</span></span>                                                           |
|    <span data-ttu-id="cf2b5-111">组件</span><span class="sxs-lookup"><span data-stu-id="cf2b5-111">Component</span></span>    |                                                            <span data-ttu-id="cf2b5-112">N\A</span><span class="sxs-lookup"><span data-stu-id="cf2b5-112">N\A</span></span>                                                            |
|  <span data-ttu-id="cf2b5-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="cf2b5-113">Symbolic Name</span></span>  |                                                <span data-ttu-id="cf2b5-114">SSO_WARN_PS_NO_GLOBAL_SYNC</span><span class="sxs-lookup"><span data-stu-id="cf2b5-114">SSO_WARN_PS_NO_GLOBAL_SYNC</span></span>                                                 |
|  <span data-ttu-id="cf2b5-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="cf2b5-115">Message Text</span></span>   | <span data-ttu-id="cf2b5-116">组适配器要求全局标志允许密码同步。</span><span class="sxs-lookup"><span data-stu-id="cf2b5-116">Group adapters require password sync to be allowed by the global flags.</span></span> <span data-ttu-id="cf2b5-117">检查全局 flags.%r</span><span class="sxs-lookup"><span data-stu-id="cf2b5-117">Check the global flags.%r</span></span><br /><br /> <span data-ttu-id="cf2b5-118">适配器： %1</span><span class="sxs-lookup"><span data-stu-id="cf2b5-118">Adapter: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="cf2b5-119">解释</span><span class="sxs-lookup"><span data-stu-id="cf2b5-119">Explanation</span></span>  
 <span data-ttu-id="cf2b5-120">此警告事件表示外部密码同步适配器请求密码同步和全局标志未设置。</span><span class="sxs-lookup"><span data-stu-id="cf2b5-120">This Warning event indicates that password sync is requested by an external password sync adapter and neither of the global flags is set.</span></span> <span data-ttu-id="cf2b5-121">有两个标记，允许将密码发送到外部系统：Sso_flag_full_sync_from_windows_to_external; 另外，允许接收来自外部系统： SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB 的密码。</span><span class="sxs-lookup"><span data-stu-id="cf2b5-121">There are two flags, one that allows sending of password to external system: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL and another that allows receiving of passwords from external systems SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cf2b5-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="cf2b5-122">User Action</span></span>  
 <span data-ttu-id="cf2b5-123">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cf2b5-123">To resolve this warning, do the following:</span></span>  

-   <span data-ttu-id="cf2b5-124">使用 SSO Admin MMC 管理单元，(系统&#124;属性&#124;选项) 或命令行工具`ssomanage –enable winsync/extsync`来启用全局标志。</span><span class="sxs-lookup"><span data-stu-id="cf2b5-124">Use the SSO Admin MMC Snap-In, (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  

## <a name="more-info"></a><span data-ttu-id="cf2b5-125">详细信息</span><span class="sxs-lookup"><span data-stu-id="cf2b5-125">More info</span></span>

- <span data-ttu-id="cf2b5-126">**企业单一登录标志** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="cf2b5-126">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="cf2b5-127">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="cf2b5-127">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
