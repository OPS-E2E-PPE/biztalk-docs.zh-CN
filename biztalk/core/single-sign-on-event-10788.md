---
title: 单一登录：Event 10788 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: deeb8859-6b2e-452d-a7e5-0cb10de68bd2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c2594fdaf20acb55131d928f22506c164a5c1dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394137"
---
# <a name="single-sign-on-event-10788"></a><span data-ttu-id="1cb76-102">单一登录：事件 10788</span><span class="sxs-lookup"><span data-stu-id="1cb76-102">Single Sign-On: Event 10788</span></span>
## <a name="details"></a><span data-ttu-id="1cb76-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1cb76-103">Details</span></span>  
  
|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1cb76-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1cb76-104">Product Name</span></span>   |                                                        <span data-ttu-id="1cb76-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1cb76-105">Enterprise Single Sign-On</span></span>                                                         |
| <span data-ttu-id="1cb76-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="1cb76-106">Product Version</span></span> |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    <span data-ttu-id="1cb76-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1cb76-107">Event ID</span></span>     |                                                                  <span data-ttu-id="1cb76-108">10788</span><span class="sxs-lookup"><span data-stu-id="1cb76-108">10788</span></span>                                                                   |
|  <span data-ttu-id="1cb76-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1cb76-109">Event Source</span></span>   |                                                                  <span data-ttu-id="1cb76-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1cb76-110">ENTSSO</span></span>                                                                  |
|    <span data-ttu-id="1cb76-111">组件</span><span class="sxs-lookup"><span data-stu-id="1cb76-111">Component</span></span>    |                                                                   <span data-ttu-id="1cb76-112">不可用</span><span class="sxs-lookup"><span data-stu-id="1cb76-112">N/A</span></span>                                                                    |
|  <span data-ttu-id="1cb76-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1cb76-113">Symbolic Name</span></span>  |                                                       <span data-ttu-id="1cb76-114">ENTSSO_E_DTC_IMPORT_FAILED1</span><span class="sxs-lookup"><span data-stu-id="1cb76-114">ENTSSO_E_DTC_IMPORT_FAILED1</span></span>                                                        |
|  <span data-ttu-id="1cb76-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1cb76-115">Message Text</span></span>   | <span data-ttu-id="1cb76-116">无法导入 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="1cb76-116">Could not import a DTC transaction.</span></span> <span data-ttu-id="1cb76-117">请检查 MSDTC 正确配置用于远程操作。</span><span class="sxs-lookup"><span data-stu-id="1cb76-117">Please check that MSDTC is configured correctly for remote operation.</span></span> <span data-ttu-id="1cb76-118">请参阅文档了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="1cb76-118">See documentation for details.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1cb76-119">解释</span><span class="sxs-lookup"><span data-stu-id="1cb76-119">Explanation</span></span>  
 <span data-ttu-id="1cb76-120">无法导入 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="1cb76-120">Could not import a DTC transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1cb76-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="1cb76-121">User Action</span></span>  
 <span data-ttu-id="1cb76-122">检查 MSDTC 正确配置用于远程操作，并在指定计算机的更多详细信息，请参阅事件日志。</span><span class="sxs-lookup"><span data-stu-id="1cb76-122">Check that MSDTC is configured correctly for remote operation, and see the event log on the specified computer for more details.</span></span>  
  
 <span data-ttu-id="1cb76-123">有关 MSDTC 问题的帮助，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。</span><span class="sxs-lookup"><span data-stu-id="1cb76-123">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>