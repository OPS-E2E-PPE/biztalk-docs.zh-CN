---
title: 单一登录：Event 10527 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40995ad8-9f74-4e96-863d-427e23025ba1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57f5ac8452d96e3af54ff4d5cfc21f6664435bc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262503"
---
# <a name="single-sign-on-event-10527"></a><span data-ttu-id="bcb83-102">单一登录：事件 10527</span><span class="sxs-lookup"><span data-stu-id="bcb83-102">Single Sign-On: Event 10527</span></span>
## <a name="details"></a><span data-ttu-id="bcb83-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="bcb83-103">Details</span></span>  

|                 |                                                                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bcb83-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="bcb83-104">Product Name</span></span>   |                                                                                      <span data-ttu-id="bcb83-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="bcb83-105">Enterprise Single Sign-On</span></span>                                                                                      |
| <span data-ttu-id="bcb83-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="bcb83-106">Product Version</span></span> |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                      |
|    <span data-ttu-id="bcb83-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="bcb83-107">Event ID</span></span>     |                                                                                                <span data-ttu-id="bcb83-108">10527</span><span class="sxs-lookup"><span data-stu-id="bcb83-108">10527</span></span>                                                                                                |
|  <span data-ttu-id="bcb83-109">事件源</span><span class="sxs-lookup"><span data-stu-id="bcb83-109">Event Source</span></span>   |                                                                                               <span data-ttu-id="bcb83-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bcb83-110">ENTSSO</span></span>                                                                                                |
|    <span data-ttu-id="bcb83-111">组件</span><span class="sxs-lookup"><span data-stu-id="bcb83-111">Component</span></span>    |                                                                                                  <span data-ttu-id="bcb83-112">0</span><span class="sxs-lookup"><span data-stu-id="bcb83-112">0</span></span>                                                                                                  |
|  <span data-ttu-id="bcb83-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="bcb83-113">Symbolic Name</span></span>  |                                                                                     <span data-ttu-id="bcb83-114">SSO_ERROR_GET_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="bcb83-114">SSO_ERROR_GET_SECRET_FAILED</span></span>                                                                                     |
|  <span data-ttu-id="bcb83-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="bcb83-115">Message Text</span></span>   | <span data-ttu-id="bcb83-116">获取主机密 failed.%r 的请求</span><span class="sxs-lookup"><span data-stu-id="bcb83-116">A request to get a master secret failed.%r</span></span><br /><br /> <span data-ttu-id="bcb83-117">密钥编号: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bcb83-117">Secret Number: %1%r</span></span><br /><br /> <span data-ttu-id="bcb83-118">客户端用户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="bcb83-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="bcb83-119">客户端计算机: %3 %r</span><span class="sxs-lookup"><span data-stu-id="bcb83-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="bcb83-120">跟踪 ID: %4 %r</span><span class="sxs-lookup"><span data-stu-id="bcb83-120">Tracking ID: %4%r</span></span><br /><br /> <span data-ttu-id="bcb83-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="bcb83-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="bcb83-122">解释</span><span class="sxs-lookup"><span data-stu-id="bcb83-122">Explanation</span></span>  
 <span data-ttu-id="bcb83-123">此错误事件表示获取主密钥的请求已失败。</span><span class="sxs-lookup"><span data-stu-id="bcb83-123">This Error event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="bcb83-124">在这些情况下应该有相关的邮件应用程序事件日志中。</span><span class="sxs-lookup"><span data-stu-id="bcb83-124">In these cases there should be related messages in the Application event log.</span></span>  

## <a name="user-action"></a><span data-ttu-id="bcb83-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="bcb83-125">User Action</span></span>  
 <span data-ttu-id="bcb83-126">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bcb83-126">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="bcb83-127">检查应用程序事件日志关联的事件或错误。</span><span class="sxs-lookup"><span data-stu-id="bcb83-127">Check the Application event log for associated events or errors.</span></span>  

  <span data-ttu-id="bcb83-128">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="bcb83-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="bcb83-129">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="bcb83-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="bcb83-130">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="bcb83-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
