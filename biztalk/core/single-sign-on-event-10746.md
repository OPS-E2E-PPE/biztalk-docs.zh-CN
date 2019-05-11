---
title: 单一登录：Event 10746 | Microsoft Docs
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
ms.openlocfilehash: 19bef7a20062761f1d019b786bd96581b302bec4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395495"
---
# <a name="single-sign-on-event-10746"></a><span data-ttu-id="bf9bd-102">单一登录：事件 10746</span><span class="sxs-lookup"><span data-stu-id="bf9bd-102">Single Sign-On: Event 10746</span></span>
## <a name="details"></a><span data-ttu-id="bf9bd-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="bf9bd-103">Details</span></span>  

|                 |                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bf9bd-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="bf9bd-104">Product Name</span></span>   |                                                           <span data-ttu-id="bf9bd-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="bf9bd-105">Enterprise Single Sign-On</span></span>                                                           |
| <span data-ttu-id="bf9bd-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="bf9bd-106">Product Version</span></span> |                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                           |
|    <span data-ttu-id="bf9bd-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bf9bd-107">Event ID</span></span>     |                                                                     <span data-ttu-id="bf9bd-108">10746</span><span class="sxs-lookup"><span data-stu-id="bf9bd-108">10746</span></span>                                                                     |
|  <span data-ttu-id="bf9bd-109">事件源</span><span class="sxs-lookup"><span data-stu-id="bf9bd-109">Event Source</span></span>   |                                                                    <span data-ttu-id="bf9bd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bf9bd-110">ENTSSO</span></span>                                                                     |
|    <span data-ttu-id="bf9bd-111">组件</span><span class="sxs-lookup"><span data-stu-id="bf9bd-111">Component</span></span>    |                                                                      <span data-ttu-id="bf9bd-112">N\A</span><span class="sxs-lookup"><span data-stu-id="bf9bd-112">N\A</span></span>                                                                      |
|  <span data-ttu-id="bf9bd-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="bf9bd-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="bf9bd-114">SSO_WARN_PASSWORD_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="bf9bd-114">SSO_WARN_PASSWORD_EXPIRED</span></span>                                                           |
|  <span data-ttu-id="bf9bd-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="bf9bd-115">Message Text</span></span>   | <span data-ttu-id="bf9bd-116">外部帐户的密码已 expired.%r</span><span class="sxs-lookup"><span data-stu-id="bf9bd-116">The password for the external account has expired.%r</span></span><br /><br /> <span data-ttu-id="bf9bd-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bf9bd-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="bf9bd-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="bf9bd-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="bf9bd-119">外部帐户： %3</span><span class="sxs-lookup"><span data-stu-id="bf9bd-119">External Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="bf9bd-120">解释</span><span class="sxs-lookup"><span data-stu-id="bf9bd-120">Explanation</span></span>  
 <span data-ttu-id="bf9bd-121">此警告事件表明外部帐户的密码已过期。</span><span class="sxs-lookup"><span data-stu-id="bf9bd-121">This Warning event indicates that the password for the external account has expired.</span></span>  

## <a name="user-action"></a><span data-ttu-id="bf9bd-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="bf9bd-122">User Action</span></span>  
 <span data-ttu-id="bf9bd-123">若要解决此警告，请检查系统和应用程序事件日志中的关联错误。</span><span class="sxs-lookup"><span data-stu-id="bf9bd-123">To resolve this warning, check the system and application event logs for associated errors.</span></span>    

## <a name="more-info"></a><span data-ttu-id="bf9bd-124">详细信息</span><span class="sxs-lookup"><span data-stu-id="bf9bd-124">More info</span></span>
<span data-ttu-id="bf9bd-125">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="bf9bd-125">For more information, see the following resources:</span></span>  

- <span data-ttu-id="bf9bd-126">**密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="bf9bd-126">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  

- [<span data-ttu-id="bf9bd-127">密码同步</span><span class="sxs-lookup"><span data-stu-id="bf9bd-127">Password Synchronization</span></span>](../core/password-synchronization2.md)
