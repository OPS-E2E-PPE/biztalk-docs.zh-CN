---
title: 单一登录： 事件 10765 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e28fe42e-aa2b-4be4-b757-bc9c5c37526b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd49ead3fc30d3b98ea804a98a5882696ea749d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975102"
---
# <a name="single-sign-on-event-10765"></a><span data-ttu-id="0b810-102">单一登录： 事件 10765</span><span class="sxs-lookup"><span data-stu-id="0b810-102">Single Sign-On: Event 10765</span></span>
## <a name="details"></a><span data-ttu-id="0b810-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0b810-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="0b810-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0b810-104">Product Name</span></span>   |                 <span data-ttu-id="0b810-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0b810-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="0b810-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0b810-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="0b810-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0b810-107">Event ID</span></span>     |                           <span data-ttu-id="0b810-108">10765</span><span class="sxs-lookup"><span data-stu-id="0b810-108">10765</span></span>                            |
|  <span data-ttu-id="0b810-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0b810-109">Event Source</span></span>   |                           <span data-ttu-id="0b810-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0b810-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="0b810-111">组件</span><span class="sxs-lookup"><span data-stu-id="0b810-111">Component</span></span>    |                            <span data-ttu-id="0b810-112">N/A</span><span class="sxs-lookup"><span data-stu-id="0b810-112">N/A</span></span>                             |
|  <span data-ttu-id="0b810-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0b810-113">Symbolic Name</span></span>  |                  <span data-ttu-id="0b810-114">ENTSSO_E_NO_CREDENTIALS</span><span class="sxs-lookup"><span data-stu-id="0b810-114">ENTSSO_E_NO_CREDENTIALS</span></span>                   |
|  <span data-ttu-id="0b810-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0b810-115">Message Text</span></span>   |       <span data-ttu-id="0b810-116">尚未为此映射设置凭据。</span><span class="sxs-lookup"><span data-stu-id="0b810-116">No credentials have been set for the mapping.</span></span>        |
  
## <a name="explanation"></a><span data-ttu-id="0b810-117">解释</span><span class="sxs-lookup"><span data-stu-id="0b810-117">Explanation</span></span>  
 <span data-ttu-id="0b810-118">您请求了一个映射的 GetCredentials，但指定的映射没有凭据。</span><span class="sxs-lookup"><span data-stu-id="0b810-118">You have requested a GetCredentials on a mapping, and the mapping specified has no credentials.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b810-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="0b810-119">User Action</span></span>  
 <span data-ttu-id="0b810-120">使用命令行或 MMC 管理单元为映射设置凭据。</span><span class="sxs-lookup"><span data-stu-id="0b810-120">Use the command line or the MMC Snap-in to set credentials for the mapping.</span></span>