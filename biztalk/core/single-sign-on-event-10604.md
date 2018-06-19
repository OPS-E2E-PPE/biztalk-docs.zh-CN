---
title: 单一登录： 事件 10604 |Microsoft 文档
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
ms.openlocfilehash: 0d9d6858fb13542ca642c9c48a8a187b66ba6526
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270541"
---
# <a name="single-sign-on-event-10604"></a><span data-ttu-id="4bd6c-102">单一登录： 事件 10604</span><span class="sxs-lookup"><span data-stu-id="4bd6c-102">Single Sign-On: Event 10604</span></span>
## <a name="details"></a><span data-ttu-id="4bd6c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4bd6c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4bd6c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4bd6c-104">Product Name</span></span>|<span data-ttu-id="4bd6c-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="4bd6c-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="4bd6c-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="4bd6c-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="4bd6c-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4bd6c-107">Event ID</span></span>|<span data-ttu-id="4bd6c-108">10604</span><span class="sxs-lookup"><span data-stu-id="4bd6c-108">10604</span></span>|  
|<span data-ttu-id="4bd6c-109">事件源</span><span class="sxs-lookup"><span data-stu-id="4bd6c-109">Event Source</span></span>|<span data-ttu-id="4bd6c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4bd6c-110">ENTSSO</span></span>|  
|<span data-ttu-id="4bd6c-111">组件</span><span class="sxs-lookup"><span data-stu-id="4bd6c-111">Component</span></span>|<span data-ttu-id="4bd6c-112">N/A</span><span class="sxs-lookup"><span data-stu-id="4bd6c-112">N/A</span></span>|  
|<span data-ttu-id="4bd6c-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="4bd6c-113">Symbolic Name</span></span>|<span data-ttu-id="4bd6c-114">SSO_ERROR_SSOCSTX_OUT_OF_PROC</span><span class="sxs-lookup"><span data-stu-id="4bd6c-114">SSO_ERROR_SSOCSTX_OUT_OF_PROC</span></span>|  
|<span data-ttu-id="4bd6c-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="4bd6c-115">Message Text</span></span>|<span data-ttu-id="4bd6c-116">ENTSSO Server COM + 应用程序配置不正确。</span><span class="sxs-lookup"><span data-stu-id="4bd6c-116">The 'ENTSSO Server' COM+ application is not configured correctly.</span></span> <span data-ttu-id="4bd6c-117">它必须是 COM + 库应用程序。</span><span class="sxs-lookup"><span data-stu-id="4bd6c-117">It must be a COM+ library application.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4bd6c-118">解释</span><span class="sxs-lookup"><span data-stu-id="4bd6c-118">Explanation</span></span>  
 <span data-ttu-id="4bd6c-119">COM + 应用程序必须配置为将 COM + 库应用程序。</span><span class="sxs-lookup"><span data-stu-id="4bd6c-119">The COM+ application must be configured as a COM+ library application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4bd6c-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="4bd6c-120">User Action</span></span>  
 <span data-ttu-id="4bd6c-121">在 ENTSSO MMC 管理单元中，展开 COM+ 文件夹并找到您的 ENTSSO Server。</span><span class="sxs-lookup"><span data-stu-id="4bd6c-121">In the ENTSSO MMC Snap-In, expand the COM+ folder and locate your ENTSSO Server.</span></span> <span data-ttu-id="4bd6c-122">右键单击此服务器，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="4bd6c-122">Right-click the server, and then click Properties.</span></span> <span data-ttu-id="4bd6c-123">选择“库应用程序”而不是“服务器应用程序”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4bd6c-123">Select Library Application instead of Server Application, and click OK.</span></span>