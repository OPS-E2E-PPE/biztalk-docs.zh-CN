---
title: 单一登录： 事件 10809 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d4bf5ba006af8c479abc621accdc28296c0eae3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016060"
---
# <a name="single-sign-on-event-10809"></a><span data-ttu-id="66176-102">单一登录： 事件 10809</span><span class="sxs-lookup"><span data-stu-id="66176-102">Single Sign-On: Event 10809</span></span>
## <a name="details"></a><span data-ttu-id="66176-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="66176-103">Details</span></span>  
  
|                 |                                                                   |
|-----------------|-------------------------------------------------------------------|
|  <span data-ttu-id="66176-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="66176-104">Product Name</span></span>   |                     <span data-ttu-id="66176-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="66176-105">Enterprise Single Sign-On</span></span>                     |
| <span data-ttu-id="66176-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="66176-106">Product Version</span></span> |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]     |
|    <span data-ttu-id="66176-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="66176-107">Event ID</span></span>     |                               <span data-ttu-id="66176-108">10809</span><span class="sxs-lookup"><span data-stu-id="66176-108">10809</span></span>                               |
|  <span data-ttu-id="66176-109">事件源</span><span class="sxs-lookup"><span data-stu-id="66176-109">Event Source</span></span>   |                              <span data-ttu-id="66176-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="66176-110">ENTSSO</span></span>                               |
|    <span data-ttu-id="66176-111">组件</span><span class="sxs-lookup"><span data-stu-id="66176-111">Component</span></span>    |                                <span data-ttu-id="66176-112">N/A</span><span class="sxs-lookup"><span data-stu-id="66176-112">N/A</span></span>                                |
|  <span data-ttu-id="66176-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="66176-113">Symbolic Name</span></span>  |                  <span data-ttu-id="66176-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="66176-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span></span>                   |
|  <span data-ttu-id="66176-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="66176-115">Message Text</span></span>   | <span data-ttu-id="66176-116">主机启动的单一登录未启用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="66176-116">The application is not enabled for Host Initiated Single Sign-On.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="66176-117">解释</span><span class="sxs-lookup"><span data-stu-id="66176-117">Explanation</span></span>  
 <span data-ttu-id="66176-118">主机启动的单一登录未启用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="66176-118">The application is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66176-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="66176-119">User Action</span></span>  
 <span data-ttu-id="66176-120">使用管理工具配置主机启动的单一登录。</span><span class="sxs-lookup"><span data-stu-id="66176-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="66176-121">这会设置</span><span class="sxs-lookup"><span data-stu-id="66176-121">This will set the</span></span>  
  
 <span data-ttu-id="66176-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS 标志。</span><span class="sxs-lookup"><span data-stu-id="66176-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the application.</span></span>