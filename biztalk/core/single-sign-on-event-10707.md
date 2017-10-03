---
title: "单一登录： 事件 10707 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59629786-4f98-4861-aba3-153670bafc12
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81f4d484aa7a69f23cb66a921f1c630db9fcf790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10707"></a><span data-ttu-id="2a1f7-102">单一登录： 事件 10707</span><span class="sxs-lookup"><span data-stu-id="2a1f7-102">Single Sign-On: Event 10707</span></span>
## <a name="details"></a><span data-ttu-id="2a1f7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2a1f7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a1f7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2a1f7-104">Product Name</span></span>|<span data-ttu-id="2a1f7-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="2a1f7-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="2a1f7-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="2a1f7-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="2a1f7-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2a1f7-107">Event ID</span></span>|<span data-ttu-id="2a1f7-108">10707</span><span class="sxs-lookup"><span data-stu-id="2a1f7-108">10707</span></span>|  
|<span data-ttu-id="2a1f7-109">事件源</span><span class="sxs-lookup"><span data-stu-id="2a1f7-109">Event Source</span></span>|<span data-ttu-id="2a1f7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2a1f7-110">ENTSSO</span></span>|  
|<span data-ttu-id="2a1f7-111">组件</span><span class="sxs-lookup"><span data-stu-id="2a1f7-111">Component</span></span>|<span data-ttu-id="2a1f7-112">N\A</span><span class="sxs-lookup"><span data-stu-id="2a1f7-112">N\A</span></span>|  
|<span data-ttu-id="2a1f7-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="2a1f7-113">Symbolic Name</span></span>|<span data-ttu-id="2a1f7-114">SSO_WARN_PS_NO_APP_SYNC</span><span class="sxs-lookup"><span data-stu-id="2a1f7-114">SSO_WARN_PS_NO_APP_SYNC</span></span>|  
|<span data-ttu-id="2a1f7-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="2a1f7-115">Message Text</span></span>|<span data-ttu-id="2a1f7-116">此适配器的密码同步标志必须允许密码同步并且必须匹配全局标志。</span><span class="sxs-lookup"><span data-stu-id="2a1f7-116">Password sync flags for this adapter must allow password sync and must match the global flags.</span></span> <span data-ttu-id="2a1f7-117">请检查适配器标志和全局标志。%r</span><span class="sxs-lookup"><span data-stu-id="2a1f7-117">Check the adapter flags and the global flags.%r</span></span><br /><br /> <span data-ttu-id="2a1f7-118">适配器： %1</span><span class="sxs-lookup"><span data-stu-id="2a1f7-118">Adapter: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2a1f7-119">解释</span><span class="sxs-lookup"><span data-stu-id="2a1f7-119">Explanation</span></span>  
 <span data-ttu-id="2a1f7-120">此警告事件表明此适配器的密码同步标志必须允许密码同步并且必须匹配全局标志。</span><span class="sxs-lookup"><span data-stu-id="2a1f7-120">This Warning event indicates that password sync flags for this adapter must allow password sync and must match the global flags.</span></span>  
  
 <span data-ttu-id="2a1f7-121">密码同步适配器的密码同步由两个标志控制，一个允许将密码发送到外部系统 (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL)，另一个允许从外部系统接收密码 (SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB)。</span><span class="sxs-lookup"><span data-stu-id="2a1f7-121">Password sync for a password sync adapter is controlled by two flags, one allows sending of password to external systems (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) and another which allows receiving of passwords from external systems (SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB).</span></span> <span data-ttu-id="2a1f7-122">为成功进行密码同步，这些标志必须都设置为“全局标志”，也可以设置为特定适配器标志。</span><span class="sxs-lookup"><span data-stu-id="2a1f7-122">For successfull password sync these must be set for both the “global flags” and also for the specific adapter flags.</span></span> <span data-ttu-id="2a1f7-123">当外部密码同步适配器请求密码同步，并且这些标志未设置为“全局标志”和适配器标志时，将发出此警告事件。</span><span class="sxs-lookup"><span data-stu-id="2a1f7-123">This warning event is issued when password sync is requested by an external password sync adapter and neither of these flags is set for both the “global flags” and the adapter flags.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2a1f7-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="2a1f7-124">User Action</span></span>  
 <span data-ttu-id="2a1f7-125">若要解决此警告问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2a1f7-125">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="2a1f7-126">使用 SSO 管理 MMC 管理单元 (系统 &#124;属性 &#124;选项） 或命令行工具`ssomanage –enable winsync/extsync`若要启用的全局标志。</span><span class="sxs-lookup"><span data-stu-id="2a1f7-126">Use the SSO Admin MMC Snap-In (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="2a1f7-127">详细信息</span><span class="sxs-lookup"><span data-stu-id="2a1f7-127">More info</span></span>
  
-   <span data-ttu-id="2a1f7-128">**企业单一登录标志**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="2a1f7-128">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
  
-   [<span data-ttu-id="2a1f7-129">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="2a1f7-129">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)