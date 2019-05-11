---
title: 单一登录：Event 10563 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c944cc4-7fe0-41cc-9608-ee954e8222e0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b735a435a076b873b8462f3b794012f731956ad1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398810"
---
# <a name="single-sign-on-event-10563"></a><span data-ttu-id="21949-102">单一登录：事件 10563</span><span class="sxs-lookup"><span data-stu-id="21949-102">Single Sign-On: Event 10563</span></span>
## <a name="details"></a><span data-ttu-id="21949-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="21949-103">Details</span></span>  
  
|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  <span data-ttu-id="21949-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="21949-104">Product Name</span></span>   |                      <span data-ttu-id="21949-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="21949-105">Enterprise Single Sign-On</span></span>                       |
| <span data-ttu-id="21949-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="21949-106">Product Version</span></span> |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    <span data-ttu-id="21949-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="21949-107">Event ID</span></span>     |                                <span data-ttu-id="21949-108">10563</span><span class="sxs-lookup"><span data-stu-id="21949-108">10563</span></span>                                 |
|  <span data-ttu-id="21949-109">事件源</span><span class="sxs-lookup"><span data-stu-id="21949-109">Event Source</span></span>   |                                <span data-ttu-id="21949-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="21949-110">ENTSSO</span></span>                                |
|    <span data-ttu-id="21949-111">组件</span><span class="sxs-lookup"><span data-stu-id="21949-111">Component</span></span>    |                                 <span data-ttu-id="21949-112">不可用</span><span class="sxs-lookup"><span data-stu-id="21949-112">N/A</span></span>                                  |
|  <span data-ttu-id="21949-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="21949-113">Symbolic Name</span></span>  |                       <span data-ttu-id="21949-114">SSO_WARN_PERFMON_FAILED</span><span class="sxs-lookup"><span data-stu-id="21949-114">SSO_WARN_PERFMON_FAILED</span></span>                        |
|  <span data-ttu-id="21949-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="21949-115">Message Text</span></span>   | <span data-ttu-id="21949-116">性能监视无法 start.%r</span><span class="sxs-lookup"><span data-stu-id="21949-116">Performance monitoring failed to start.%r</span></span><br /><br /> <span data-ttu-id="21949-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="21949-117">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="21949-118">解释</span><span class="sxs-lookup"><span data-stu-id="21949-118">Explanation</span></span>  
 <span data-ttu-id="21949-119">性能监视启动失败。</span><span class="sxs-lookup"><span data-stu-id="21949-119">Performance monitoring failed to start.</span></span> <span data-ttu-id="21949-120">系统将继续正常运行，但性能监视将不可用。</span><span class="sxs-lookup"><span data-stu-id="21949-120">The system will continue to run normally but performance monitoring will not be available.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="21949-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="21949-121">User Action</span></span>  
 <span data-ttu-id="21949-122">它可能需要卸载并重新安装 perfmon 实用程序。</span><span class="sxs-lookup"><span data-stu-id="21949-122">It may be necessary to uninstall and reinstall the perfmon utility.</span></span>