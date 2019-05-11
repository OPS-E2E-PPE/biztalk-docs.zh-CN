---
title: 单一登录：事件 10532 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae2112bc-b53c-4d99-9dc1-a2f55dda4665
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ea52d8e64f5a59a633a6e22eef7220f44b36f77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262344"
---
# <a name="single-sign-on-event-10532"></a><span data-ttu-id="b9df6-102">单一登录：事件 10532</span><span class="sxs-lookup"><span data-stu-id="b9df6-102">Single Sign-On: Event 10532</span></span>
## <a name="details"></a><span data-ttu-id="b9df6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b9df6-103">Details</span></span>  

|                 |                                                                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b9df6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b9df6-104">Product Name</span></span>   |                                                                              <span data-ttu-id="b9df6-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b9df6-105">Enterprise Single Sign-On</span></span>                                                                              |
| <span data-ttu-id="b9df6-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b9df6-106">Product Version</span></span> |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                              |
|    <span data-ttu-id="b9df6-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b9df6-107">Event ID</span></span>     |                                                                                        <span data-ttu-id="b9df6-108">10532</span><span class="sxs-lookup"><span data-stu-id="b9df6-108">10532</span></span>                                                                                        |
|  <span data-ttu-id="b9df6-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b9df6-109">Event Source</span></span>   |                                                                                       <span data-ttu-id="b9df6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b9df6-110">ENTSSO</span></span>                                                                                        |
|    <span data-ttu-id="b9df6-111">组件</span><span class="sxs-lookup"><span data-stu-id="b9df6-111">Component</span></span>    |                                                                                         <span data-ttu-id="b9df6-112">CO</span><span class="sxs-lookup"><span data-stu-id="b9df6-112">CO</span></span>                                                                                          |
|  <span data-ttu-id="b9df6-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b9df6-113">Symbolic Name</span></span>  |                                                                             <span data-ttu-id="b9df6-114">SSO_WARN_LOST_SECRET_SERVER</span><span class="sxs-lookup"><span data-stu-id="b9df6-114">SSO_WARN_LOST_SECRET_SERVER</span></span>                                                                             |
|  <span data-ttu-id="b9df6-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b9df6-115">Message Text</span></span>   | <span data-ttu-id="b9df6-116">检索主密钥失败。</span><span class="sxs-lookup"><span data-stu-id="b9df6-116">Failed to retrieve master secrets.</span></span> <span data-ttu-id="b9df6-117">验证主密钥服务器名称正确，以及它是 available.%r</span><span class="sxs-lookup"><span data-stu-id="b9df6-117">Verify that the master secret server name is correct and that it is available.%r</span></span><br /><br /> <span data-ttu-id="b9df6-118">密钥服务器名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="b9df6-118">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="b9df6-119">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="b9df6-119">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="b9df6-120">解释</span><span class="sxs-lookup"><span data-stu-id="b9df6-120">Explanation</span></span>  
 <span data-ttu-id="b9df6-121">此警告事件表示获取主密钥的请求已失败。</span><span class="sxs-lookup"><span data-stu-id="b9df6-121">This Warning event indicates that a request to get the master secret has failed.</span></span> <span data-ttu-id="b9df6-122">这可能是因为未在服务器上运行企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="b9df6-122">This might be because the Enterprise Single Sign-On service is not running on the server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="b9df6-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="b9df6-123">User Action</span></span>  
 <span data-ttu-id="b9df6-124">若要解决此警告，请执行一个或多个以下操作：</span><span class="sxs-lookup"><span data-stu-id="b9df6-124">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="b9df6-125">检查应用程序事件日志关联的事件或错误。</span><span class="sxs-lookup"><span data-stu-id="b9df6-125">Check the Application event log for associated events or errors.</span></span>  

- <span data-ttu-id="b9df6-126">验证主密钥服务器名称正确。</span><span class="sxs-lookup"><span data-stu-id="b9df6-126">Verify the master secret server name is correct.</span></span>  

- <span data-ttu-id="b9df6-127">验证主密钥服务器处于联机状态并且正在运行企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="b9df6-127">Verify the master secret server is online and that the Enterprise Single Sign-On service is running.</span></span>  

  <span data-ttu-id="b9df6-128">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="b9df6-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="b9df6-129">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="b9df6-129">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="b9df6-130">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="b9df6-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
