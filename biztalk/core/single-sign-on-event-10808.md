---
title: 单一登录： 事件 10808 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b4efc1d-f163-4440-a78e-53065c6af36c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b891a8cb076c332eca8918ece713385c1bbccc3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277085"
---
# <a name="single-sign-on-event-10808"></a><span data-ttu-id="ef0b3-102">单一登录： 事件 10808</span><span class="sxs-lookup"><span data-stu-id="ef0b3-102">Single Sign-On: Event 10808</span></span>
## <a name="details"></a><span data-ttu-id="ef0b3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ef0b3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef0b3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ef0b3-104">Product Name</span></span>|<span data-ttu-id="ef0b3-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ef0b3-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="ef0b3-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ef0b3-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="ef0b3-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ef0b3-107">Event ID</span></span>|<span data-ttu-id="ef0b3-108">10808</span><span class="sxs-lookup"><span data-stu-id="ef0b3-108">10808</span></span>|  
|<span data-ttu-id="ef0b3-109">事件源</span><span class="sxs-lookup"><span data-stu-id="ef0b3-109">Event Source</span></span>|<span data-ttu-id="ef0b3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ef0b3-110">ENTSSO</span></span>|  
|<span data-ttu-id="ef0b3-111">组件</span><span class="sxs-lookup"><span data-stu-id="ef0b3-111">Component</span></span>|<span data-ttu-id="ef0b3-112">N/A</span><span class="sxs-lookup"><span data-stu-id="ef0b3-112">N/A</span></span>|  
|<span data-ttu-id="ef0b3-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="ef0b3-113">Symbolic Name</span></span>|<span data-ttu-id="ef0b3-114">ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="ef0b3-114">ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED</span></span>|  
|<span data-ttu-id="ef0b3-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="ef0b3-115">Message Text</span></span>|<span data-ttu-id="ef0b3-116">没有为主机启动的单一登录启用 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="ef0b3-116">The SSO system is not enabled for Host Initiated Single Sign-On.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ef0b3-117">解释</span><span class="sxs-lookup"><span data-stu-id="ef0b3-117">Explanation</span></span>  
 <span data-ttu-id="ef0b3-118">没有为主机启动的单一登录启用 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="ef0b3-118">The SSO system is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ef0b3-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="ef0b3-119">User Action</span></span>  
 <span data-ttu-id="ef0b3-120">使用管理工具配置主机启动的单一登录。</span><span class="sxs-lookup"><span data-stu-id="ef0b3-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="ef0b3-121">这便会设置</span><span class="sxs-lookup"><span data-stu-id="ef0b3-121">This will set the</span></span>  
  
 <span data-ttu-id="ef0b3-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS 标记。</span><span class="sxs-lookup"><span data-stu-id="ef0b3-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the global information.</span></span>