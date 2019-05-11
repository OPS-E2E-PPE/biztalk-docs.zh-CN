---
title: 单一登录：Event 10678 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af92ce1-fdac-432f-be6b-cf8958aee776
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c8acb17f22b9b7fbf3faeaa918aa2fc0a7fd68e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397461"
---
# <a name="single-sign-on-event-10678"></a><span data-ttu-id="e507c-102">单一登录：事件 10678</span><span class="sxs-lookup"><span data-stu-id="e507c-102">Single Sign-On: Event 10678</span></span>
## <a name="details"></a><span data-ttu-id="e507c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e507c-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                 |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e507c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e507c-104">Product Name</span></span>   |                                                                                                                    <span data-ttu-id="e507c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e507c-105">Enterprise Single Sign-On</span></span>                                                                                                                    |
| <span data-ttu-id="e507c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e507c-106">Product Version</span></span> |                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    <span data-ttu-id="e507c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e507c-107">Event ID</span></span>     |                                                                                                                              <span data-ttu-id="e507c-108">10678</span><span class="sxs-lookup"><span data-stu-id="e507c-108">10678</span></span>                                                                                                                              |
|  <span data-ttu-id="e507c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e507c-109">Event Source</span></span>   |                                                                                                                             <span data-ttu-id="e507c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e507c-110">ENTSSO</span></span>                                                                                                                              |
|    <span data-ttu-id="e507c-111">组件</span><span class="sxs-lookup"><span data-stu-id="e507c-111">Component</span></span>    |                                                                                                                               <span data-ttu-id="e507c-112">N\A</span><span class="sxs-lookup"><span data-stu-id="e507c-112">N\A</span></span>                                                                                                                               |
|  <span data-ttu-id="e507c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e507c-113">Symbolic Name</span></span>  |                                                                                                                   <span data-ttu-id="e507c-114">SSO_WARN_PASSWORD_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="e507c-114">SSO_WARN_PASSWORD_MISMATCH</span></span>                                                                                                                    |
|  <span data-ttu-id="e507c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e507c-115">Message Text</span></span>   | <span data-ttu-id="e507c-116">外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="e507c-116">External password change.</span></span> <span data-ttu-id="e507c-117">适配器提供旧密码与外部 account.%r 的现有密码不匹配</span><span class="sxs-lookup"><span data-stu-id="e507c-117">The old password supplied by the adapter does not match the existing password for the external account.%r</span></span><br /><br /> <span data-ttu-id="e507c-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="e507c-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="e507c-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="e507c-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="e507c-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="e507c-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="e507c-121">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="e507c-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="e507c-122">解释</span><span class="sxs-lookup"><span data-stu-id="e507c-122">Explanation</span></span>  
 <span data-ttu-id="e507c-123">此警告事件表明适配器提供旧密码与外部帐户的现有密码不匹配。</span><span class="sxs-lookup"><span data-stu-id="e507c-123">This Warning event indicates that the old password supplied by the adapter does not match the existing password for the external account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e507c-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="e507c-124">User Action</span></span>  
 <span data-ttu-id="e507c-125">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e507c-125">To resolve this warning do the following:</span></span>  

-   <span data-ttu-id="e507c-126">确定哪些应用程序分配给此适配器 （事件日志消息中的名称），然后使用 SSO 管理工具设置此外部帐户的外部凭据。</span><span class="sxs-lookup"><span data-stu-id="e507c-126">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="e507c-127">必须在所有这些应用程序设置 （适用于给定的帐户的外部密码。</span><span class="sxs-lookup"><span data-stu-id="e507c-127">You must set the external password (for the given account) in all of those Applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="e507c-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="e507c-128">More info</span></span>

- [<span data-ttu-id="e507c-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="e507c-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="e507c-130">**密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="e507c-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
