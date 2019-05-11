---
title: 单一登录：Event 10604 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eea14ab1-5a89-4a62-b414-1bcb36ea339e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 577015af1c021bd17d0d286974e554f9ebf399bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397768"
---
# <a name="single-sign-on-event-10604"></a><span data-ttu-id="73045-102">单一登录：事件 10604</span><span class="sxs-lookup"><span data-stu-id="73045-102">Single Sign-On: Event 10604</span></span>
## <a name="details"></a><span data-ttu-id="73045-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="73045-103">Details</span></span>  
  
|                 |                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="73045-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="73045-104">Product Name</span></span>   |                                        <span data-ttu-id="73045-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="73045-105">Enterprise Single Sign-On</span></span>                                         |
| <span data-ttu-id="73045-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="73045-106">Product Version</span></span> |                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                        |
|    <span data-ttu-id="73045-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="73045-107">Event ID</span></span>     |                                                  <span data-ttu-id="73045-108">10604</span><span class="sxs-lookup"><span data-stu-id="73045-108">10604</span></span>                                                   |
|  <span data-ttu-id="73045-109">事件源</span><span class="sxs-lookup"><span data-stu-id="73045-109">Event Source</span></span>   |                                                  <span data-ttu-id="73045-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="73045-110">ENTSSO</span></span>                                                  |
|    <span data-ttu-id="73045-111">组件</span><span class="sxs-lookup"><span data-stu-id="73045-111">Component</span></span>    |                                                   <span data-ttu-id="73045-112">不可用</span><span class="sxs-lookup"><span data-stu-id="73045-112">N/A</span></span>                                                    |
|  <span data-ttu-id="73045-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="73045-113">Symbolic Name</span></span>  |                                      <span data-ttu-id="73045-114">SSO_ERROR_SSOCSTX_OUT_OF_PROC</span><span class="sxs-lookup"><span data-stu-id="73045-114">SSO_ERROR_SSOCSTX_OUT_OF_PROC</span></span>                                       |
|  <span data-ttu-id="73045-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="73045-115">Message Text</span></span>   | <span data-ttu-id="73045-116">ENTSSO Server COM + 应用程序配置不正确。</span><span class="sxs-lookup"><span data-stu-id="73045-116">The 'ENTSSO Server' COM+ application is not configured correctly.</span></span> <span data-ttu-id="73045-117">它必须是 COM + 库应用程序。</span><span class="sxs-lookup"><span data-stu-id="73045-117">It must be a COM+ library application.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="73045-118">解释</span><span class="sxs-lookup"><span data-stu-id="73045-118">Explanation</span></span>  
 <span data-ttu-id="73045-119">COM + 应用程序必须配置为 COM + 库应用程序。</span><span class="sxs-lookup"><span data-stu-id="73045-119">The COM+ application must be configured as a COM+ library application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="73045-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="73045-120">User Action</span></span>  
 <span data-ttu-id="73045-121">在 ENTSSO MMC 管理单元中，展开 COM + 文件夹并找到您的 ENTSSO Server。</span><span class="sxs-lookup"><span data-stu-id="73045-121">In the ENTSSO MMC Snap-In, expand the COM+ folder and locate your ENTSSO Server.</span></span> <span data-ttu-id="73045-122">右键单击服务器，然后单击属性。</span><span class="sxs-lookup"><span data-stu-id="73045-122">Right-click the server, and then click Properties.</span></span> <span data-ttu-id="73045-123">选择库应用程序而不是服务器应用程序，然后单击确定。</span><span class="sxs-lookup"><span data-stu-id="73045-123">Select Library Application instead of Server Application, and click OK.</span></span>