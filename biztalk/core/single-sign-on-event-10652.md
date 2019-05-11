---
title: 单一登录：Event 10652 | Microsoft Docs
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
ms.openlocfilehash: df470103391e41cdac109e5b58af0514d402f04a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397651"
---
# <a name="single-sign-on-event-10652"></a><span data-ttu-id="57ec3-102">单一登录：事件 10652</span><span class="sxs-lookup"><span data-stu-id="57ec3-102">Single Sign-On: Event 10652</span></span>
## <a name="details"></a><span data-ttu-id="57ec3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="57ec3-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="57ec3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="57ec3-104">Product Name</span></span>   |                         <span data-ttu-id="57ec3-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="57ec3-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="57ec3-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="57ec3-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="57ec3-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="57ec3-107">Event ID</span></span>     |                                   <span data-ttu-id="57ec3-108">10652</span><span class="sxs-lookup"><span data-stu-id="57ec3-108">10652</span></span>                                   |
|  <span data-ttu-id="57ec3-109">事件源</span><span class="sxs-lookup"><span data-stu-id="57ec3-109">Event Source</span></span>   |                                  <span data-ttu-id="57ec3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="57ec3-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="57ec3-111">组件</span><span class="sxs-lookup"><span data-stu-id="57ec3-111">Component</span></span>    |                                    <span data-ttu-id="57ec3-112">N\A</span><span class="sxs-lookup"><span data-stu-id="57ec3-112">N\A</span></span>                                    |
|  <span data-ttu-id="57ec3-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="57ec3-113">Symbolic Name</span></span>  |                   <span data-ttu-id="57ec3-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="57ec3-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span></span>                    |
|  <span data-ttu-id="57ec3-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="57ec3-115">Message Text</span></span>   | <span data-ttu-id="57ec3-116">密码同步服务无法 initialize.%r</span><span class="sxs-lookup"><span data-stu-id="57ec3-116">Password sync services failed to initialize.%r</span></span><br /><br /> <span data-ttu-id="57ec3-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="57ec3-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="57ec3-118">解释</span><span class="sxs-lookup"><span data-stu-id="57ec3-118">Explanation</span></span>  
 <span data-ttu-id="57ec3-119">此错误事件表示密码同步服务无法启动由于出现异常。</span><span class="sxs-lookup"><span data-stu-id="57ec3-119">This Error event indicates that the Password Sync Service could not start due to an exception.</span></span>  

## <a name="user-action"></a><span data-ttu-id="57ec3-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="57ec3-120">User Action</span></span>  
 <span data-ttu-id="57ec3-121">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="57ec3-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="57ec3-122">检查应用程序和系统事件日志中的 ENTSSO 或其他服务的相关错误。</span><span class="sxs-lookup"><span data-stu-id="57ec3-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="57ec3-123">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="57ec3-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="57ec3-124">密码同步</span><span class="sxs-lookup"><span data-stu-id="57ec3-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
