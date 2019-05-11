---
title: 单一登录：Event 10605 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c9812b4-43bc-43c4-be8f-6f57c432bda6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181191572cd433ebcd6ab2356a1cb0455c6a4c09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397777"
---
# <a name="single-sign-on-event-10605"></a><span data-ttu-id="1e053-102">单一登录：事件 10605</span><span class="sxs-lookup"><span data-stu-id="1e053-102">Single Sign-On: Event 10605</span></span>
## <a name="details"></a><span data-ttu-id="1e053-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1e053-103">Details</span></span>  
  
|                 |                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1e053-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1e053-104">Product Name</span></span>   |                                                                       <span data-ttu-id="1e053-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1e053-105">Enterprise Single Sign-On</span></span>                                                                       |
| <span data-ttu-id="1e053-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="1e053-106">Product Version</span></span> |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    <span data-ttu-id="1e053-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1e053-107">Event ID</span></span>     |                                                                                 <span data-ttu-id="1e053-108">10605</span><span class="sxs-lookup"><span data-stu-id="1e053-108">10605</span></span>                                                                                 |
|  <span data-ttu-id="1e053-109">事件源</span><span class="sxs-lookup"><span data-stu-id="1e053-109">Event Source</span></span>   |                                                                                <span data-ttu-id="1e053-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1e053-110">ENTSSO</span></span>                                                                                 |
|    <span data-ttu-id="1e053-111">组件</span><span class="sxs-lookup"><span data-stu-id="1e053-111">Component</span></span>    |                                                                                  <span data-ttu-id="1e053-112">不可用</span><span class="sxs-lookup"><span data-stu-id="1e053-112">N/A</span></span>                                                                                  |
|  <span data-ttu-id="1e053-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="1e053-113">Symbolic Name</span></span>  |                                                                         <span data-ttu-id="1e053-114">SSO_ERROR_DTC_IMPORT</span><span class="sxs-lookup"><span data-stu-id="1e053-114">SSO_ERROR_DTC_IMPORT</span></span>                                                                          |
|  <span data-ttu-id="1e053-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="1e053-115">Message Text</span></span>   | <span data-ttu-id="1e053-116">无法导入 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="1e053-116">Could not import a DTC transaction.</span></span> <span data-ttu-id="1e053-117">请检查 MSDTC 正确配置用于远程操作。</span><span class="sxs-lookup"><span data-stu-id="1e053-117">Please check that MSDTC is configured correctly for remote operation.</span></span> <span data-ttu-id="1e053-118">请参阅 details.%r 文档</span><span class="sxs-lookup"><span data-stu-id="1e053-118">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="1e053-119">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="1e053-119">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1e053-120">解释</span><span class="sxs-lookup"><span data-stu-id="1e053-120">Explanation</span></span>  
 <span data-ttu-id="1e053-121">没有与 Microsoft 分布式事务处理协调器 (MSDTC) 的问题。</span><span class="sxs-lookup"><span data-stu-id="1e053-121">There is a problem with the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1e053-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="1e053-122">User Action</span></span>  
 <span data-ttu-id="1e053-123">有关 MSDTC 问题的帮助，请参阅[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。</span><span class="sxs-lookup"><span data-stu-id="1e053-123">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>