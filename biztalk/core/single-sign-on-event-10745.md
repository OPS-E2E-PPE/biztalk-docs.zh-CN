---
title: 单一登录：Event 10745 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed630e40-d876-4e90-937e-4d2d54fe9f1a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d75304b54a9ebd2484b36273a165cf8fa1cc998
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395503"
---
# <a name="single-sign-on-event-10745"></a><span data-ttu-id="f8ff7-102">单一登录：事件 10745</span><span class="sxs-lookup"><span data-stu-id="f8ff7-102">Single Sign-On: Event 10745</span></span>
## <a name="details"></a><span data-ttu-id="f8ff7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f8ff7-103">Details</span></span>  

|                 |                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f8ff7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f8ff7-104">Product Name</span></span>   |                                                          <span data-ttu-id="f8ff7-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f8ff7-105">Enterprise Single Sign-On</span></span>                                                           |
| <span data-ttu-id="f8ff7-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f8ff7-106">Product Version</span></span> |                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                          |
|    <span data-ttu-id="f8ff7-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f8ff7-107">Event ID</span></span>     |                                                                    <span data-ttu-id="f8ff7-108">10745</span><span class="sxs-lookup"><span data-stu-id="f8ff7-108">10745</span></span>                                                                     |
|  <span data-ttu-id="f8ff7-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f8ff7-109">Event Source</span></span>   |                                                                    <span data-ttu-id="f8ff7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f8ff7-110">ENTSSO</span></span>                                                                    |
|    <span data-ttu-id="f8ff7-111">组件</span><span class="sxs-lookup"><span data-stu-id="f8ff7-111">Component</span></span>    |                                                                     <span data-ttu-id="f8ff7-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f8ff7-112">N\A</span></span>                                                                      |
|  <span data-ttu-id="f8ff7-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f8ff7-113">Symbolic Name</span></span>  |                                                          <span data-ttu-id="f8ff7-114">SSO_ERROR_ADAPTER_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="f8ff7-114">SSO_ERROR_ADAPTER_OFFLINE</span></span>                                                           |
|  <span data-ttu-id="f8ff7-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f8ff7-115">Message Text</span></span>   | <span data-ttu-id="f8ff7-116">该适配器是 offline.%r</span><span class="sxs-lookup"><span data-stu-id="f8ff7-116">The adapter is offline.%r</span></span><br /><br /> <span data-ttu-id="f8ff7-117">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f8ff7-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="f8ff7-118">适配器: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f8ff7-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="f8ff7-119">出现错误消息: %3 %r</span><span class="sxs-lookup"><span data-stu-id="f8ff7-119">Error Message: %3%r</span></span><br /><br /> <span data-ttu-id="f8ff7-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="f8ff7-120">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="f8ff7-121">解释</span><span class="sxs-lookup"><span data-stu-id="f8ff7-121">Explanation</span></span>  
 <span data-ttu-id="f8ff7-122">此错误事件表示指定的适配器处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="f8ff7-122">This Error event indicates that the specified adapter is offline.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f8ff7-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="f8ff7-123">User Action</span></span>  
 <span data-ttu-id="f8ff7-124">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="f8ff7-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="f8ff7-125">检查系统和应用程序事件日志中的关联错误。</span><span class="sxs-lookup"><span data-stu-id="f8ff7-125">Check the system and application event logs for associated errors.</span></span>  

- <span data-ttu-id="f8ff7-126">检查外部适配器存在错误。</span><span class="sxs-lookup"><span data-stu-id="f8ff7-126">Check the external adapter for errors.</span></span>  

  <span data-ttu-id="f8ff7-127">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="f8ff7-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="f8ff7-128">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="f8ff7-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
