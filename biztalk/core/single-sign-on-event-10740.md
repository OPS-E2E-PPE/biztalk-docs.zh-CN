---
title: 单一登录：Event 10740 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e8521e7-32af-4a58-8b1a-66ea1d13f1e1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db19b81cb024ff6dfee2196cdefc33f8f977dea9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291751"
---
# <a name="single-sign-on-event-10740"></a><span data-ttu-id="26939-102">单一登录：事件 10740</span><span class="sxs-lookup"><span data-stu-id="26939-102">Single Sign-On: Event 10740</span></span>
## <a name="details"></a><span data-ttu-id="26939-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="26939-103">Details</span></span>  

|                 |                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="26939-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="26939-104">Product Name</span></span>   |                                                                 <span data-ttu-id="26939-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="26939-105">Enterprise Single Sign-On</span></span>                                                                  |
| <span data-ttu-id="26939-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="26939-106">Product Version</span></span> |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                 |
|    <span data-ttu-id="26939-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="26939-107">Event ID</span></span>     |                                                                           <span data-ttu-id="26939-108">10740</span><span class="sxs-lookup"><span data-stu-id="26939-108">10740</span></span>                                                                            |
|  <span data-ttu-id="26939-109">事件源</span><span class="sxs-lookup"><span data-stu-id="26939-109">Event Source</span></span>   |                                                                           <span data-ttu-id="26939-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="26939-110">ENTSSO</span></span>                                                                           |
|    <span data-ttu-id="26939-111">组件</span><span class="sxs-lookup"><span data-stu-id="26939-111">Component</span></span>    |                                                                            <span data-ttu-id="26939-112">N\A</span><span class="sxs-lookup"><span data-stu-id="26939-112">N\A</span></span>                                                                             |
|  <span data-ttu-id="26939-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="26939-113">Symbolic Name</span></span>  |                                                               <span data-ttu-id="26939-114">SSO_WARN_INVALID_WINDOWS_USER</span><span class="sxs-lookup"><span data-stu-id="26939-114">SSO_WARN_INVALID_WINDOWS_USER</span></span>                                                                |
|  <span data-ttu-id="26939-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="26939-115">Message Text</span></span>   | <span data-ttu-id="26939-116">Windows 帐户不是有效的应用程序 update.%r</span><span class="sxs-lookup"><span data-stu-id="26939-116">The Windows Account is not valid for application update.%r</span></span><br /><br /> <span data-ttu-id="26939-117">应用程序名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="26939-117">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="26939-118">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="26939-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="26939-119">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="26939-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="26939-120">解释</span><span class="sxs-lookup"><span data-stu-id="26939-120">Explanation</span></span>  
 <span data-ttu-id="26939-121">此警告事件表示 （事件消息中指定） 的 Windows 帐户对于应用程序更新无效。</span><span class="sxs-lookup"><span data-stu-id="26939-121">This Warning event indicates that the Windows Account (specified in the event message) is not valid for application update.</span></span> <span data-ttu-id="26939-122">更改主机组应用程序的 Windows 帐户时会发生该错误。</span><span class="sxs-lookup"><span data-stu-id="26939-122">This can occur when changing the Windows account for a Host Group application.</span></span> <span data-ttu-id="26939-123">主机组应用程序用于实现单一登录从外部系统到 Windows 系统。</span><span class="sxs-lookup"><span data-stu-id="26939-123">Host Group applications are used for single sign-on from external systems to Windows systems.</span></span> <span data-ttu-id="26939-124">它们可以将一组外部用户映射到单个 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="26939-124">They can map a set of external users to a single Windows account.</span></span> <span data-ttu-id="26939-125">在应用程序的应用程序用户字段中定义映射到 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="26939-125">The Windows account they are mapped to is defined in the Application Users field of the application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="26939-126">用户操作</span><span class="sxs-lookup"><span data-stu-id="26939-126">User Action</span></span>  
 <span data-ttu-id="26939-127">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="26939-127">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="26939-128">检查 Windows 帐户正在使用无效。</span><span class="sxs-lookup"><span data-stu-id="26939-128">Check that the Windows account your are using is valid.</span></span>  

- <span data-ttu-id="26939-129">重新创建具有正确的 Windows 帐户属性的 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="26939-129">Recreate the Windows account with the correct Windows account properties.</span></span>  

  <span data-ttu-id="26939-130">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="26939-130">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="26939-131">密码同步</span><span class="sxs-lookup"><span data-stu-id="26939-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
