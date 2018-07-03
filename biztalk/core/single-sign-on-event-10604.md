---
title: 单一登录： 事件 10604 |Microsoft Docs
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
ms.openlocfilehash: 48996ec333c9035e57393e270db06ca173cfc9e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990582"
---
# <a name="single-sign-on-event-10604"></a><span data-ttu-id="07b16-102">单一登录： 事件 10604</span><span class="sxs-lookup"><span data-stu-id="07b16-102">Single Sign-On: Event 10604</span></span>
## <a name="details"></a><span data-ttu-id="07b16-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="07b16-103">Details</span></span>  
  
|                 |                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="07b16-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="07b16-104">Product Name</span></span>   |                                        <span data-ttu-id="07b16-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="07b16-105">Enterprise Single Sign-On</span></span>                                         |
| <span data-ttu-id="07b16-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="07b16-106">Product Version</span></span> |                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                        |
|    <span data-ttu-id="07b16-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="07b16-107">Event ID</span></span>     |                                                  <span data-ttu-id="07b16-108">10604</span><span class="sxs-lookup"><span data-stu-id="07b16-108">10604</span></span>                                                   |
|  <span data-ttu-id="07b16-109">事件源</span><span class="sxs-lookup"><span data-stu-id="07b16-109">Event Source</span></span>   |                                                  <span data-ttu-id="07b16-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="07b16-110">ENTSSO</span></span>                                                  |
|    <span data-ttu-id="07b16-111">组件</span><span class="sxs-lookup"><span data-stu-id="07b16-111">Component</span></span>    |                                                   <span data-ttu-id="07b16-112">N/A</span><span class="sxs-lookup"><span data-stu-id="07b16-112">N/A</span></span>                                                    |
|  <span data-ttu-id="07b16-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="07b16-113">Symbolic Name</span></span>  |                                      <span data-ttu-id="07b16-114">SSO_ERROR_SSOCSTX_OUT_OF_PROC</span><span class="sxs-lookup"><span data-stu-id="07b16-114">SSO_ERROR_SSOCSTX_OUT_OF_PROC</span></span>                                       |
|  <span data-ttu-id="07b16-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="07b16-115">Message Text</span></span>   | <span data-ttu-id="07b16-116">ENTSSO Server COM + 应用程序配置不正确。</span><span class="sxs-lookup"><span data-stu-id="07b16-116">The 'ENTSSO Server' COM+ application is not configured correctly.</span></span> <span data-ttu-id="07b16-117">它必须是 COM + 库应用程序。</span><span class="sxs-lookup"><span data-stu-id="07b16-117">It must be a COM+ library application.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="07b16-118">解释</span><span class="sxs-lookup"><span data-stu-id="07b16-118">Explanation</span></span>  
 <span data-ttu-id="07b16-119">COM + 应用程序必须配置为 COM + 库应用程序。</span><span class="sxs-lookup"><span data-stu-id="07b16-119">The COM+ application must be configured as a COM+ library application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07b16-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="07b16-120">User Action</span></span>  
 <span data-ttu-id="07b16-121">在 ENTSSO MMC 管理单元中，展开 COM+ 文件夹并找到您的 ENTSSO Server。</span><span class="sxs-lookup"><span data-stu-id="07b16-121">In the ENTSSO MMC Snap-In, expand the COM+ folder and locate your ENTSSO Server.</span></span> <span data-ttu-id="07b16-122">右键单击此服务器，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="07b16-122">Right-click the server, and then click Properties.</span></span> <span data-ttu-id="07b16-123">选择“库应用程序”而不是“服务器应用程序”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="07b16-123">Select Library Application instead of Server Application, and click OK.</span></span>