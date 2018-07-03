---
title: 单一登录： 事件 10785 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4f4a2ad-a378-4806-ba16-d2872c4773f1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96194f9ab4a057301e9c0a20d4c222f730e70bfb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991510"
---
# <a name="single-sign-on-event-10785"></a><span data-ttu-id="d9d13-102">单一登录： 事件 10785</span><span class="sxs-lookup"><span data-stu-id="d9d13-102">Single Sign-On: Event 10785</span></span>
## <a name="details"></a><span data-ttu-id="d9d13-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d9d13-103">Details</span></span>  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="d9d13-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d9d13-104">Product Name</span></span>   |                   <span data-ttu-id="d9d13-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d9d13-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="d9d13-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d9d13-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="d9d13-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d9d13-107">Event ID</span></span>     |                             <span data-ttu-id="d9d13-108">10785</span><span class="sxs-lookup"><span data-stu-id="d9d13-108">10785</span></span>                              |
|  <span data-ttu-id="d9d13-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d9d13-109">Event Source</span></span>   |                             <span data-ttu-id="d9d13-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d9d13-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="d9d13-111">组件</span><span class="sxs-lookup"><span data-stu-id="d9d13-111">Component</span></span>    |                              <span data-ttu-id="d9d13-112">N/A</span><span class="sxs-lookup"><span data-stu-id="d9d13-112">N/A</span></span>                               |
|  <span data-ttu-id="d9d13-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d9d13-113">Symbolic Name</span></span>  |                       <span data-ttu-id="d9d13-114">ENTSSO_E_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="d9d13-114">ENTSSO_E_DB_ACCESS</span></span>                       |
|  <span data-ttu-id="d9d13-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d9d13-115">Message Text</span></span>   | <span data-ttu-id="d9d13-116">尝试访问 SSO 数据库时出错。</span><span class="sxs-lookup"><span data-stu-id="d9d13-116">An error occurred while attempting to access the SSO database.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d9d13-117">解释</span><span class="sxs-lookup"><span data-stu-id="d9d13-117">Explanation</span></span>  
 <span data-ttu-id="d9d13-118">ENTSSO 数据库可能处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="d9d13-118">The ENTSSO database may be offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d9d13-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="d9d13-119">User Action</span></span>  
 <span data-ttu-id="d9d13-120">请系统管理员检查 ENTSSO 服务器上的事件日志。</span><span class="sxs-lookup"><span data-stu-id="d9d13-120">Have your system administrator check the Event Log on the ENTSSO server.</span></span>