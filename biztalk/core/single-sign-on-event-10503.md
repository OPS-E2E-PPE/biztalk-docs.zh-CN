---
title: 单一登录：Event 10503 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04292ae8-8daf-4f5a-837e-fe5dfcd02b10
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72b82421d4c70833f085b8e95c75c60cb1944545
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243481"
---
# <a name="single-sign-on-event-10503"></a><span data-ttu-id="edd16-102">单一登录：事件 10503</span><span class="sxs-lookup"><span data-stu-id="edd16-102">Single Sign-On: Event 10503</span></span>
## <a name="details"></a><span data-ttu-id="edd16-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="edd16-103">Details</span></span>  

|                 |                                                               |
|-----------------|---------------------------------------------------------------|
|  <span data-ttu-id="edd16-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="edd16-104">Product Name</span></span>   |                   <span data-ttu-id="edd16-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="edd16-105">Enterprise Single Sign-On</span></span>                   |
| <span data-ttu-id="edd16-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="edd16-106">Product Version</span></span> |  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="edd16-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="edd16-107">Event ID</span></span>     |                             <span data-ttu-id="edd16-108">10503</span><span class="sxs-lookup"><span data-stu-id="edd16-108">10503</span></span>                             |
|  <span data-ttu-id="edd16-109">事件源</span><span class="sxs-lookup"><span data-stu-id="edd16-109">Event Source</span></span>   |                            <span data-ttu-id="edd16-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="edd16-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="edd16-111">组件</span><span class="sxs-lookup"><span data-stu-id="edd16-111">Component</span></span>    |                              <span data-ttu-id="edd16-112">N\A</span><span class="sxs-lookup"><span data-stu-id="edd16-112">N\A</span></span>                              |
|  <span data-ttu-id="edd16-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="edd16-113">Symbolic Name</span></span>  |                <span data-ttu-id="edd16-114">SSO_ERROR_SERVICE_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="edd16-114">SSO_ERROR_SERVICE_START_FAILED</span></span>                 |
|  <span data-ttu-id="edd16-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="edd16-115">Message Text</span></span>   | <span data-ttu-id="edd16-116">SSO 服务无法 start.%r</span><span class="sxs-lookup"><span data-stu-id="edd16-116">The SSO service failed to start.%r</span></span><br /><br /> <span data-ttu-id="edd16-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="edd16-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="edd16-118">解释</span><span class="sxs-lookup"><span data-stu-id="edd16-118">Explanation</span></span>  
 <span data-ttu-id="edd16-119">此错误事件表示 ENTSSO 服务无法启动由于出现异常。</span><span class="sxs-lookup"><span data-stu-id="edd16-119">This Error event indicates that the ENTSSO Service could not start due to an exception.</span></span>  

## <a name="user-action"></a><span data-ttu-id="edd16-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="edd16-120">User Action</span></span>  
 <span data-ttu-id="edd16-121">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="edd16-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="edd16-122">检查应用程序和系统事件日志中的 ENTSSO 或其他服务的相关错误。</span><span class="sxs-lookup"><span data-stu-id="edd16-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="edd16-123">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="edd16-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="edd16-124">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="edd16-124">Using SSO</span></span>](../core/using-sso.md)
