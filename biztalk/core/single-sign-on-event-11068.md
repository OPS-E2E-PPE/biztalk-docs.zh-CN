---
title: 单一登录：事件 11068 |Microsoft Docs
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
ms.openlocfilehash: 634fdcb87698628e2a579028ea8fad11ac035d27
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530775"
---
# <a name="single-sign-on-event-11068"></a><span data-ttu-id="a9cdc-102">单一登录：事件 11068</span><span class="sxs-lookup"><span data-stu-id="a9cdc-102">Single Sign-On: Event 11068</span></span>
## <a name="details"></a><span data-ttu-id="a9cdc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a9cdc-103">Details</span></span>  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a9cdc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a9cdc-104">Product Name</span></span>   |                                                                      <span data-ttu-id="a9cdc-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="a9cdc-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="a9cdc-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="a9cdc-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="a9cdc-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a9cdc-107">Event ID</span></span>     |                                                                                <span data-ttu-id="a9cdc-108">11068</span><span class="sxs-lookup"><span data-stu-id="a9cdc-108">11068</span></span>                                                                                |
|  <span data-ttu-id="a9cdc-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a9cdc-109">Event Source</span></span>   |                                                                               <span data-ttu-id="a9cdc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a9cdc-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="a9cdc-111">组件</span><span class="sxs-lookup"><span data-stu-id="a9cdc-111">Component</span></span>    |                                                                                 <span data-ttu-id="a9cdc-112">不可用</span><span class="sxs-lookup"><span data-stu-id="a9cdc-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="a9cdc-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a9cdc-113">Symbolic Name</span></span>  |                                                          <span data-ttu-id="a9cdc-114">SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE</span><span class="sxs-lookup"><span data-stu-id="a9cdc-114">SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE</span></span>                                                          |
|  <span data-ttu-id="a9cdc-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="a9cdc-115">Message Text</span></span>   | <span data-ttu-id="a9cdc-116">查找服务器访问被拒绝。</span><span class="sxs-lookup"><span data-stu-id="a9cdc-116">Lookup server access denied.</span></span> <span data-ttu-id="a9cdc-117">此 SSO 服务器当前未配置为允许远程查找。</span><span class="sxs-lookup"><span data-stu-id="a9cdc-117">This SSO server is currently not configured to allow remote lookup.</span></span> <span data-ttu-id="a9cdc-118">使用 ssoconfig-remoteLookup yes 或 SSO 管理 MMC.%r</span><span class="sxs-lookup"><span data-stu-id="a9cdc-118">Use 'ssoconfig -remoteLookup yes' or the SSO Administration MMC.%r</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a9cdc-119">解释</span><span class="sxs-lookup"><span data-stu-id="a9cdc-119">Explanation</span></span>  
 <span data-ttu-id="a9cdc-120">查找服务器访问被拒绝，因为 ENTSSO 服务器未配置为允许远程查找。</span><span class="sxs-lookup"><span data-stu-id="a9cdc-120">Lookup server access has been denied because the ENTSSO server is not configured to allow remote lookup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a9cdc-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="a9cdc-121">User Action</span></span>  
 <span data-ttu-id="a9cdc-122">若要允许远程查找，在**服务器管理单元**，**高级**选项卡上，选择**允许远程查找**。</span><span class="sxs-lookup"><span data-stu-id="a9cdc-122">To allow remote lookup, in the **Servers Snap-In**, **Advanced** tab, select **Allow Remote Lookup**.</span></span>  
  
 <span data-ttu-id="a9cdc-123">有关详细信息，请参阅[如何使用服务器管理单元中](../core/how-to-use-the-servers-snap-in.md)。</span><span class="sxs-lookup"><span data-stu-id="a9cdc-123">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>