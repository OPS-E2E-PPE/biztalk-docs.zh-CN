---
title: 单一登录：Event 10665 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d0de9d0-9b46-4f3a-b796-1ce3de01cf4c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47cd0f957ba835df7f7463a8ee9c33f7b4503eb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397560"
---
# <a name="single-sign-on-event-10665"></a><span data-ttu-id="7ceba-102">单一登录：事件 10665</span><span class="sxs-lookup"><span data-stu-id="7ceba-102">Single Sign-On: Event 10665</span></span>
## <a name="details"></a><span data-ttu-id="7ceba-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7ceba-103">Details</span></span>  

|                 |                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7ceba-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7ceba-104">Product Name</span></span>   |                                               <span data-ttu-id="7ceba-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7ceba-105">Enterprise Single Sign-On</span></span>                                                |
| <span data-ttu-id="7ceba-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="7ceba-106">Product Version</span></span> |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    <span data-ttu-id="7ceba-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7ceba-107">Event ID</span></span>     |                                                         <span data-ttu-id="7ceba-108">10665</span><span class="sxs-lookup"><span data-stu-id="7ceba-108">10665</span></span>                                                          |
|  <span data-ttu-id="7ceba-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7ceba-109">Event Source</span></span>   |                                                         <span data-ttu-id="7ceba-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7ceba-110">ENTSSO</span></span>                                                         |
|    <span data-ttu-id="7ceba-111">组件</span><span class="sxs-lookup"><span data-stu-id="7ceba-111">Component</span></span>    |                                                          <span data-ttu-id="7ceba-112">N\A</span><span class="sxs-lookup"><span data-stu-id="7ceba-112">N\A</span></span>                                                           |
|  <span data-ttu-id="7ceba-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7ceba-113">Symbolic Name</span></span>  |                                                 <span data-ttu-id="7ceba-114">SSO_WARN_NO_PROPERTIES</span><span class="sxs-lookup"><span data-stu-id="7ceba-114">SSO_WARN_NO_PROPERTIES</span></span>                                                 |
|  <span data-ttu-id="7ceba-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7ceba-115">Message Text</span></span>   | <span data-ttu-id="7ceba-116">读取密码同步适配器属性时出错。</span><span class="sxs-lookup"><span data-stu-id="7ceba-116">Error reading password sync adapter properties.</span></span> <span data-ttu-id="7ceba-117">使用 defaults.%r</span><span class="sxs-lookup"><span data-stu-id="7ceba-117">Using defaults.%r</span></span><br /><br /> <span data-ttu-id="7ceba-118">适配器: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7ceba-118">Adapter: %1%r</span></span><br /><br /> <span data-ttu-id="7ceba-119">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="7ceba-119">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="7ceba-120">解释</span><span class="sxs-lookup"><span data-stu-id="7ceba-120">Explanation</span></span>  
 <span data-ttu-id="7ceba-121">此警告事件表明时读取默认密码同步适配器属性时出错。</span><span class="sxs-lookup"><span data-stu-id="7ceba-121">This Warning event indicates that there was an error reading the default password sync adapter properties.</span></span> <span data-ttu-id="7ceba-122">每个密码同步适配器都有与之关联的配置属性。</span><span class="sxs-lookup"><span data-stu-id="7ceba-122">Each password sync adapter has configuration properties associated with it.</span></span> <span data-ttu-id="7ceba-123">这些属性存储在 SSO 配置存储区中，并创建密码同步适配器时由 SSO 命令行工具或 SSO 管理 MMC 创建。</span><span class="sxs-lookup"><span data-stu-id="7ceba-123">These properties are stored in the SSO config store and are created by the SSO command line tools or the SSO Admin MMC when the password sync adapter is created.</span></span>  <span data-ttu-id="7ceba-124">可能会缺少某些属性如果密码同步适配器创建了任何其他方法，则可以发出此错误。</span><span class="sxs-lookup"><span data-stu-id="7ceba-124">There can be missing properties if the password sync adapter was created by any other means, then this error can be issued.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7ceba-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="7ceba-125">User Action</span></span>  
 <span data-ttu-id="7ceba-126">若要解决此警告，请执行一个或多个以下操作：</span><span class="sxs-lookup"><span data-stu-id="7ceba-126">To resolve this warning, do one or more of the following:</span></span>  

-   <span data-ttu-id="7ceba-127">验证密码同步适配器属性。</span><span class="sxs-lookup"><span data-stu-id="7ceba-127">Verify password sync adapter properties.</span></span>  

-   <span data-ttu-id="7ceba-128">重新创建密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="7ceba-128">Recreate the password sync adapter</span></span>  

## <a name="more-info"></a><span data-ttu-id="7ceba-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="7ceba-129">More info</span></span>

- <span data-ttu-id="7ceba-130">**密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="7ceba-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="7ceba-131">密码同步</span><span class="sxs-lookup"><span data-stu-id="7ceba-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
