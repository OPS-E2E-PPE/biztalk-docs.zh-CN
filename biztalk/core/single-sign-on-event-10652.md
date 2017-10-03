---
title: "单一登录： 事件 10652 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae7fe452-bcec-4722-8ec6-78d4fe462a0a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62066b2fbbc47d07fa57f047313ed5ed8cda47d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10652"></a><span data-ttu-id="20b8a-102">单一登录： 事件 10652</span><span class="sxs-lookup"><span data-stu-id="20b8a-102">Single Sign-On: Event 10652</span></span>
## <a name="details"></a><span data-ttu-id="20b8a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="20b8a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="20b8a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="20b8a-104">Product Name</span></span>|<span data-ttu-id="20b8a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="20b8a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="20b8a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="20b8a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="20b8a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="20b8a-107">Event ID</span></span>|<span data-ttu-id="20b8a-108">10652</span><span class="sxs-lookup"><span data-stu-id="20b8a-108">10652</span></span>|  
|<span data-ttu-id="20b8a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="20b8a-109">Event Source</span></span>|<span data-ttu-id="20b8a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="20b8a-110">ENTSSO</span></span>|  
|<span data-ttu-id="20b8a-111">组件</span><span class="sxs-lookup"><span data-stu-id="20b8a-111">Component</span></span>|<span data-ttu-id="20b8a-112">N\A</span><span class="sxs-lookup"><span data-stu-id="20b8a-112">N\A</span></span>|  
|<span data-ttu-id="20b8a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="20b8a-113">Symbolic Name</span></span>|<span data-ttu-id="20b8a-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="20b8a-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span></span>|  
|<span data-ttu-id="20b8a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="20b8a-115">Message Text</span></span>|<span data-ttu-id="20b8a-116">密码同步服务初始化失败。%r</span><span class="sxs-lookup"><span data-stu-id="20b8a-116">Password sync services failed to initialize.%r</span></span><br /><br /> <span data-ttu-id="20b8a-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="20b8a-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="20b8a-118">解释</span><span class="sxs-lookup"><span data-stu-id="20b8a-118">Explanation</span></span>  
 <span data-ttu-id="20b8a-119">此错误事件表示，由于发生异常，密码同步服务无法启动。</span><span class="sxs-lookup"><span data-stu-id="20b8a-119">This Error event indicates that the Password Sync Service could not start due to an exception.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="20b8a-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="20b8a-120">User Action</span></span>  
 <span data-ttu-id="20b8a-121">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="20b8a-121">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="20b8a-122">检查应用程序和系统事件日志，以了解 ENTSSO 或其他服务的相关错误。</span><span class="sxs-lookup"><span data-stu-id="20b8a-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  
  
 <span data-ttu-id="20b8a-123">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="20b8a-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="20b8a-124">密码同步</span><span class="sxs-lookup"><span data-stu-id="20b8a-124">Password Synchronization</span></span>](../core/password-synchronization2.md)