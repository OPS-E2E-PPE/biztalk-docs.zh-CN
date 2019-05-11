---
title: 单一登录：Event 10679 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645f2b74-2cbe-4c6a-b0f5-7e31f93f88c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f3b551d0c5eecab6ad84b54303bd2c25bbf46eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397440"
---
# <a name="single-sign-on-event-10679"></a><span data-ttu-id="89c7a-102">单一登录：事件 10679</span><span class="sxs-lookup"><span data-stu-id="89c7a-102">Single Sign-On: Event 10679</span></span>
## <a name="details"></a><span data-ttu-id="89c7a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="89c7a-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="89c7a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="89c7a-104">Product Name</span></span>   |                                                                                                           <span data-ttu-id="89c7a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="89c7a-105">Enterprise Single Sign-On</span></span>                                                                                                            |
| <span data-ttu-id="89c7a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="89c7a-106">Product Version</span></span> |                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                           |
|    <span data-ttu-id="89c7a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="89c7a-107">Event ID</span></span>     |                                                                                                                     <span data-ttu-id="89c7a-108">10679</span><span class="sxs-lookup"><span data-stu-id="89c7a-108">10679</span></span>                                                                                                                      |
|  <span data-ttu-id="89c7a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="89c7a-109">Event Source</span></span>   |                                                                                                                     <span data-ttu-id="89c7a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="89c7a-110">ENTSSO</span></span>                                                                                                                     |
|    <span data-ttu-id="89c7a-111">组件</span><span class="sxs-lookup"><span data-stu-id="89c7a-111">Component</span></span>    |                                                                                                                      <span data-ttu-id="89c7a-112">N\A</span><span class="sxs-lookup"><span data-stu-id="89c7a-112">N\A</span></span>                                                                                                                       |
|  <span data-ttu-id="89c7a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="89c7a-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="89c7a-114">SSO_WARN_PS_MAPPING_DISABLED</span><span class="sxs-lookup"><span data-stu-id="89c7a-114">SSO_WARN_PS_MAPPING_DISABLED</span></span>                                                                                                          |
|  <span data-ttu-id="89c7a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="89c7a-115">Message Text</span></span>   | <span data-ttu-id="89c7a-116">外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="89c7a-116">External password change.</span></span> <span data-ttu-id="89c7a-117">密码未更改外部帐户因为映射被 disabled.%r</span><span class="sxs-lookup"><span data-stu-id="89c7a-117">The password was not changed for the external account because the mapping is disabled.%r</span></span><br /><br /> <span data-ttu-id="89c7a-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="89c7a-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="89c7a-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="89c7a-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="89c7a-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="89c7a-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="89c7a-121">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="89c7a-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="89c7a-122">解释</span><span class="sxs-lookup"><span data-stu-id="89c7a-122">Explanation</span></span>  
 <span data-ttu-id="89c7a-123">此警告事件表示，密码未更改外部帐户因为已禁用映射。</span><span class="sxs-lookup"><span data-stu-id="89c7a-123">This Warning event indicates that the password was not changed for the external account because the mapping is disabled.</span></span>  

## <a name="user-action"></a><span data-ttu-id="89c7a-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="89c7a-124">User Action</span></span>  
 <span data-ttu-id="89c7a-125">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="89c7a-125">To resolve this warning do the following:</span></span>  

-   <span data-ttu-id="89c7a-126">使用 SSO 管理工具来启用此适配器的映射。</span><span class="sxs-lookup"><span data-stu-id="89c7a-126">Use the SSO administration tools to enable mapping for this adapter.</span></span>  

## <a name="more-info"></a><span data-ttu-id="89c7a-127">详细信息</span><span class="sxs-lookup"><span data-stu-id="89c7a-127">More info</span></span>

- [<span data-ttu-id="89c7a-128">密码同步</span><span class="sxs-lookup"><span data-stu-id="89c7a-128">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="89c7a-129">**密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="89c7a-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
