---
title: 单一登录：事件 11069 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1accfe68-000c-4b5e-909c-244e18eba110
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc680a452c6e70f6e10623779da1ca312f62a1fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396080"
---
# <a name="single-sign-on-event-11069"></a><span data-ttu-id="86627-102">单一登录：事件 11069</span><span class="sxs-lookup"><span data-stu-id="86627-102">Single Sign-On: Event 11069</span></span>
## <a name="details"></a><span data-ttu-id="86627-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="86627-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="86627-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="86627-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="86627-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="86627-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="86627-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="86627-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="86627-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="86627-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="86627-108">11069</span><span class="sxs-lookup"><span data-stu-id="86627-108">11069</span></span>                                                                                                         |
|  <span data-ttu-id="86627-109">事件源</span><span class="sxs-lookup"><span data-stu-id="86627-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="86627-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="86627-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="86627-111">组件</span><span class="sxs-lookup"><span data-stu-id="86627-111">Component</span></span>    |                                                                                                          <span data-ttu-id="86627-112">不可用</span><span class="sxs-lookup"><span data-stu-id="86627-112">N/A</span></span>                                                                                                          |
|  <span data-ttu-id="86627-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="86627-113">Symbolic Name</span></span>  |                                                                                             <span data-ttu-id="86627-114">SSO_WARN_PS_PCNS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="86627-114">SSO_WARN_PS_PCNS_NOT_ALLOWED</span></span>                                                                                              |
|  <span data-ttu-id="86627-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="86627-115">Message Text</span></span>   | <span data-ttu-id="86627-116">此 SSO 服务器当前未配置为允许从 PCNS 进行 Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="86627-116">This SSO server is currently not configured to allow Windows password changes from PCNS.</span></span> <span data-ttu-id="86627-117">使用 ssoconfig-allowPS PCNS yes 或 SSO 管理 MMC.%r</span><span class="sxs-lookup"><span data-stu-id="86627-117">Use 'ssoconfig -allowPS PCNS yes' or the SSO Administration MMC.%r</span></span><br /><br /> <span data-ttu-id="86627-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="86627-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="86627-119">客户端用户： %2</span><span class="sxs-lookup"><span data-stu-id="86627-119">Client User: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="86627-120">解释</span><span class="sxs-lookup"><span data-stu-id="86627-120">Explanation</span></span>  
 <span data-ttu-id="86627-121">此 SSO 服务器当前未配置为允许从 PCNS 进行 Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="86627-121">This SSO server is currently not configured to allow Windows password changes from PCNS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="86627-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="86627-122">User Action</span></span>  
 <span data-ttu-id="86627-123">若要允许从 PCNS，Windows 密码更改，在**服务器管理单元**，**密码同步属性**选项卡上，选择**允许从 PCNS 进行密码同步。**</span><span class="sxs-lookup"><span data-stu-id="86627-123">To allow Windows password changes from PCNS, in the **Servers Snap-In**, **Password Sync Properties** tab, select **Allow Password Sync from PCNS.**</span></span>  
  
 <span data-ttu-id="86627-124">有关详细信息，请参阅[如何使用服务器管理单元中](../core/how-to-use-the-servers-snap-in.md)。</span><span class="sxs-lookup"><span data-stu-id="86627-124">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>