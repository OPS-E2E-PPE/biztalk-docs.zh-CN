---
title: 单一登录： 事件 10806 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23650d6b-b6a4-4c41-96cd-476e5b0f7f63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be61b0a48dde7b1c8de9ec716f4f9426c39fa0cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002694"
---
# <a name="single-sign-on-event-10806"></a><span data-ttu-id="8a4d2-102">单一登录： 事件 10806</span><span class="sxs-lookup"><span data-stu-id="8a4d2-102">Single Sign-On: Event 10806</span></span>
## <a name="details"></a><span data-ttu-id="8a4d2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8a4d2-103">Details</span></span>  
  
|                 |                                                                                   |
|-----------------|-----------------------------------------------------------------------------------|
|  <span data-ttu-id="8a4d2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8a4d2-104">Product Name</span></span>   |                             <span data-ttu-id="8a4d2-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8a4d2-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="8a4d2-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8a4d2-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    <span data-ttu-id="8a4d2-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8a4d2-107">Event ID</span></span>     |                                       <span data-ttu-id="8a4d2-108">10806</span><span class="sxs-lookup"><span data-stu-id="8a4d2-108">10806</span></span>                                       |
|  <span data-ttu-id="8a4d2-109">事件源</span><span class="sxs-lookup"><span data-stu-id="8a4d2-109">Event Source</span></span>   |                                      <span data-ttu-id="8a4d2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8a4d2-110">ENTSSO</span></span>                                       |
|    <span data-ttu-id="8a4d2-111">组件</span><span class="sxs-lookup"><span data-stu-id="8a4d2-111">Component</span></span>    |                                        <span data-ttu-id="8a4d2-112">N/A</span><span class="sxs-lookup"><span data-stu-id="8a4d2-112">N/A</span></span>                                        |
|  <span data-ttu-id="8a4d2-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="8a4d2-113">Symbolic Name</span></span>  |                         <span data-ttu-id="8a4d2-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="8a4d2-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span></span>                          |
|  <span data-ttu-id="8a4d2-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="8a4d2-115">Message Text</span></span>   | <span data-ttu-id="8a4d2-116">无法删除该应用程序，因为它当前已分配给某个适配器。</span><span class="sxs-lookup"><span data-stu-id="8a4d2-116">The application cannot be deleted because it is currently assigned to an adapter.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8a4d2-117">解释</span><span class="sxs-lookup"><span data-stu-id="8a4d2-117">Explanation</span></span>  
 <span data-ttu-id="8a4d2-118">应用程序被分配到适配器后无法删除。</span><span class="sxs-lookup"><span data-stu-id="8a4d2-118">An application cannot be deleted when it is assigned to an adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8a4d2-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="8a4d2-119">User Action</span></span>  
 <span data-ttu-id="8a4d2-120">取消将应用程序分配到适合器，然后再将其删除。</span><span class="sxs-lookup"><span data-stu-id="8a4d2-120">Unassign the application from the adapter, and then delete it.</span></span>