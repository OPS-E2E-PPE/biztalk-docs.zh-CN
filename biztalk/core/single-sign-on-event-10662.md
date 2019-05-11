---
title: 单一登录：Event 10662 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe707f23-ad54-4adb-a755-8d706a75efa4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ed63088692545e73c5804b5c0f60d59fd36f6f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397600"
---
# <a name="single-sign-on-event-10662"></a><span data-ttu-id="cabf1-102">单一登录：事件 10662</span><span class="sxs-lookup"><span data-stu-id="cabf1-102">Single Sign-On: Event 10662</span></span>
## <a name="details"></a><span data-ttu-id="cabf1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cabf1-103">Details</span></span>  

|                 |                                                                                                                                                                                   |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cabf1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cabf1-104">Product Name</span></span>   |                                                                             <span data-ttu-id="cabf1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="cabf1-105">Enterprise Single Sign-On</span></span>                                                                             |
| <span data-ttu-id="cabf1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="cabf1-106">Product Version</span></span> |                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    <span data-ttu-id="cabf1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cabf1-107">Event ID</span></span>     |                                                                                       <span data-ttu-id="cabf1-108">10662</span><span class="sxs-lookup"><span data-stu-id="cabf1-108">10662</span></span>                                                                                       |
|  <span data-ttu-id="cabf1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="cabf1-109">Event Source</span></span>   |                                                                                      <span data-ttu-id="cabf1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cabf1-110">ENTSSO</span></span>                                                                                       |
|    <span data-ttu-id="cabf1-111">组件</span><span class="sxs-lookup"><span data-stu-id="cabf1-111">Component</span></span>    |                                                                                        <span data-ttu-id="cabf1-112">N\A</span><span class="sxs-lookup"><span data-stu-id="cabf1-112">N\A</span></span>                                                                                        |
|  <span data-ttu-id="cabf1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="cabf1-113">Symbolic Name</span></span>  |                                                                     <span data-ttu-id="cabf1-114">SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="cabf1-114">SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED</span></span>                                                                     |
|  <span data-ttu-id="cabf1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="cabf1-115">Message Text</span></span>   | <span data-ttu-id="cabf1-116">Windows 密码更改已从 PCNS.%r 中收到</span><span class="sxs-lookup"><span data-stu-id="cabf1-116">A Windows password change was received from PCNS.%r</span></span><br /><br /> <span data-ttu-id="cabf1-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="cabf1-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="cabf1-118">Windows 帐户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="cabf1-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="cabf1-119">其他数据: %3 %r</span><span class="sxs-lookup"><span data-stu-id="cabf1-119">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="cabf1-120">客户端用户： %4</span><span class="sxs-lookup"><span data-stu-id="cabf1-120">Client User: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="cabf1-121">解释</span><span class="sxs-lookup"><span data-stu-id="cabf1-121">Explanation</span></span>  
 <span data-ttu-id="cabf1-122">此信息事件表明，从密码更改通知服务收到 Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="cabf1-122">This Information event indicates that a Windows password change was received from Password Change Notification Services.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cabf1-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="cabf1-123">User Action</span></span>  

-   <span data-ttu-id="cabf1-124">不不需要任何用户操作。</span><span class="sxs-lookup"><span data-stu-id="cabf1-124">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="cabf1-125">详细信息</span><span class="sxs-lookup"><span data-stu-id="cabf1-125">More info</span></span>

- [<span data-ttu-id="cabf1-126">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="cabf1-126">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  

- <span data-ttu-id="cabf1-127">**密码同步适配器属性：选项** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="cabf1-127">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
