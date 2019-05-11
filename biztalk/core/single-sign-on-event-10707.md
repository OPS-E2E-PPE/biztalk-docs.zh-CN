---
title: 单一登录：Event 10707 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59629786-4f98-4861-aba3-153670bafc12
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e323f9b712e566278bf43224611b2d39e74dcecb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397275"
---
# <a name="single-sign-on-event-10707"></a><span data-ttu-id="896b9-102">单一登录：事件 10707</span><span class="sxs-lookup"><span data-stu-id="896b9-102">Single Sign-On: Event 10707</span></span>
## <a name="details"></a><span data-ttu-id="896b9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="896b9-103">Details</span></span>  

|                 |                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="896b9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="896b9-104">Product Name</span></span>   |                                                                       <span data-ttu-id="896b9-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="896b9-105">Enterprise Single Sign-On</span></span>                                                                        |
| <span data-ttu-id="896b9-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="896b9-106">Product Version</span></span> |                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    <span data-ttu-id="896b9-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="896b9-107">Event ID</span></span>     |                                                                                 <span data-ttu-id="896b9-108">10707</span><span class="sxs-lookup"><span data-stu-id="896b9-108">10707</span></span>                                                                                  |
|  <span data-ttu-id="896b9-109">事件源</span><span class="sxs-lookup"><span data-stu-id="896b9-109">Event Source</span></span>   |                                                                                 <span data-ttu-id="896b9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="896b9-110">ENTSSO</span></span>                                                                                 |
|    <span data-ttu-id="896b9-111">组件</span><span class="sxs-lookup"><span data-stu-id="896b9-111">Component</span></span>    |                                                                                  <span data-ttu-id="896b9-112">N\A</span><span class="sxs-lookup"><span data-stu-id="896b9-112">N\A</span></span>                                                                                   |
|  <span data-ttu-id="896b9-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="896b9-113">Symbolic Name</span></span>  |                                                                        <span data-ttu-id="896b9-114">SSO_WARN_PS_NO_APP_SYNC</span><span class="sxs-lookup"><span data-stu-id="896b9-114">SSO_WARN_PS_NO_APP_SYNC</span></span>                                                                         |
|  <span data-ttu-id="896b9-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="896b9-115">Message Text</span></span>   | <span data-ttu-id="896b9-116">此适配器的密码同步标志必须允许密码同步，并且必须匹配全局标志。</span><span class="sxs-lookup"><span data-stu-id="896b9-116">Password sync flags for this adapter must allow password sync and must match the global flags.</span></span> <span data-ttu-id="896b9-117">检查适配器标志和全局 flags.%r</span><span class="sxs-lookup"><span data-stu-id="896b9-117">Check the adapter flags and the global flags.%r</span></span><br /><br /> <span data-ttu-id="896b9-118">适配器： %1</span><span class="sxs-lookup"><span data-stu-id="896b9-118">Adapter: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="896b9-119">解释</span><span class="sxs-lookup"><span data-stu-id="896b9-119">Explanation</span></span>  
 <span data-ttu-id="896b9-120">此警告事件表明此适配器的密码同步标志必须允许密码同步，并且必须匹配全局标志。</span><span class="sxs-lookup"><span data-stu-id="896b9-120">This Warning event indicates that password sync flags for this adapter must allow password sync and must match the global flags.</span></span>  

 <span data-ttu-id="896b9-121">一个由两个标志控制的密码同步适配器的密码同步，允许发送到外部系统 (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) 的密码，另一类允许接收来自外部系统 (SSO_FLAG_PARTIAL_ 密码SYNC_FROM_EXTERNAL_TO_DB)。</span><span class="sxs-lookup"><span data-stu-id="896b9-121">Password sync for a password sync adapter is controlled by two flags, one allows sending of password to external systems (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) and another which allows receiving of passwords from external systems (SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB).</span></span> <span data-ttu-id="896b9-122">这些必须对于成功的密码同步设置这两个"全局标志"，还负责特定适配器标志。</span><span class="sxs-lookup"><span data-stu-id="896b9-122">For successfull password sync these must be set for both the “global flags” and also for the specific adapter flags.</span></span> <span data-ttu-id="896b9-123">外部密码同步适配器请求密码同步，并且这些标志设置为"全局标志"和适配器标志时，会发出此警告事件。</span><span class="sxs-lookup"><span data-stu-id="896b9-123">This warning event is issued when password sync is requested by an external password sync adapter and neither of these flags is set for both the “global flags” and the adapter flags.</span></span>  

## <a name="user-action"></a><span data-ttu-id="896b9-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="896b9-124">User Action</span></span>  
 <span data-ttu-id="896b9-125">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="896b9-125">To resolve this warning, do the following:</span></span>  

-   <span data-ttu-id="896b9-126">使用 SSO Admin MMC 管理单元 (系统&#124;属性&#124;选项) 或命令行工具`ssomanage –enable winsync/extsync`来启用全局标志。</span><span class="sxs-lookup"><span data-stu-id="896b9-126">Use the SSO Admin MMC Snap-In (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  

## <a name="more-info"></a><span data-ttu-id="896b9-127">详细信息</span><span class="sxs-lookup"><span data-stu-id="896b9-127">More info</span></span>

- <span data-ttu-id="896b9-128">**企业单一登录标志** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="896b9-128">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  

- [<span data-ttu-id="896b9-129">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="896b9-129">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
