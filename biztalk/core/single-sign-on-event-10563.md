---
title: "单一登录： 事件 10563 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c944cc4-7fe0-41cc-9608-ee954e8222e0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2ff30e245350004d798b0c6c2950b5bab345e77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10563"></a><span data-ttu-id="808eb-102">单一登录： 事件 10563</span><span class="sxs-lookup"><span data-stu-id="808eb-102">Single Sign-On: Event 10563</span></span>
## <a name="details"></a><span data-ttu-id="808eb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="808eb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="808eb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="808eb-104">Product Name</span></span>|<span data-ttu-id="808eb-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="808eb-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="808eb-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="808eb-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="808eb-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="808eb-107">Event ID</span></span>|<span data-ttu-id="808eb-108">10563</span><span class="sxs-lookup"><span data-stu-id="808eb-108">10563</span></span>|  
|<span data-ttu-id="808eb-109">事件源</span><span class="sxs-lookup"><span data-stu-id="808eb-109">Event Source</span></span>|<span data-ttu-id="808eb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="808eb-110">ENTSSO</span></span>|  
|<span data-ttu-id="808eb-111">组件</span><span class="sxs-lookup"><span data-stu-id="808eb-111">Component</span></span>|<span data-ttu-id="808eb-112">N/A</span><span class="sxs-lookup"><span data-stu-id="808eb-112">N/A</span></span>|  
|<span data-ttu-id="808eb-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="808eb-113">Symbolic Name</span></span>|<span data-ttu-id="808eb-114">SSO_WARN_PERFMON_FAILED</span><span class="sxs-lookup"><span data-stu-id="808eb-114">SSO_WARN_PERFMON_FAILED</span></span>|  
|<span data-ttu-id="808eb-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="808eb-115">Message Text</span></span>|<span data-ttu-id="808eb-116">性能监视启动失败。%r</span><span class="sxs-lookup"><span data-stu-id="808eb-116">Performance monitoring failed to start.%r</span></span><br /><br /> <span data-ttu-id="808eb-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="808eb-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="808eb-118">解释</span><span class="sxs-lookup"><span data-stu-id="808eb-118">Explanation</span></span>  
 <span data-ttu-id="808eb-119">性能监视启动失败。</span><span class="sxs-lookup"><span data-stu-id="808eb-119">Performance monitoring failed to start.</span></span> <span data-ttu-id="808eb-120">系统将继续正常运行，但性能监视将不可用。</span><span class="sxs-lookup"><span data-stu-id="808eb-120">The system will continue to run normally but performance monitoring will not be available.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="808eb-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="808eb-121">User Action</span></span>  
 <span data-ttu-id="808eb-122">必须卸载并重新安装 perfmon 实用程序。</span><span class="sxs-lookup"><span data-stu-id="808eb-122">It may be necessary to uninstall and reinstall the perfmon utility.</span></span>