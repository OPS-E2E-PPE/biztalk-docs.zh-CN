---
title: 单一登录： 事件 10808 |Microsoft Docs
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
ms.openlocfilehash: 49d4e6ab0f6a9ea10ef28440f5b8399778fbc93b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971398"
---
# <a name="single-sign-on-event-10808"></a><span data-ttu-id="f7ae2-102">单一登录： 事件 10808</span><span class="sxs-lookup"><span data-stu-id="f7ae2-102">Single Sign-On: Event 10808</span></span>
## <a name="details"></a><span data-ttu-id="f7ae2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f7ae2-103">Details</span></span>  
  
|                 |                                                                  |
|-----------------|------------------------------------------------------------------|
|  <span data-ttu-id="f7ae2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f7ae2-104">Product Name</span></span>   |                    <span data-ttu-id="f7ae2-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f7ae2-105">Enterprise Single Sign-On</span></span>                     |
| <span data-ttu-id="f7ae2-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f7ae2-106">Product Version</span></span> |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]    |
|    <span data-ttu-id="f7ae2-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f7ae2-107">Event ID</span></span>     |                              <span data-ttu-id="f7ae2-108">10808</span><span class="sxs-lookup"><span data-stu-id="f7ae2-108">10808</span></span>                               |
|  <span data-ttu-id="f7ae2-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f7ae2-109">Event Source</span></span>   |                              <span data-ttu-id="f7ae2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f7ae2-110">ENTSSO</span></span>                              |
|    <span data-ttu-id="f7ae2-111">组件</span><span class="sxs-lookup"><span data-stu-id="f7ae2-111">Component</span></span>    |                               <span data-ttu-id="f7ae2-112">N/A</span><span class="sxs-lookup"><span data-stu-id="f7ae2-112">N/A</span></span>                                |
|  <span data-ttu-id="f7ae2-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f7ae2-113">Symbolic Name</span></span>  |                <span data-ttu-id="f7ae2-114">ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="f7ae2-114">ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED</span></span>                 |
|  <span data-ttu-id="f7ae2-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f7ae2-115">Message Text</span></span>   | <span data-ttu-id="f7ae2-116">没有为主机启动的单一登录启用 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="f7ae2-116">The SSO system is not enabled for Host Initiated Single Sign-On.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f7ae2-117">解释</span><span class="sxs-lookup"><span data-stu-id="f7ae2-117">Explanation</span></span>  
 <span data-ttu-id="f7ae2-118">没有为主机启动的单一登录启用 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="f7ae2-118">The SSO system is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f7ae2-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="f7ae2-119">User Action</span></span>  
 <span data-ttu-id="f7ae2-120">使用管理工具配置主机启动的单一登录。</span><span class="sxs-lookup"><span data-stu-id="f7ae2-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="f7ae2-121">这会设置</span><span class="sxs-lookup"><span data-stu-id="f7ae2-121">This will set the</span></span>  
  
 <span data-ttu-id="f7ae2-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS 标记。</span><span class="sxs-lookup"><span data-stu-id="f7ae2-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the global information.</span></span>