---
title: 单一登录： 事件 10503 |Microsoft Docs
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
ms.openlocfilehash: b90af01551359b5caa1a5404facc9e3fece95673
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990710"
---
# <a name="single-sign-on-event-10503"></a><span data-ttu-id="7373f-102">单一登录： 事件 10503</span><span class="sxs-lookup"><span data-stu-id="7373f-102">Single Sign-On: Event 10503</span></span>
## <a name="details"></a><span data-ttu-id="7373f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7373f-103">Details</span></span>  

|                 |                                                               |
|-----------------|---------------------------------------------------------------|
|  <span data-ttu-id="7373f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7373f-104">Product Name</span></span>   |                   <span data-ttu-id="7373f-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7373f-105">Enterprise Single Sign-On</span></span>                   |
| <span data-ttu-id="7373f-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="7373f-106">Product Version</span></span> |  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="7373f-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7373f-107">Event ID</span></span>     |                             <span data-ttu-id="7373f-108">10503</span><span class="sxs-lookup"><span data-stu-id="7373f-108">10503</span></span>                             |
|  <span data-ttu-id="7373f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7373f-109">Event Source</span></span>   |                            <span data-ttu-id="7373f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7373f-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="7373f-111">组件</span><span class="sxs-lookup"><span data-stu-id="7373f-111">Component</span></span>    |                              <span data-ttu-id="7373f-112">N\A</span><span class="sxs-lookup"><span data-stu-id="7373f-112">N\A</span></span>                              |
|  <span data-ttu-id="7373f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7373f-113">Symbolic Name</span></span>  |                <span data-ttu-id="7373f-114">SSO_ERROR_SERVICE_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="7373f-114">SSO_ERROR_SERVICE_START_FAILED</span></span>                 |
|  <span data-ttu-id="7373f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7373f-115">Message Text</span></span>   | <span data-ttu-id="7373f-116">无法启动 SSO 服务。%r</span><span class="sxs-lookup"><span data-stu-id="7373f-116">The SSO service failed to start.%r</span></span><br /><br /> <span data-ttu-id="7373f-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="7373f-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="7373f-118">解释</span><span class="sxs-lookup"><span data-stu-id="7373f-118">Explanation</span></span>  
 <span data-ttu-id="7373f-119">此错误事件表示由于出现异常导致无法启动 ENTSSO 服务。</span><span class="sxs-lookup"><span data-stu-id="7373f-119">This Error event indicates that the ENTSSO Service could not start due to an exception.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7373f-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="7373f-120">User Action</span></span>  
 <span data-ttu-id="7373f-121">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7373f-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="7373f-122">检查应用程序和系统事件日志，以了解 ENTSSO 或其他服务的相关错误。</span><span class="sxs-lookup"><span data-stu-id="7373f-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="7373f-123">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="7373f-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="7373f-124">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="7373f-124">Using SSO</span></span>](../core/using-sso.md)
