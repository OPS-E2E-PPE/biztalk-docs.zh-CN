---
title: 单一登录：事件 11047 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa4eb1ae-45a6-4e0c-9af6-6bf1ed63acfb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97d70d94ffad94b4a81d09c821469c4adbfbe775
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400959"
---
# <a name="single-sign-on-event-11047"></a><span data-ttu-id="e2357-102">单一登录：事件 11047</span><span class="sxs-lookup"><span data-stu-id="e2357-102">Single Sign-On: Event 11047</span></span>
## <a name="details"></a><span data-ttu-id="e2357-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e2357-103">Details</span></span>  
  
|                 |                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e2357-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e2357-104">Product Name</span></span>   |                                                                <span data-ttu-id="e2357-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="e2357-105">Enterprise Single Sign-On</span></span>                                                                |
| <span data-ttu-id="e2357-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="e2357-106">Product Version</span></span> |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    <span data-ttu-id="e2357-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e2357-107">Event ID</span></span>     |                                                                          <span data-ttu-id="e2357-108">11047</span><span class="sxs-lookup"><span data-stu-id="e2357-108">11047</span></span>                                                                          |
|  <span data-ttu-id="e2357-109">事件源</span><span class="sxs-lookup"><span data-stu-id="e2357-109">Event Source</span></span>   |                                                                         <span data-ttu-id="e2357-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e2357-110">ENTSSO</span></span>                                                                          |
|    <span data-ttu-id="e2357-111">组件</span><span class="sxs-lookup"><span data-stu-id="e2357-111">Component</span></span>    |                                                                           <span data-ttu-id="e2357-112">不可用</span><span class="sxs-lookup"><span data-stu-id="e2357-112">N/A</span></span>                                                                           |
|  <span data-ttu-id="e2357-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="e2357-113">Symbolic Name</span></span>  |                                                                 <span data-ttu-id="e2357-114">SSO_ERROR_SSOSQL_FAILED</span><span class="sxs-lookup"><span data-stu-id="e2357-114">SSO_ERROR_SSOSQL_FAILED</span></span>                                                                 |
|  <span data-ttu-id="e2357-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="e2357-115">Message Text</span></span>   | <span data-ttu-id="e2357-116">无法创建 SSOSQL。</span><span class="sxs-lookup"><span data-stu-id="e2357-116">Could not create SSOSQL.</span></span> <span data-ttu-id="e2357-117">若要解决此问题，请重新安装 SSO 或尝试 Visual Studio 命令 prompt.%r regasm SSOSQL.dll</span><span class="sxs-lookup"><span data-stu-id="e2357-117">To fix the problem, reinstall SSO or try ‘regasm SSOSQL.dll’ from a Visual Studio command prompt.%r</span></span><br /><br /> <span data-ttu-id="e2357-118">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="e2357-118">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e2357-119">解释</span><span class="sxs-lookup"><span data-stu-id="e2357-119">Explanation</span></span>  
 <span data-ttu-id="e2357-120">这可能是由于安装错误所致。</span><span class="sxs-lookup"><span data-stu-id="e2357-120">This is likely caused by an installation error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e2357-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="e2357-121">User Action</span></span>  
 <span data-ttu-id="e2357-122">若要解决此问题，请重新安装 SSO 或尝试从 Visual Studio 命令提示符下的 regasm SSOSQL.dll。</span><span class="sxs-lookup"><span data-stu-id="e2357-122">To fix the problem, reinstall SSO or try ‘regasm SSOSQL.dll’ from a Visual Studio command prompt.</span></span>