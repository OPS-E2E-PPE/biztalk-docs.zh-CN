---
title: 单一登录： 事件 10560 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8677a807-2973-4753-8816-c93c45697d92
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82f9245b4eda9b6bf567aae1de2071d3e77aae04
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967750"
---
# <a name="single-sign-on-event-10560"></a><span data-ttu-id="78a92-102">单一登录： 事件 10560</span><span class="sxs-lookup"><span data-stu-id="78a92-102">Single Sign-On: Event 10560</span></span>
## <a name="details"></a><span data-ttu-id="78a92-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="78a92-103">Details</span></span>  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="78a92-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="78a92-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="78a92-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="78a92-105">Enterprise Single Sign-On</span></span>                                                                                  |
| <span data-ttu-id="78a92-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="78a92-106">Product Version</span></span> |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="78a92-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="78a92-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="78a92-108">10560</span><span class="sxs-lookup"><span data-stu-id="78a92-108">10560</span></span>                                                                                            |
|  <span data-ttu-id="78a92-109">事件源</span><span class="sxs-lookup"><span data-stu-id="78a92-109">Event Source</span></span>   |                                                                                           <span data-ttu-id="78a92-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="78a92-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="78a92-111">组件</span><span class="sxs-lookup"><span data-stu-id="78a92-111">Component</span></span>    |                                                                                             <span data-ttu-id="78a92-112">N/A</span><span class="sxs-lookup"><span data-stu-id="78a92-112">N/A</span></span>                                                                                             |
|  <span data-ttu-id="78a92-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="78a92-113">Symbolic Name</span></span>  |                                                                               <span data-ttu-id="78a92-114">SSO_ERROR_BACKUP_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="78a92-114">SSO_ERROR_BACKUP_SECRET_FAILED</span></span>                                                                                |
|  <span data-ttu-id="78a92-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="78a92-115">Message Text</span></span>   | <span data-ttu-id="78a92-116">备份主密钥失败。%r</span><span class="sxs-lookup"><span data-stu-id="78a92-116">Failed to back up the master secrets.%r</span></span><br /><br /> <span data-ttu-id="78a92-117">文件名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="78a92-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="78a92-118">当前 MSID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="78a92-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="78a92-119">上一个 MSID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="78a92-119">Previous MSID: %3%r</span></span><br /><br /> <span data-ttu-id="78a92-120">客户端用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="78a92-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="78a92-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="78a92-121">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="78a92-122">解释</span><span class="sxs-lookup"><span data-stu-id="78a92-122">Explanation</span></span>  
 <span data-ttu-id="78a92-123">尝试备份主密钥失败。</span><span class="sxs-lookup"><span data-stu-id="78a92-123">An attempt to back up the master secret has failed.</span></span> <span data-ttu-id="78a92-124">尝试进行备份的用户的权限不正确，或使用的路径或目录不正确。</span><span class="sxs-lookup"><span data-stu-id="78a92-124">The user attempting this backup may have had the wrong permissions, path, or directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="78a92-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="78a92-125">User Action</span></span>  
 <span data-ttu-id="78a92-126">有关备份主密钥的信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="78a92-126">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>