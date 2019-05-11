---
title: 单一登录：Event 10806 | Microsoft Docs
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
ms.openlocfilehash: 0c7aee239e10e96147ff19ee29aa83e7578d8a80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396128"
---
# <a name="single-sign-on-event-10806"></a><span data-ttu-id="05f0c-102">单一登录：事件 10806</span><span class="sxs-lookup"><span data-stu-id="05f0c-102">Single Sign-On: Event 10806</span></span>
## <a name="details"></a><span data-ttu-id="05f0c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="05f0c-103">Details</span></span>  
  
|                 |                                                                                   |
|-----------------|-----------------------------------------------------------------------------------|
|  <span data-ttu-id="05f0c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="05f0c-104">Product Name</span></span>   |                             <span data-ttu-id="05f0c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="05f0c-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="05f0c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="05f0c-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    <span data-ttu-id="05f0c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="05f0c-107">Event ID</span></span>     |                                       <span data-ttu-id="05f0c-108">10806</span><span class="sxs-lookup"><span data-stu-id="05f0c-108">10806</span></span>                                       |
|  <span data-ttu-id="05f0c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="05f0c-109">Event Source</span></span>   |                                      <span data-ttu-id="05f0c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="05f0c-110">ENTSSO</span></span>                                       |
|    <span data-ttu-id="05f0c-111">组件</span><span class="sxs-lookup"><span data-stu-id="05f0c-111">Component</span></span>    |                                        <span data-ttu-id="05f0c-112">不可用</span><span class="sxs-lookup"><span data-stu-id="05f0c-112">N/A</span></span>                                        |
|  <span data-ttu-id="05f0c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="05f0c-113">Symbolic Name</span></span>  |                         <span data-ttu-id="05f0c-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="05f0c-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span></span>                          |
|  <span data-ttu-id="05f0c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="05f0c-115">Message Text</span></span>   | <span data-ttu-id="05f0c-116">无法删除应用程序，因为当前已分配给某个适配器。</span><span class="sxs-lookup"><span data-stu-id="05f0c-116">The application cannot be deleted because it is currently assigned to an adapter.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="05f0c-117">解释</span><span class="sxs-lookup"><span data-stu-id="05f0c-117">Explanation</span></span>  
 <span data-ttu-id="05f0c-118">分配给一个适配器时，无法删除应用程序。</span><span class="sxs-lookup"><span data-stu-id="05f0c-118">An application cannot be deleted when it is assigned to an adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="05f0c-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="05f0c-119">User Action</span></span>  
 <span data-ttu-id="05f0c-120">取消分配应用程序通过该适配器，然后再删除它。</span><span class="sxs-lookup"><span data-stu-id="05f0c-120">Unassign the application from the adapter, and then delete it.</span></span>