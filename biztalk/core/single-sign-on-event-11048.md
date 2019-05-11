---
title: 单一登录：事件 11048 |Microsoft Docs
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
ms.openlocfilehash: 9b21787ab368df4ddf7bad7c9ca93d541cc796c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400946"
---
# <a name="single-sign-on-event-11048"></a><span data-ttu-id="3c708-102">单一登录：事件 11048</span><span class="sxs-lookup"><span data-stu-id="3c708-102">Single Sign-On: Event 11048</span></span>
## <a name="details"></a><span data-ttu-id="3c708-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3c708-103">Details</span></span>  
  
|                 |                                                                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3c708-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3c708-104">Product Name</span></span>   |                                                                             <span data-ttu-id="3c708-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3c708-105">Enterprise Single Sign-On</span></span>                                                                              |
| <span data-ttu-id="3c708-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="3c708-106">Product Version</span></span> |                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                             |
|    <span data-ttu-id="3c708-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3c708-107">Event ID</span></span>     |                                                                                       <span data-ttu-id="3c708-108">11048</span><span class="sxs-lookup"><span data-stu-id="3c708-108">11048</span></span>                                                                                        |
|  <span data-ttu-id="3c708-109">事件源</span><span class="sxs-lookup"><span data-stu-id="3c708-109">Event Source</span></span>   |                                                                                       <span data-ttu-id="3c708-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3c708-110">ENTSSO</span></span>                                                                                       |
|    <span data-ttu-id="3c708-111">组件</span><span class="sxs-lookup"><span data-stu-id="3c708-111">Component</span></span>    |                                                                                        <span data-ttu-id="3c708-112">不可用</span><span class="sxs-lookup"><span data-stu-id="3c708-112">N/A</span></span>                                                                                         |
|  <span data-ttu-id="3c708-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="3c708-113">Symbolic Name</span></span>  |                                                                              <span data-ttu-id="3c708-114">SSO_ERROR_SSOCSTX_FAILED</span><span class="sxs-lookup"><span data-stu-id="3c708-114">SSO_ERROR_SSOCSTX_FAILED</span></span>                                                                              |
|  <span data-ttu-id="3c708-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="3c708-115">Message Text</span></span>   | <span data-ttu-id="3c708-116">无法创建 SSOCSTX。</span><span class="sxs-lookup"><span data-stu-id="3c708-116">Could not create SSOCSTX.</span></span> <span data-ttu-id="3c708-117">若要解决此问题，请重新安装 SSO 或将 SSOCSTX.dll 安装到 COM + 库 application.%r</span><span class="sxs-lookup"><span data-stu-id="3c708-117">To fix the problem, reinstall SSO or install SSOCSTX.dll into a COM+ library application.%r</span></span><br /><br /> <span data-ttu-id="3c708-118">其他数据: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3c708-118">Additional Data: %1%r</span></span><br /><br /> <span data-ttu-id="3c708-119">错误代码： %2</span><span class="sxs-lookup"><span data-stu-id="3c708-119">Error Code: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3c708-120">解释</span><span class="sxs-lookup"><span data-stu-id="3c708-120">Explanation</span></span>  
 <span data-ttu-id="3c708-121">这可能是由于安装错误所致。</span><span class="sxs-lookup"><span data-stu-id="3c708-121">This is likely caused by an installation error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c708-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="3c708-122">User Action</span></span>  
 <span data-ttu-id="3c708-123">若要解决此问题，请重新安装 SSO 或将 SSOCSTX.dll 安装到 COM + 库应用程序。</span><span class="sxs-lookup"><span data-stu-id="3c708-123">To fix the problem, reinstall SSO or install SSOCSTX.dll into a COM+ library application.</span></span>