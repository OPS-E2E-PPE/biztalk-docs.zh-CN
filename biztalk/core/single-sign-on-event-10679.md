---
title: 单一登录： 事件 10679 |Microsoft Docs
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
ms.openlocfilehash: dbeb91e58582fcd37fca4c791b35a9edfc558c96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000350"
---
# <a name="single-sign-on-event-10679"></a><span data-ttu-id="5c5b7-102">单一登录： 事件 10679</span><span class="sxs-lookup"><span data-stu-id="5c5b7-102">Single Sign-On: Event 10679</span></span>
## <a name="details"></a><span data-ttu-id="5c5b7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5c5b7-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5c5b7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5c5b7-104">Product Name</span></span>   |                                                                                                           <span data-ttu-id="5c5b7-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5c5b7-105">Enterprise Single Sign-On</span></span>                                                                                                            |
| <span data-ttu-id="5c5b7-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5c5b7-106">Product Version</span></span> |                                                                                           [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                           |
|    <span data-ttu-id="5c5b7-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5c5b7-107">Event ID</span></span>     |                                                                                                                     <span data-ttu-id="5c5b7-108">10679</span><span class="sxs-lookup"><span data-stu-id="5c5b7-108">10679</span></span>                                                                                                                      |
|  <span data-ttu-id="5c5b7-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5c5b7-109">Event Source</span></span>   |                                                                                                                     <span data-ttu-id="5c5b7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5c5b7-110">ENTSSO</span></span>                                                                                                                     |
|    <span data-ttu-id="5c5b7-111">组件</span><span class="sxs-lookup"><span data-stu-id="5c5b7-111">Component</span></span>    |                                                                                                                      <span data-ttu-id="5c5b7-112">N\A</span><span class="sxs-lookup"><span data-stu-id="5c5b7-112">N\A</span></span>                                                                                                                       |
|  <span data-ttu-id="5c5b7-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5c5b7-113">Symbolic Name</span></span>  |                                                                                                          <span data-ttu-id="5c5b7-114">SSO_WARN_PS_MAPPING_DISABLED</span><span class="sxs-lookup"><span data-stu-id="5c5b7-114">SSO_WARN_PS_MAPPING_DISABLED</span></span>                                                                                                          |
|  <span data-ttu-id="5c5b7-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5c5b7-115">Message Text</span></span>   | <span data-ttu-id="5c5b7-116">外部密码更改。</span><span class="sxs-lookup"><span data-stu-id="5c5b7-116">External password change.</span></span> <span data-ttu-id="5c5b7-117">由于已禁用映射，因此未更改外部帐户的密码。%r</span><span class="sxs-lookup"><span data-stu-id="5c5b7-117">The password was not changed for the external account because the mapping is disabled.%r</span></span><br /><br /> <span data-ttu-id="5c5b7-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5c5b7-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="5c5b7-119">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="5c5b7-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="5c5b7-120">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="5c5b7-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="5c5b7-121">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="5c5b7-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="5c5b7-122">解释</span><span class="sxs-lookup"><span data-stu-id="5c5b7-122">Explanation</span></span>  
 <span data-ttu-id="5c5b7-123">此警告事件表明由于已禁用映射而未更改外部帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="5c5b7-123">This Warning event indicates that the password was not changed for the external account because the mapping is disabled.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5c5b7-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="5c5b7-124">User Action</span></span>  
 <span data-ttu-id="5c5b7-125">要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5c5b7-125">To resolve this warning do the following:</span></span>  

-   <span data-ttu-id="5c5b7-126">使用 SSO 管理工具启用此适配器的映射。</span><span class="sxs-lookup"><span data-stu-id="5c5b7-126">Use the SSO administration tools to enable mapping for this adapter.</span></span>  

## <a name="more-info"></a><span data-ttu-id="5c5b7-127">详细信息</span><span class="sxs-lookup"><span data-stu-id="5c5b7-127">More info</span></span>

- [<span data-ttu-id="5c5b7-128">密码同步</span><span class="sxs-lookup"><span data-stu-id="5c5b7-128">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="5c5b7-129">**密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="5c5b7-129">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
