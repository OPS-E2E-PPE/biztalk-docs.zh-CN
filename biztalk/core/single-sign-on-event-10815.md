---
title: 单一登录：Event 10815 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf4ebb92-f0fa-499c-9bda-0cde726ec98e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22da14967d42a0a20bba7a79392e87f3a0052c35
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396121"
---
# <a name="single-sign-on-event-10815"></a><span data-ttu-id="9c514-102">单一登录：事件 10815</span><span class="sxs-lookup"><span data-stu-id="9c514-102">Single Sign-On: Event 10815</span></span>
## <a name="details"></a><span data-ttu-id="9c514-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9c514-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="9c514-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9c514-104">Product Name</span></span>   |                 <span data-ttu-id="9c514-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="9c514-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="9c514-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="9c514-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="9c514-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9c514-107">Event ID</span></span>     |                           <span data-ttu-id="9c514-108">10815</span><span class="sxs-lookup"><span data-stu-id="9c514-108">10815</span></span>                            |
|  <span data-ttu-id="9c514-109">事件源</span><span class="sxs-lookup"><span data-stu-id="9c514-109">Event Source</span></span>   |                           <span data-ttu-id="9c514-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9c514-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="9c514-111">组件</span><span class="sxs-lookup"><span data-stu-id="9c514-111">Component</span></span>    |                            <span data-ttu-id="9c514-112">不可用</span><span class="sxs-lookup"><span data-stu-id="9c514-112">N/A</span></span>                             |
|  <span data-ttu-id="9c514-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="9c514-113">Symbolic Name</span></span>  |                   <span data-ttu-id="9c514-114">ENTSSO_E_WRONG_SECRET</span><span class="sxs-lookup"><span data-stu-id="9c514-114">ENTSSO_E_WRONG_SECRET</span></span>                    |
|  <span data-ttu-id="9c514-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="9c514-115">Message Text</span></span>   |                  <span data-ttu-id="9c514-116">主密钥不正确。</span><span class="sxs-lookup"><span data-stu-id="9c514-116">Incorrect master secret.</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="9c514-117">解释</span><span class="sxs-lookup"><span data-stu-id="9c514-117">Explanation</span></span>  
 <span data-ttu-id="9c514-118">在尝试还原主密钥，你可能已指定错误的文件。</span><span class="sxs-lookup"><span data-stu-id="9c514-118">In attempting to restore the master secret, you may have specified the wrong file.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9c514-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="9c514-119">User Action</span></span>  
 <span data-ttu-id="9c514-120">再次检查该文件，并确保它是正确的。</span><span class="sxs-lookup"><span data-stu-id="9c514-120">Check the file again and make sure it is the right one.</span></span>