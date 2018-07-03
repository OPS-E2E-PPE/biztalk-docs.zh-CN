---
title: 单一登录： 事件 10788 |Microsoft Docs
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
ms.openlocfilehash: b1bf8d17abd7fd5652821b998cae34915e7777f2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019657"
---
# <a name="single-sign-on-event-10788"></a><span data-ttu-id="3eb86-102">单一登录： 事件 10788</span><span class="sxs-lookup"><span data-stu-id="3eb86-102">Single Sign-On: Event 10788</span></span>
## <a name="details"></a><span data-ttu-id="3eb86-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3eb86-103">Details</span></span>  
  
|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3eb86-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3eb86-104">Product Name</span></span>   |                                                        <span data-ttu-id="3eb86-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="3eb86-105">Enterprise Single Sign-On</span></span>                                                         |
| <span data-ttu-id="3eb86-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="3eb86-106">Product Version</span></span> |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    <span data-ttu-id="3eb86-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3eb86-107">Event ID</span></span>     |                                                                  <span data-ttu-id="3eb86-108">10788</span><span class="sxs-lookup"><span data-stu-id="3eb86-108">10788</span></span>                                                                   |
|  <span data-ttu-id="3eb86-109">事件源</span><span class="sxs-lookup"><span data-stu-id="3eb86-109">Event Source</span></span>   |                                                                  <span data-ttu-id="3eb86-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3eb86-110">ENTSSO</span></span>                                                                  |
|    <span data-ttu-id="3eb86-111">组件</span><span class="sxs-lookup"><span data-stu-id="3eb86-111">Component</span></span>    |                                                                   <span data-ttu-id="3eb86-112">N/A</span><span class="sxs-lookup"><span data-stu-id="3eb86-112">N/A</span></span>                                                                    |
|  <span data-ttu-id="3eb86-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="3eb86-113">Symbolic Name</span></span>  |                                                       <span data-ttu-id="3eb86-114">ENTSSO_E_DTC_IMPORT_FAILED1</span><span class="sxs-lookup"><span data-stu-id="3eb86-114">ENTSSO_E_DTC_IMPORT_FAILED1</span></span>                                                        |
|  <span data-ttu-id="3eb86-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="3eb86-115">Message Text</span></span>   | <span data-ttu-id="3eb86-116">无法导入 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="3eb86-116">Could not import a DTC transaction.</span></span> <span data-ttu-id="3eb86-117">请检查是否正确配置 MSDTC 以用于远程操作。</span><span class="sxs-lookup"><span data-stu-id="3eb86-117">Please check that MSDTC is configured correctly for remote operation.</span></span> <span data-ttu-id="3eb86-118">有关详细信息，请参阅文档。</span><span class="sxs-lookup"><span data-stu-id="3eb86-118">See documentation for details.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3eb86-119">解释</span><span class="sxs-lookup"><span data-stu-id="3eb86-119">Explanation</span></span>  
 <span data-ttu-id="3eb86-120">无法导入 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="3eb86-120">Could not import a DTC transaction.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3eb86-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="3eb86-121">User Action</span></span>  
 <span data-ttu-id="3eb86-122">请检查是否正确配置 MSDTC 以用于远程操作；有关详细信息，请参阅指定计算机上的事件日志。</span><span class="sxs-lookup"><span data-stu-id="3eb86-122">Check that MSDTC is configured correctly for remote operation, and see the event log on the specified computer for more details.</span></span>  
  
 <span data-ttu-id="3eb86-123">有关 MSDTC 问题的帮助，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。</span><span class="sxs-lookup"><span data-stu-id="3eb86-123">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>