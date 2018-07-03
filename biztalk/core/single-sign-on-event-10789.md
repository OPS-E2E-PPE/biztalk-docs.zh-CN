---
title: 单一登录： 事件 10789 |Microsoft Docs
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
ms.openlocfilehash: 85ad6c7975e78f30872a60462e74ba16b18db0a1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997470"
---
# <a name="single-sign-on-event-10789"></a><span data-ttu-id="019d4-102">单一登录： 事件 10789</span><span class="sxs-lookup"><span data-stu-id="019d4-102">Single Sign-On: Event 10789</span></span>
## <a name="details"></a><span data-ttu-id="019d4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="019d4-103">Details</span></span>  
  
|                 |                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="019d4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="019d4-104">Product Name</span></span>   |                                                                    <span data-ttu-id="019d4-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="019d4-105">Enterprise Single Sign-On</span></span>                                                                     |
| <span data-ttu-id="019d4-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="019d4-106">Product Version</span></span> |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                    |
|    <span data-ttu-id="019d4-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="019d4-107">Event ID</span></span>     |                                                                              <span data-ttu-id="019d4-108">10789</span><span class="sxs-lookup"><span data-stu-id="019d4-108">10789</span></span>                                                                               |
|  <span data-ttu-id="019d4-109">事件源</span><span class="sxs-lookup"><span data-stu-id="019d4-109">Event Source</span></span>   |                                                                              <span data-ttu-id="019d4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="019d4-110">ENTSSO</span></span>                                                                              |
|    <span data-ttu-id="019d4-111">组件</span><span class="sxs-lookup"><span data-stu-id="019d4-111">Component</span></span>    |                                                                               <span data-ttu-id="019d4-112">N/A</span><span class="sxs-lookup"><span data-stu-id="019d4-112">N/A</span></span>                                                                                |
|  <span data-ttu-id="019d4-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="019d4-113">Symbolic Name</span></span>  |                                                                   <span data-ttu-id="019d4-114">ENTSSO_E_DTC_IMPORT_FAILED2</span><span class="sxs-lookup"><span data-stu-id="019d4-114">ENTSSO_E_DTC_IMPORT_FAILED2</span></span>                                                                    |
|  <span data-ttu-id="019d4-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="019d4-115">Message Text</span></span>   | <span data-ttu-id="019d4-116">无法导入 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="019d4-116">Could not import a DTC transaction.</span></span> <span data-ttu-id="019d4-117">请检查是否正确配置 MSDTC 以用于远程操作。</span><span class="sxs-lookup"><span data-stu-id="019d4-117">Please check that MSDTC is configured correctly for remote operation.</span></span> <span data-ttu-id="019d4-118">有关详细信息，请查看计算机“%1”上的事件日志。</span><span class="sxs-lookup"><span data-stu-id="019d4-118">See the event log (on computer ‘%1’) for more details.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="019d4-119">解释</span><span class="sxs-lookup"><span data-stu-id="019d4-119">Explanation</span></span>  
 <span data-ttu-id="019d4-120">无法导入 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="019d4-120">Could not import a DTC transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="019d4-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="019d4-121">User Action</span></span>  
 <span data-ttu-id="019d4-122">请检查是否正确配置 MSDTC 以用于远程操作；有关详细信息，请参阅指定计算机上的事件日志。</span><span class="sxs-lookup"><span data-stu-id="019d4-122">Check that MSDTC is configured correctly for remote operation, and see the event log on the specified computer for more details.</span></span>  
  
 <span data-ttu-id="019d4-123">有关 MSDTC 问题的帮助，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。</span><span class="sxs-lookup"><span data-stu-id="019d4-123">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>