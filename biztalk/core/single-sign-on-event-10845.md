---
title: 单一登录：Event 10845 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37b8b3c2-ae61-49a1-b171-ca51664f00dd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7590765806f9962fd3f3987a752d258a09bfe27a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307253"
---
# <a name="single-sign-on-event-10845"></a><span data-ttu-id="7eabf-102">单一登录：事件 10845</span><span class="sxs-lookup"><span data-stu-id="7eabf-102">Single Sign-On: Event 10845</span></span>
## <a name="details"></a><span data-ttu-id="7eabf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eabf-103">Details</span></span>  
  
|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7eabf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7eabf-104">Product Name</span></span>   |                                               <span data-ttu-id="7eabf-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7eabf-105">Enterprise Single Sign-On</span></span>                                               |
| <span data-ttu-id="7eabf-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="7eabf-106">Product Version</span></span> |                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    <span data-ttu-id="7eabf-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7eabf-107">Event ID</span></span>     |                                                         <span data-ttu-id="7eabf-108">10845</span><span class="sxs-lookup"><span data-stu-id="7eabf-108">10845</span></span>                                                         |
|  <span data-ttu-id="7eabf-109">事件源</span><span class="sxs-lookup"><span data-stu-id="7eabf-109">Event Source</span></span>   |                                                        <span data-ttu-id="7eabf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7eabf-110">ENTSSO</span></span>                                                         |
|    <span data-ttu-id="7eabf-111">组件</span><span class="sxs-lookup"><span data-stu-id="7eabf-111">Component</span></span>    |                                                          <span data-ttu-id="7eabf-112">不可用</span><span class="sxs-lookup"><span data-stu-id="7eabf-112">N/A</span></span>                                                          |
|  <span data-ttu-id="7eabf-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="7eabf-113">Symbolic Name</span></span>  |                                                  <span data-ttu-id="7eabf-114">ENTSSO_E_DB_ACCESS2</span><span class="sxs-lookup"><span data-stu-id="7eabf-114">ENTSSO_E_DB_ACCESS2</span></span>                                                  |
|  <span data-ttu-id="7eabf-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="7eabf-115">Message Text</span></span>   | <span data-ttu-id="7eabf-116">尝试访问 SSO 数据库时出错。</span><span class="sxs-lookup"><span data-stu-id="7eabf-116">An error occurred while attempting to access the SSO database.</span></span> <span data-ttu-id="7eabf-117">查看更多详细信息的日志 （在计算机"%1"）。</span><span class="sxs-lookup"><span data-stu-id="7eabf-117">See the event log (on computer ‘%1’) for more details.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7eabf-118">解释</span><span class="sxs-lookup"><span data-stu-id="7eabf-118">Explanation</span></span>  
 <span data-ttu-id="7eabf-119">尝试访问 SSO 数据库时出错。</span><span class="sxs-lookup"><span data-stu-id="7eabf-119">An error occurred while attempting to access the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7eabf-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="7eabf-120">User Action</span></span>  
 <span data-ttu-id="7eabf-121">指定从 SQL Server 的其他信息的计算机上，请参阅事件日志。</span><span class="sxs-lookup"><span data-stu-id="7eabf-121">See the event log on the specified computer for additional information from the SQL Server.</span></span>