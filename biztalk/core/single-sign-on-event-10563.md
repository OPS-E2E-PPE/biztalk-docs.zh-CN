---
title: 单一登录： 事件 10563 |Microsoft Docs
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
ms.openlocfilehash: 49fc95cf7c257febd6ab631dcc016598dd2e4e24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976501"
---
# <a name="single-sign-on-event-10563"></a><span data-ttu-id="e3748-102">单一登录： 事件 10563</span><span class="sxs-lookup"><span data-stu-id="e3748-102">Single Sign-On: Event 10563</span></span>
## <a name="details"></a><span data-ttu-id="e3748-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e3748-103">Details</span></span>  
  
|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  <span data-ttu-id="e3748-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e3748-104">Product Name</span></span>   |                      <span data-ttu-id="e3748-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e3748-105">Enterprise Single Sign-On</span></span>                       |
| <span data-ttu-id="e3748-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e3748-106">Product Version</span></span> |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    <span data-ttu-id="e3748-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e3748-107">Event ID</span></span>     |                                <span data-ttu-id="e3748-108">10563</span><span class="sxs-lookup"><span data-stu-id="e3748-108">10563</span></span>                                 |
|  <span data-ttu-id="e3748-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e3748-109">Event Source</span></span>   |                                <span data-ttu-id="e3748-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e3748-110">ENTSSO</span></span>                                |
|    <span data-ttu-id="e3748-111">组件</span><span class="sxs-lookup"><span data-stu-id="e3748-111">Component</span></span>    |                                 <span data-ttu-id="e3748-112">N/A</span><span class="sxs-lookup"><span data-stu-id="e3748-112">N/A</span></span>                                  |
|  <span data-ttu-id="e3748-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e3748-113">Symbolic Name</span></span>  |                       <span data-ttu-id="e3748-114">SSO_WARN_PERFMON_FAILED</span><span class="sxs-lookup"><span data-stu-id="e3748-114">SSO_WARN_PERFMON_FAILED</span></span>                        |
|  <span data-ttu-id="e3748-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e3748-115">Message Text</span></span>   | <span data-ttu-id="e3748-116">性能监视启动失败。%r</span><span class="sxs-lookup"><span data-stu-id="e3748-116">Performance monitoring failed to start.%r</span></span><br /><br /> <span data-ttu-id="e3748-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="e3748-117">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e3748-118">解释</span><span class="sxs-lookup"><span data-stu-id="e3748-118">Explanation</span></span>  
 <span data-ttu-id="e3748-119">性能监视启动失败。</span><span class="sxs-lookup"><span data-stu-id="e3748-119">Performance monitoring failed to start.</span></span> <span data-ttu-id="e3748-120">系统将继续正常运行，但性能监视将不可用。</span><span class="sxs-lookup"><span data-stu-id="e3748-120">The system will continue to run normally but performance monitoring will not be available.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e3748-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="e3748-121">User Action</span></span>  
 <span data-ttu-id="e3748-122">必须卸载并重新安装 perfmon 实用程序。</span><span class="sxs-lookup"><span data-stu-id="e3748-122">It may be necessary to uninstall and reinstall the perfmon utility.</span></span>