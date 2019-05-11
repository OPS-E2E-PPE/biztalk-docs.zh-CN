---
title: 单一登录：Event 10666 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 103947bb-e843-4427-a28a-1cceec90e2ae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 921f11f422e4707d81a9387cd9606c3dfd3f337d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397550"
---
# <a name="single-sign-on-event-10666"></a><span data-ttu-id="7a324-102">单一登录：事件 10666</span><span class="sxs-lookup"><span data-stu-id="7a324-102">Single Sign-On: Event 10666</span></span>
## <a name="details"></a><span data-ttu-id="7a324-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7a324-103">Details</span></span>  

|                 |                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7a324-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7a324-104">Product Name</span></span>   |                                                                         <span data-ttu-id="7a324-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7a324-105">Enterprise Single Sign-On</span></span>                                                                          |
| <span data-ttu-id="7a324-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="7a324-106">Product Version</span></span> |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                         |
|    <span data-ttu-id="7a324-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7a324-107">Event ID</span></span>     |                                                                                   <span data-ttu-id="7a324-108">10666</span><span class="sxs-lookup"><span data-stu-id="7a324-108">10666</span></span>                                                                                    |
|  <span data-ttu-id="7a324-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7a324-109">Event Source</span></span>   |                                                                                   <span data-ttu-id="7a324-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7a324-110">ENTSSO</span></span>                                                                                   |
|    <span data-ttu-id="7a324-111">组件</span><span class="sxs-lookup"><span data-stu-id="7a324-111">Component</span></span>    |                                                                                    <span data-ttu-id="7a324-112">N\A</span><span class="sxs-lookup"><span data-stu-id="7a324-112">N\A</span></span>                                                                                     |
|  <span data-ttu-id="7a324-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7a324-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="7a324-114">SSO_INFO_DAMPED_EXTERNAL_PASSWORD_CHANGE</span><span class="sxs-lookup"><span data-stu-id="7a324-114">SSO_INFO_DAMPED_EXTERNAL_PASSWORD_CHANGE</span></span>                                                                  |
|  <span data-ttu-id="7a324-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7a324-115">Message Text</span></span>   | <span data-ttu-id="7a324-116">外部密码更改被阻止 （检测为重复 discarded).%r，因而</span><span class="sxs-lookup"><span data-stu-id="7a324-116">An external password change was damped (detected as a duplicate and discarded).%r</span></span><br /><br /> <span data-ttu-id="7a324-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7a324-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="7a324-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7a324-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="7a324-119">外部帐户： %3</span><span class="sxs-lookup"><span data-stu-id="7a324-119">External Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="7a324-120">解释</span><span class="sxs-lookup"><span data-stu-id="7a324-120">Explanation</span></span>  
 <span data-ttu-id="7a324-121">此信息事件表明外部密码更改已确定为不重复并丢弃。</span><span class="sxs-lookup"><span data-stu-id="7a324-121">This Information event indicates that an external password change was determined to be a duplicate and discarded.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7a324-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="7a324-122">User Action</span></span>  

- <span data-ttu-id="7a324-123">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="7a324-123">No user action is necessary.</span></span>  

  <span data-ttu-id="7a324-124">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="7a324-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="7a324-125">密码同步</span><span class="sxs-lookup"><span data-stu-id="7a324-125">Password Synchronization</span></span>](../core/password-synchronization2.md)
