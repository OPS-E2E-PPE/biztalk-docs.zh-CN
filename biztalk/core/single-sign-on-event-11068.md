---
title: 单一登录： 事件 11068 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f09a1191-ae67-4156-a8a5-d24e4439fc68
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 218da642493981211de4a0e10b504ea8f434945f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020491"
---
# <a name="single-sign-on-event-11068"></a><span data-ttu-id="defa0-102">单一登录： 事件 11068</span><span class="sxs-lookup"><span data-stu-id="defa0-102">Single Sign-On: Event 11068</span></span>
## <a name="details"></a><span data-ttu-id="defa0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="defa0-103">Details</span></span>  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="defa0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="defa0-104">Product Name</span></span>   |                                                                      <span data-ttu-id="defa0-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="defa0-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="defa0-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="defa0-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="defa0-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="defa0-107">Event ID</span></span>     |                                                                                <span data-ttu-id="defa0-108">11068</span><span class="sxs-lookup"><span data-stu-id="defa0-108">11068</span></span>                                                                                |
|  <span data-ttu-id="defa0-109">事件源</span><span class="sxs-lookup"><span data-stu-id="defa0-109">Event Source</span></span>   |                                                                               <span data-ttu-id="defa0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="defa0-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="defa0-111">组件</span><span class="sxs-lookup"><span data-stu-id="defa0-111">Component</span></span>    |                                                                                 <span data-ttu-id="defa0-112">N/A</span><span class="sxs-lookup"><span data-stu-id="defa0-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="defa0-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="defa0-113">Symbolic Name</span></span>  |                                                          <span data-ttu-id="defa0-114">SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE</span><span class="sxs-lookup"><span data-stu-id="defa0-114">SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE</span></span>                                                          |
|  <span data-ttu-id="defa0-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="defa0-115">Message Text</span></span>   | <span data-ttu-id="defa0-116">查找服务器访问被拒绝。</span><span class="sxs-lookup"><span data-stu-id="defa0-116">Lookup server access denied.</span></span> <span data-ttu-id="defa0-117">此 SSO 服务器当前未配置为允许远程查找。</span><span class="sxs-lookup"><span data-stu-id="defa0-117">This SSO server is currently not configured to allow remote lookup.</span></span> <span data-ttu-id="defa0-118">请使用“ssoconfig -remoteLookup yes”或 SSO 管理 MMC。%r</span><span class="sxs-lookup"><span data-stu-id="defa0-118">Use 'ssoconfig -remoteLookup yes' or the SSO Administration MMC.%r</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="defa0-119">解释</span><span class="sxs-lookup"><span data-stu-id="defa0-119">Explanation</span></span>  
 <span data-ttu-id="defa0-120">由于 ENTSSO 服务器未配置为允许远程查找，因此查找服务器访问已被拒绝。</span><span class="sxs-lookup"><span data-stu-id="defa0-120">Lookup server access has been denied because the ENTSSO server is not configured to allow remote lookup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="defa0-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="defa0-121">User Action</span></span>  
 <span data-ttu-id="defa0-122">若要允许远程查找，在**服务器管理单元**，**高级**选项卡上，选择**允许远程查找**。</span><span class="sxs-lookup"><span data-stu-id="defa0-122">To allow remote lookup, in the **Servers Snap-In**, **Advanced** tab, select **Allow Remote Lookup**.</span></span>  
  
 <span data-ttu-id="defa0-123">有关详细信息，请参阅[如何使用服务器管理单元中](../core/how-to-use-the-servers-snap-in.md)。</span><span class="sxs-lookup"><span data-stu-id="defa0-123">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>