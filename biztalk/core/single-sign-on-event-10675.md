---
title: 单一登录：Event 10675 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb383c6d-0c46-4752-b8f6-200e1cd9763e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16cb93d1247bb4db43cba36ea99cc6a2bbc0c7ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397471"
---
# <a name="single-sign-on-event-10675"></a><span data-ttu-id="015e0-102">单一登录：事件 10675</span><span class="sxs-lookup"><span data-stu-id="015e0-102">Single Sign-On: Event 10675</span></span>
## <a name="details"></a><span data-ttu-id="015e0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="015e0-103">Details</span></span>  

|                 |                                                                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="015e0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="015e0-104">Product Name</span></span>   |                                                                                        <span data-ttu-id="015e0-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="015e0-105">Enterprise Single Sign-On</span></span>                                                                                         |
| <span data-ttu-id="015e0-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="015e0-106">Product Version</span></span> |                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                        |
|    <span data-ttu-id="015e0-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="015e0-107">Event ID</span></span>     |                                                                                                  <span data-ttu-id="015e0-108">10675</span><span class="sxs-lookup"><span data-stu-id="015e0-108">10675</span></span>                                                                                                   |
|  <span data-ttu-id="015e0-109">事件源</span><span class="sxs-lookup"><span data-stu-id="015e0-109">Event Source</span></span>   |                                                                                                  <span data-ttu-id="015e0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="015e0-110">ENTSSO</span></span>                                                                                                  |
|    <span data-ttu-id="015e0-111">组件</span><span class="sxs-lookup"><span data-stu-id="015e0-111">Component</span></span>    |                                                                                                   <span data-ttu-id="015e0-112">N\A</span><span class="sxs-lookup"><span data-stu-id="015e0-112">N\A</span></span>                                                                                                    |
|  <span data-ttu-id="015e0-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="015e0-113">Symbolic Name</span></span>  |                                                                                      <span data-ttu-id="015e0-114">SSO_INFO_WINDOWS_PASSWORD_SET</span><span class="sxs-lookup"><span data-stu-id="015e0-114">SSO_INFO_WINDOWS_PASSWORD_SET</span></span>                                                                                       |
|  <span data-ttu-id="015e0-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="015e0-115">Message Text</span></span>   | <span data-ttu-id="015e0-116">SSO database.%r 中已成功更新 Windows 密码</span><span class="sxs-lookup"><span data-stu-id="015e0-116">The Windows password was successfully updated in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="015e0-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="015e0-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="015e0-118">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="015e0-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="015e0-119">应用程序名称: %3 %r</span><span class="sxs-lookup"><span data-stu-id="015e0-119">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="015e0-120">外部帐户： %4</span><span class="sxs-lookup"><span data-stu-id="015e0-120">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="015e0-121">解释</span><span class="sxs-lookup"><span data-stu-id="015e0-121">Explanation</span></span>  
 <span data-ttu-id="015e0-122">此信息事件表明 SSO 数据库中已成功更新 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="015e0-122">This Information event indicates that the Windows password was successfully updated in the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="015e0-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="015e0-123">User Action</span></span>  

- <span data-ttu-id="015e0-124">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="015e0-124">No user action is necessary.</span></span>  

  <span data-ttu-id="015e0-125">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="015e0-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="015e0-126">密码同步</span><span class="sxs-lookup"><span data-stu-id="015e0-126">Password Synchronization</span></span>](../core/password-synchronization2.md)
