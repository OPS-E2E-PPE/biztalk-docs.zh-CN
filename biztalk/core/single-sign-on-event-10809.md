---
title: "单一登录： 事件 10809 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e010c6ee391e72ec270ddbdc767bed861836cb8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10809"></a><span data-ttu-id="8779c-102">单一登录： 事件 10809</span><span class="sxs-lookup"><span data-stu-id="8779c-102">Single Sign-On: Event 10809</span></span>
## <a name="details"></a><span data-ttu-id="8779c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8779c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8779c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8779c-104">Product Name</span></span>|<span data-ttu-id="8779c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8779c-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="8779c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8779c-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="8779c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8779c-107">Event ID</span></span>|<span data-ttu-id="8779c-108">10809</span><span class="sxs-lookup"><span data-stu-id="8779c-108">10809</span></span>|  
|<span data-ttu-id="8779c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="8779c-109">Event Source</span></span>|<span data-ttu-id="8779c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8779c-110">ENTSSO</span></span>|  
|<span data-ttu-id="8779c-111">组件</span><span class="sxs-lookup"><span data-stu-id="8779c-111">Component</span></span>|<span data-ttu-id="8779c-112">N/A</span><span class="sxs-lookup"><span data-stu-id="8779c-112">N/A</span></span>|  
|<span data-ttu-id="8779c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="8779c-113">Symbolic Name</span></span>|<span data-ttu-id="8779c-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="8779c-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span></span>|  
|<span data-ttu-id="8779c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="8779c-115">Message Text</span></span>|<span data-ttu-id="8779c-116">主机启动的单一登录未启用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="8779c-116">The application is not enabled for Host Initiated Single Sign-On.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8779c-117">解释</span><span class="sxs-lookup"><span data-stu-id="8779c-117">Explanation</span></span>  
 <span data-ttu-id="8779c-118">主机启动的单一登录未启用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="8779c-118">The application is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8779c-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="8779c-119">User Action</span></span>  
 <span data-ttu-id="8779c-120">使用管理工具配置主机启动的单一登录。</span><span class="sxs-lookup"><span data-stu-id="8779c-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="8779c-121">这便会设置</span><span class="sxs-lookup"><span data-stu-id="8779c-121">This will set the</span></span>  
  
 <span data-ttu-id="8779c-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS 标志。</span><span class="sxs-lookup"><span data-stu-id="8779c-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the application.</span></span>