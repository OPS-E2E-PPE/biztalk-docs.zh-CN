---
title: 单一登录： 事件 10652 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae7fe452-bcec-4722-8ec6-78d4fe462a0a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2e27c678f2c031c642107cd770566f92d7ca708
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985742"
---
# <a name="single-sign-on-event-10652"></a><span data-ttu-id="e911c-102">单一登录： 事件 10652</span><span class="sxs-lookup"><span data-stu-id="e911c-102">Single Sign-On: Event 10652</span></span>
## <a name="details"></a><span data-ttu-id="e911c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e911c-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="e911c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e911c-104">Product Name</span></span>   |                         <span data-ttu-id="e911c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e911c-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="e911c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e911c-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="e911c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e911c-107">Event ID</span></span>     |                                   <span data-ttu-id="e911c-108">10652</span><span class="sxs-lookup"><span data-stu-id="e911c-108">10652</span></span>                                   |
|  <span data-ttu-id="e911c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e911c-109">Event Source</span></span>   |                                  <span data-ttu-id="e911c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e911c-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="e911c-111">组件</span><span class="sxs-lookup"><span data-stu-id="e911c-111">Component</span></span>    |                                    <span data-ttu-id="e911c-112">N\A</span><span class="sxs-lookup"><span data-stu-id="e911c-112">N\A</span></span>                                    |
|  <span data-ttu-id="e911c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e911c-113">Symbolic Name</span></span>  |                   <span data-ttu-id="e911c-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="e911c-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span></span>                    |
|  <span data-ttu-id="e911c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e911c-115">Message Text</span></span>   | <span data-ttu-id="e911c-116">密码同步服务初始化失败。%r</span><span class="sxs-lookup"><span data-stu-id="e911c-116">Password sync services failed to initialize.%r</span></span><br /><br /> <span data-ttu-id="e911c-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="e911c-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="e911c-118">解释</span><span class="sxs-lookup"><span data-stu-id="e911c-118">Explanation</span></span>  
 <span data-ttu-id="e911c-119">此错误事件表示，由于发生异常，密码同步服务无法启动。</span><span class="sxs-lookup"><span data-stu-id="e911c-119">This Error event indicates that the Password Sync Service could not start due to an exception.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e911c-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="e911c-120">User Action</span></span>  
 <span data-ttu-id="e911c-121">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e911c-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="e911c-122">检查应用程序和系统事件日志，以了解 ENTSSO 或其他服务的相关错误。</span><span class="sxs-lookup"><span data-stu-id="e911c-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="e911c-123">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="e911c-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="e911c-124">密码同步</span><span class="sxs-lookup"><span data-stu-id="e911c-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
