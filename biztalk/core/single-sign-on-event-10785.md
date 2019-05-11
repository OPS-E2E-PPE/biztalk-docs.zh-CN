---
title: 单一登录：Event 10785 | Microsoft Docs
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
ms.openlocfilehash: fed42624f0efc2c4ae2d13c35d48ca47a87e35cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65278017"
---
# <a name="single-sign-on-event-10785"></a><span data-ttu-id="0534b-102">单一登录：事件 10785</span><span class="sxs-lookup"><span data-stu-id="0534b-102">Single Sign-On: Event 10785</span></span>
## <a name="details"></a><span data-ttu-id="0534b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0534b-103">Details</span></span>  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="0534b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0534b-104">Product Name</span></span>   |                   <span data-ttu-id="0534b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0534b-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="0534b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0534b-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="0534b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0534b-107">Event ID</span></span>     |                             <span data-ttu-id="0534b-108">10785</span><span class="sxs-lookup"><span data-stu-id="0534b-108">10785</span></span>                              |
|  <span data-ttu-id="0534b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0534b-109">Event Source</span></span>   |                             <span data-ttu-id="0534b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0534b-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="0534b-111">组件</span><span class="sxs-lookup"><span data-stu-id="0534b-111">Component</span></span>    |                              <span data-ttu-id="0534b-112">不可用</span><span class="sxs-lookup"><span data-stu-id="0534b-112">N/A</span></span>                               |
|  <span data-ttu-id="0534b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0534b-113">Symbolic Name</span></span>  |                       <span data-ttu-id="0534b-114">ENTSSO_E_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="0534b-114">ENTSSO_E_DB_ACCESS</span></span>                       |
|  <span data-ttu-id="0534b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0534b-115">Message Text</span></span>   | <span data-ttu-id="0534b-116">尝试访问 SSO 数据库时出错。</span><span class="sxs-lookup"><span data-stu-id="0534b-116">An error occurred while attempting to access the SSO database.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0534b-117">解释</span><span class="sxs-lookup"><span data-stu-id="0534b-117">Explanation</span></span>  
 <span data-ttu-id="0534b-118">ENTSSO 数据库可能处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="0534b-118">The ENTSSO database may be offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0534b-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="0534b-119">User Action</span></span>  
 <span data-ttu-id="0534b-120">具有系统管理员检查 ENTSSO 服务器上的事件日志。</span><span class="sxs-lookup"><span data-stu-id="0534b-120">Have your system administrator check the Event Log on the ENTSSO server.</span></span>