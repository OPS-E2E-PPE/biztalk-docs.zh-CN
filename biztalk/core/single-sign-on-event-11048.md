---
title: 单一登录： 事件 11048 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: abceb5ca-f772-4cc8-8e20-2cda8765575e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da3843cf1cde3394df048230e642c98770d0da3e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989214"
---
# <a name="single-sign-on-event-11048"></a><span data-ttu-id="2b21f-102">单一登录： 事件 11048</span><span class="sxs-lookup"><span data-stu-id="2b21f-102">Single Sign-On: Event 11048</span></span>
## <a name="details"></a><span data-ttu-id="2b21f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2b21f-103">Details</span></span>  
  
|                 |                                                                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2b21f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2b21f-104">Product Name</span></span>   |                                                                             <span data-ttu-id="2b21f-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="2b21f-105">Enterprise Single Sign-On</span></span>                                                                              |
| <span data-ttu-id="2b21f-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="2b21f-106">Product Version</span></span> |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    <span data-ttu-id="2b21f-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2b21f-107">Event ID</span></span>     |                                                                                       <span data-ttu-id="2b21f-108">11048</span><span class="sxs-lookup"><span data-stu-id="2b21f-108">11048</span></span>                                                                                        |
|  <span data-ttu-id="2b21f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="2b21f-109">Event Source</span></span>   |                                                                                       <span data-ttu-id="2b21f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2b21f-110">ENTSSO</span></span>                                                                                       |
|    <span data-ttu-id="2b21f-111">组件</span><span class="sxs-lookup"><span data-stu-id="2b21f-111">Component</span></span>    |                                                                                        <span data-ttu-id="2b21f-112">N/A</span><span class="sxs-lookup"><span data-stu-id="2b21f-112">N/A</span></span>                                                                                         |
|  <span data-ttu-id="2b21f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="2b21f-113">Symbolic Name</span></span>  |                                                                              <span data-ttu-id="2b21f-114">SSO_ERROR_SSOCSTX_FAILED</span><span class="sxs-lookup"><span data-stu-id="2b21f-114">SSO_ERROR_SSOCSTX_FAILED</span></span>                                                                              |
|  <span data-ttu-id="2b21f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="2b21f-115">Message Text</span></span>   | <span data-ttu-id="2b21f-116">无法创建 SSOCSTX。</span><span class="sxs-lookup"><span data-stu-id="2b21f-116">Could not create SSOCSTX.</span></span> <span data-ttu-id="2b21f-117">若要解决此问题，请重新安装 SSO 或将 SSOCSTX.dll 安装到 COM+ 库应用程序中。%r</span><span class="sxs-lookup"><span data-stu-id="2b21f-117">To fix the problem, reinstall SSO or install SSOCSTX.dll into a COM+ library application.%r</span></span><br /><br /> <span data-ttu-id="2b21f-118">其他数据: %1 %r</span><span class="sxs-lookup"><span data-stu-id="2b21f-118">Additional Data: %1%r</span></span><br /><br /> <span data-ttu-id="2b21f-119">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="2b21f-119">Error Code: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2b21f-120">解释</span><span class="sxs-lookup"><span data-stu-id="2b21f-120">Explanation</span></span>  
 <span data-ttu-id="2b21f-121">这可能是由于安装错误所致。</span><span class="sxs-lookup"><span data-stu-id="2b21f-121">This is likely caused by an installation error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2b21f-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="2b21f-122">User Action</span></span>  
 <span data-ttu-id="2b21f-123">若要解决此问题，请重新安装 SSO 或将 SSOCSTX.dll 安装到 COM+ 库应用程序中。</span><span class="sxs-lookup"><span data-stu-id="2b21f-123">To fix the problem, reinstall SSO or install SSOCSTX.dll into a COM+ library application.</span></span>