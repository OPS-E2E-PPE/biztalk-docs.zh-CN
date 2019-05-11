---
title: 单一登录：Event 10560 | Microsoft Docs
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
ms.openlocfilehash: b43a9558cff9325cb7a5355213001d67a0218d43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65296053"
---
# <a name="single-sign-on-event-10560"></a><span data-ttu-id="1aa7e-102">单一登录：事件 10560</span><span class="sxs-lookup"><span data-stu-id="1aa7e-102">Single Sign-On: Event 10560</span></span>
## <a name="details"></a><span data-ttu-id="1aa7e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1aa7e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1aa7e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1aa7e-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="1aa7e-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1aa7e-105">Enterprise Single Sign-On</span></span>                                                                                  |
| <span data-ttu-id="1aa7e-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="1aa7e-106">Product Version</span></span> |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="1aa7e-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1aa7e-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="1aa7e-108">10560</span><span class="sxs-lookup"><span data-stu-id="1aa7e-108">10560</span></span>                                                                                            |
|  <span data-ttu-id="1aa7e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1aa7e-109">Event Source</span></span>   |                                                                                           <span data-ttu-id="1aa7e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1aa7e-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="1aa7e-111">组件</span><span class="sxs-lookup"><span data-stu-id="1aa7e-111">Component</span></span>    |                                                                                             <span data-ttu-id="1aa7e-112">不可用</span><span class="sxs-lookup"><span data-stu-id="1aa7e-112">N/A</span></span>                                                                                             |
|  <span data-ttu-id="1aa7e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1aa7e-113">Symbolic Name</span></span>  |                                                                               <span data-ttu-id="1aa7e-114">SSO_ERROR_BACKUP_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="1aa7e-114">SSO_ERROR_BACKUP_SECRET_FAILED</span></span>                                                                                |
|  <span data-ttu-id="1aa7e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1aa7e-115">Message Text</span></span>   | <span data-ttu-id="1aa7e-116">备份主密钥 secrets.%r 失败</span><span class="sxs-lookup"><span data-stu-id="1aa7e-116">Failed to back up the master secrets.%r</span></span><br /><br /> <span data-ttu-id="1aa7e-117">文件名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="1aa7e-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="1aa7e-118">当前 MSID: %2 %r</span><span class="sxs-lookup"><span data-stu-id="1aa7e-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="1aa7e-119">上一个 MSID: %3 %r</span><span class="sxs-lookup"><span data-stu-id="1aa7e-119">Previous MSID: %3%r</span></span><br /><br /> <span data-ttu-id="1aa7e-120">客户端用户: %4 %r</span><span class="sxs-lookup"><span data-stu-id="1aa7e-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="1aa7e-121">错误代码： %5</span><span class="sxs-lookup"><span data-stu-id="1aa7e-121">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1aa7e-122">解释</span><span class="sxs-lookup"><span data-stu-id="1aa7e-122">Explanation</span></span>  
 <span data-ttu-id="1aa7e-123">尝试备份主密钥失败。</span><span class="sxs-lookup"><span data-stu-id="1aa7e-123">An attempt to back up the master secret has failed.</span></span> <span data-ttu-id="1aa7e-124">用户尝试进行备份可能存在错误的权限、 路径或目录。</span><span class="sxs-lookup"><span data-stu-id="1aa7e-124">The user attempting this backup may have had the wrong permissions, path, or directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1aa7e-125">用户操作</span><span class="sxs-lookup"><span data-stu-id="1aa7e-125">User Action</span></span>  
 <span data-ttu-id="1aa7e-126">有关备份主密钥的信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="1aa7e-126">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>