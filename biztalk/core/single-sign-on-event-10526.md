---
title: 单一登录：Event 10526 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f72d466-8b63-453c-b608-f9d64f635f65
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 924f6dee79b51740c62b302a0e57371fdd060470
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394326"
---
# <a name="single-sign-on-event-10526"></a><span data-ttu-id="7e3b6-102">单一登录：事件 10526</span><span class="sxs-lookup"><span data-stu-id="7e3b6-102">Single Sign-On: Event 10526</span></span>
## <a name="details"></a><span data-ttu-id="7e3b6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7e3b6-103">Details</span></span>  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7e3b6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7e3b6-104">Product Name</span></span>   |                                                                     <span data-ttu-id="7e3b6-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7e3b6-105">Enterprise Single Sign-On</span></span>                                                                     |
| <span data-ttu-id="7e3b6-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="7e3b6-106">Product Version</span></span> |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="7e3b6-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7e3b6-107">Event ID</span></span>     |                                                                               <span data-ttu-id="7e3b6-108">10526</span><span class="sxs-lookup"><span data-stu-id="7e3b6-108">10526</span></span>                                                                               |
|  <span data-ttu-id="7e3b6-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7e3b6-109">Event Source</span></span>   |                                                                              <span data-ttu-id="7e3b6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7e3b6-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="7e3b6-111">组件</span><span class="sxs-lookup"><span data-stu-id="7e3b6-111">Component</span></span>    |                                                                                <span data-ttu-id="7e3b6-112">N\A</span><span class="sxs-lookup"><span data-stu-id="7e3b6-112">N\A</span></span>                                                                                |
|  <span data-ttu-id="7e3b6-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7e3b6-113">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="7e3b6-114">SSO_ERROR_GENERATE_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="7e3b6-114">SSO_ERROR_GENERATE_SECRET_FAILED</span></span>                                                                  |
|  <span data-ttu-id="7e3b6-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7e3b6-115">Message Text</span></span>   | <span data-ttu-id="7e3b6-116">无法生成新的主密钥 secret.%r</span><span class="sxs-lookup"><span data-stu-id="7e3b6-116">Failed to generate a new master secret.%r</span></span><br /><br /> <span data-ttu-id="7e3b6-117">客户端用户: %1 %r</span><span class="sxs-lookup"><span data-stu-id="7e3b6-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="7e3b6-118">客户端计算机: %2 %r</span><span class="sxs-lookup"><span data-stu-id="7e3b6-118">Client Computer:%2%r</span></span><br /><br /> <span data-ttu-id="7e3b6-119">跟踪 ID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="7e3b6-119">Tracking ID: %3%r</span></span><br /><br /> <span data-ttu-id="7e3b6-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="7e3b6-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="7e3b6-121">解释</span><span class="sxs-lookup"><span data-stu-id="7e3b6-121">Explanation</span></span>  
 <span data-ttu-id="7e3b6-122">此错误事件表示用户尝试生成新的主密钥已失败。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-122">This Error event indicates that a user attempt to generate a new master secret has failed.</span></span> <span data-ttu-id="7e3b6-123">这可能是由于权限问题 （您必须是 SSO 管理员才能生成主密钥） 或可能没有主密钥写入备份文件的问题。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-123">This might be due to permissions issues (you must be an SSO Administrator to generate the master secret) or possibly there were problems writing the master secret to the backup file.</span></span> <span data-ttu-id="7e3b6-124">在这些情况下应该有相关的邮件应用程序事件日志中。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-124">In these cases there should be related messages in the Application event log.</span></span>  

## <a name="user-action"></a><span data-ttu-id="7e3b6-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="7e3b6-125">User Action</span></span>  
 <span data-ttu-id="7e3b6-126">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="7e3b6-126">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="7e3b6-127">检查应用程序事件日志关联的事件或错误。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-127">Check the Application event log for associated events or errors.</span></span>  

- <span data-ttu-id="7e3b6-128">检查你具有相应的 SSO 管理员权限。</span><span class="sxs-lookup"><span data-stu-id="7e3b6-128">Check that you have the appropriate SSO Administrator permissions.</span></span>  

  <span data-ttu-id="7e3b6-129">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="7e3b6-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="7e3b6-130">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="7e3b6-130">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="7e3b6-131">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="7e3b6-131">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
