---
title: 单一登录：Event 10680 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88ea12ff-d181-423f-9054-b0c656cc4558
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a8b734006a8ec0181a3307386a32d8d249eaa25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397434"
---
# <a name="single-sign-on-event-10680"></a><span data-ttu-id="f70a6-102">单一登录：事件 10680</span><span class="sxs-lookup"><span data-stu-id="f70a6-102">Single Sign-On: Event 10680</span></span>
## <a name="details"></a><span data-ttu-id="f70a6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f70a6-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f70a6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f70a6-104">Product Name</span></span>   |                                                                                                                                        <span data-ttu-id="f70a6-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f70a6-105">Enterprise Single Sign-On</span></span>                                                                                                                                        |
| <span data-ttu-id="f70a6-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f70a6-106">Product Version</span></span> |                                                                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                        |
|    <span data-ttu-id="f70a6-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f70a6-107">Event ID</span></span>     |                                                                                                                                                  <span data-ttu-id="f70a6-108">10680</span><span class="sxs-lookup"><span data-stu-id="f70a6-108">10680</span></span>                                                                                                                                                  |
|  <span data-ttu-id="f70a6-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f70a6-109">Event Source</span></span>   |                                                                                                                                                 <span data-ttu-id="f70a6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f70a6-110">ENTSSO</span></span>                                                                                                                                                  |
|    <span data-ttu-id="f70a6-111">组件</span><span class="sxs-lookup"><span data-stu-id="f70a6-111">Component</span></span>    |                                                                                                                                                   <span data-ttu-id="f70a6-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f70a6-112">N\A</span></span>                                                                                                                                                   |
|  <span data-ttu-id="f70a6-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f70a6-113">Symbolic Name</span></span>  |                                                                                                                                      <span data-ttu-id="f70a6-114">SSO_WARN_PS_GET_CREDS_FAILED</span><span class="sxs-lookup"><span data-stu-id="f70a6-114">SSO_WARN_PS_GET_CREDS_FAILED</span></span>                                                                                                                                       |
|  <span data-ttu-id="f70a6-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f70a6-115">Message Text</span></span>   | <span data-ttu-id="f70a6-116">密码未更改外部帐户由于无法从 SSO database.%r 获得现有外部凭据</span><span class="sxs-lookup"><span data-stu-id="f70a6-116">The password was not changed for the external account because the existing external credentials could not be obtained from the SSO database.%r</span></span><br /><br /> <span data-ttu-id="f70a6-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f70a6-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="f70a6-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f70a6-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="f70a6-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="f70a6-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="f70a6-120">外部帐户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="f70a6-120">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="f70a6-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="f70a6-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="f70a6-122">解释</span><span class="sxs-lookup"><span data-stu-id="f70a6-122">Explanation</span></span>  
 <span data-ttu-id="f70a6-123">此警告事件表示，密码未更改外部帐户由于无法从 SSO 数据库获得现有外部凭据。</span><span class="sxs-lookup"><span data-stu-id="f70a6-123">This Warning event indicates that the password was not changed for the external account because the existing external credentials could not be obtained from the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f70a6-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="f70a6-124">User Action</span></span>  
 <span data-ttu-id="f70a6-125">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f70a6-125">To resolve this warning, do the following:</span></span>  

-   <span data-ttu-id="f70a6-126">验证外部凭据。</span><span class="sxs-lookup"><span data-stu-id="f70a6-126">Verify external credentials.</span></span>  

-   <span data-ttu-id="f70a6-127">外部凭据不是有效，请使用 SSO 管理工具设置此外部帐户的外部凭据。</span><span class="sxs-lookup"><span data-stu-id="f70a6-127">The external credentials are not valid, use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="f70a6-128">必须在所有关联应用程序中设置 （适用于给定的帐户的外部密码。</span><span class="sxs-lookup"><span data-stu-id="f70a6-128">You must set the external password (for the given account) in all associated applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="f70a6-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="f70a6-129">More info</span></span>

- [<span data-ttu-id="f70a6-130">密码同步</span><span class="sxs-lookup"><span data-stu-id="f70a6-130">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="f70a6-131">**密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="f70a6-131">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
