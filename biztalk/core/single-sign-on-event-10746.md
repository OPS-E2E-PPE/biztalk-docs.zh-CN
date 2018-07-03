---
title: 单一登录： 事件 10746 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8189120b-923a-4c88-937e-f06565bcac56
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3f4fa77909ba53e16d3dffd31073ff93e233ed5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998862"
---
# <a name="single-sign-on-event-10746"></a><span data-ttu-id="909b7-102">单一登录： 事件 10746</span><span class="sxs-lookup"><span data-stu-id="909b7-102">Single Sign-On: Event 10746</span></span>
## <a name="details"></a><span data-ttu-id="909b7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="909b7-103">Details</span></span>  

|                 |                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="909b7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="909b7-104">Product Name</span></span>   |                                                           <span data-ttu-id="909b7-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="909b7-105">Enterprise Single Sign-On</span></span>                                                           |
| <span data-ttu-id="909b7-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="909b7-106">Product Version</span></span> |                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                           |
|    <span data-ttu-id="909b7-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="909b7-107">Event ID</span></span>     |                                                                     <span data-ttu-id="909b7-108">10746</span><span class="sxs-lookup"><span data-stu-id="909b7-108">10746</span></span>                                                                     |
|  <span data-ttu-id="909b7-109">事件源</span><span class="sxs-lookup"><span data-stu-id="909b7-109">Event Source</span></span>   |                                                                    <span data-ttu-id="909b7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="909b7-110">ENTSSO</span></span>                                                                     |
|    <span data-ttu-id="909b7-111">组件</span><span class="sxs-lookup"><span data-stu-id="909b7-111">Component</span></span>    |                                                                      <span data-ttu-id="909b7-112">N\A</span><span class="sxs-lookup"><span data-stu-id="909b7-112">N\A</span></span>                                                                      |
|  <span data-ttu-id="909b7-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="909b7-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="909b7-114">SSO_WARN_PASSWORD_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="909b7-114">SSO_WARN_PASSWORD_EXPIRED</span></span>                                                           |
|  <span data-ttu-id="909b7-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="909b7-115">Message Text</span></span>   | <span data-ttu-id="909b7-116">外部帐户密码已过期。%r</span><span class="sxs-lookup"><span data-stu-id="909b7-116">The password for the external account has expired.%r</span></span><br /><br /> <span data-ttu-id="909b7-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="909b7-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="909b7-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="909b7-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="909b7-119">外部帐户： %3</span><span class="sxs-lookup"><span data-stu-id="909b7-119">External Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="909b7-120">解释</span><span class="sxs-lookup"><span data-stu-id="909b7-120">Explanation</span></span>  
 <span data-ttu-id="909b7-121">此警告事件表明外部帐户的密码已过期。</span><span class="sxs-lookup"><span data-stu-id="909b7-121">This Warning event indicates that the password for the external account has expired.</span></span>  

## <a name="user-action"></a><span data-ttu-id="909b7-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="909b7-122">User Action</span></span>  
 <span data-ttu-id="909b7-123">若要解决此警告，请检查系统和应用程序事件日志中的关联错误。</span><span class="sxs-lookup"><span data-stu-id="909b7-123">To resolve this warning, check the system and application event logs for associated errors.</span></span>    

## <a name="more-info"></a><span data-ttu-id="909b7-124">详细信息</span><span class="sxs-lookup"><span data-stu-id="909b7-124">More info</span></span>
<span data-ttu-id="909b7-125">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="909b7-125">For more information, see the following resources:</span></span>  

- <span data-ttu-id="909b7-126">**密码同步适配器属性： 选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="909b7-126">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  

- [<span data-ttu-id="909b7-127">密码同步</span><span class="sxs-lookup"><span data-stu-id="909b7-127">Password Synchronization</span></span>](../core/password-synchronization2.md)
