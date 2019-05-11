---
title: 单一登录：Event 10789 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2821694e-e787-4942-8da5-4492e543b4da
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb18f1f6be9c4eae6d14e8ca662b1678be297169
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400554"
---
# <a name="single-sign-on-event-10789"></a><span data-ttu-id="45fdb-102">单一登录：事件 10789</span><span class="sxs-lookup"><span data-stu-id="45fdb-102">Single Sign-On: Event 10789</span></span>
## <a name="details"></a><span data-ttu-id="45fdb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="45fdb-103">Details</span></span>  
  
|                 |                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="45fdb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="45fdb-104">Product Name</span></span>   |                                                                    <span data-ttu-id="45fdb-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="45fdb-105">Enterprise Single Sign-On</span></span>                                                                     |
| <span data-ttu-id="45fdb-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="45fdb-106">Product Version</span></span> |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                    |
|    <span data-ttu-id="45fdb-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="45fdb-107">Event ID</span></span>     |                                                                              <span data-ttu-id="45fdb-108">10789</span><span class="sxs-lookup"><span data-stu-id="45fdb-108">10789</span></span>                                                                               |
|  <span data-ttu-id="45fdb-109">事件源</span><span class="sxs-lookup"><span data-stu-id="45fdb-109">Event Source</span></span>   |                                                                              <span data-ttu-id="45fdb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="45fdb-110">ENTSSO</span></span>                                                                              |
|    <span data-ttu-id="45fdb-111">组件</span><span class="sxs-lookup"><span data-stu-id="45fdb-111">Component</span></span>    |                                                                               <span data-ttu-id="45fdb-112">不可用</span><span class="sxs-lookup"><span data-stu-id="45fdb-112">N/A</span></span>                                                                                |
|  <span data-ttu-id="45fdb-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="45fdb-113">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="45fdb-114">ENTSSO_E_DTC_IMPORT_FAILED2</span><span class="sxs-lookup"><span data-stu-id="45fdb-114">ENTSSO_E_DTC_IMPORT_FAILED2</span></span>                                                                    |
|  <span data-ttu-id="45fdb-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="45fdb-115">Message Text</span></span>   | <span data-ttu-id="45fdb-116">无法导入 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="45fdb-116">Could not import a DTC transaction.</span></span> <span data-ttu-id="45fdb-117">请检查 MSDTC 正确配置用于远程操作。</span><span class="sxs-lookup"><span data-stu-id="45fdb-117">Please check that MSDTC is configured correctly for remote operation.</span></span> <span data-ttu-id="45fdb-118">查看更多详细信息的日志 （在计算机"%1"）。</span><span class="sxs-lookup"><span data-stu-id="45fdb-118">See the event log (on computer ‘%1’) for more details.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="45fdb-119">解释</span><span class="sxs-lookup"><span data-stu-id="45fdb-119">Explanation</span></span>  
 <span data-ttu-id="45fdb-120">无法导入 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="45fdb-120">Could not import a DTC transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="45fdb-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="45fdb-121">User Action</span></span>  
 <span data-ttu-id="45fdb-122">检查 MSDTC 正确配置用于远程操作，并在指定计算机的更多详细信息，请参阅事件日志。</span><span class="sxs-lookup"><span data-stu-id="45fdb-122">Check that MSDTC is configured correctly for remote operation, and see the event log on the specified computer for more details.</span></span>  
  
 <span data-ttu-id="45fdb-123">有关 MSDTC 问题的帮助，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。</span><span class="sxs-lookup"><span data-stu-id="45fdb-123">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>