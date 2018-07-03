---
title: 单一登录： 事件 10538 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1211ac33-9149-4dd3-85a2-d46eb24d1060
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f4b7fba63d26fde664e14470eb95b41a1580ae7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975774"
---
# <a name="single-sign-on-event-10538"></a><span data-ttu-id="47c7a-102">单一登录： 事件 10538</span><span class="sxs-lookup"><span data-stu-id="47c7a-102">Single Sign-On: Event 10538</span></span>
## <a name="details"></a><span data-ttu-id="47c7a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="47c7a-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="47c7a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="47c7a-104">Product Name</span></span>   |                         <span data-ttu-id="47c7a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="47c7a-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="47c7a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="47c7a-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="47c7a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="47c7a-107">Event ID</span></span>     |                                   <span data-ttu-id="47c7a-108">10538</span><span class="sxs-lookup"><span data-stu-id="47c7a-108">10538</span></span>                                   |
|  <span data-ttu-id="47c7a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="47c7a-109">Event Source</span></span>   |                                  <span data-ttu-id="47c7a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="47c7a-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="47c7a-111">组件</span><span class="sxs-lookup"><span data-stu-id="47c7a-111">Component</span></span>    |                                    <span data-ttu-id="47c7a-112">CO</span><span class="sxs-lookup"><span data-stu-id="47c7a-112">CO</span></span>                                     |
|  <span data-ttu-id="47c7a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="47c7a-113">Symbolic Name</span></span>  |                           <span data-ttu-id="47c7a-114">SSO_WARN_APP_DISABLED</span><span class="sxs-lookup"><span data-stu-id="47c7a-114">SSO_WARN_APP_DISABLED</span></span>                           |
|  <span data-ttu-id="47c7a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="47c7a-115">Message Text</span></span>   | <span data-ttu-id="47c7a-116">目前禁用了此应用程序。%r</span><span class="sxs-lookup"><span data-stu-id="47c7a-116">The application is currently disabled.%r</span></span><br /><br /> <span data-ttu-id="47c7a-117">应用程序名称： %1</span><span class="sxs-lookup"><span data-stu-id="47c7a-117">Application Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="47c7a-118">解释</span><span class="sxs-lookup"><span data-stu-id="47c7a-118">Explanation</span></span>  
 <span data-ttu-id="47c7a-119">此警告事件表示应用程序管理员已禁用了 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="47c7a-119">This Warning event indicates that the SSO affiliate application has been disabled by an Application Administrator.</span></span>  

## <a name="user-action"></a><span data-ttu-id="47c7a-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="47c7a-120">User Action</span></span>  
 <span data-ttu-id="47c7a-121">若要解决此警告问题，请执行以下一项或多项操作：</span><span class="sxs-lookup"><span data-stu-id="47c7a-121">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="47c7a-122">联系应用程序管理员以启用 SSO 关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="47c7a-122">Contact your Application Administrator to enable the SSO affiliate application.</span></span> <span data-ttu-id="47c7a-123">可使用 SSO 管理工具（GUI 或命令行）完成此操作。</span><span class="sxs-lookup"><span data-stu-id="47c7a-123">This can be done using the SSO administration tools (GUI or command line).</span></span>  

  <span data-ttu-id="47c7a-124">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="47c7a-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="47c7a-125">如何启用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="47c7a-125">How to Enable an Affiliate Application</span></span>](../core/how-to-enable-an-affiliate-application.md)  

- [<span data-ttu-id="47c7a-126">如何禁用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="47c7a-126">How to Disable an Affiliate Application</span></span>](../core/how-to-disable-an-affiliate-application.md)
