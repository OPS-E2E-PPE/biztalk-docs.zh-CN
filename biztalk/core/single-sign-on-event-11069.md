---
title: 单一登录： 事件 11069 |Microsoft Docs
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
ms.openlocfilehash: 1e9df27e7a5ac5f4fcedb10935fb8e63a6e0bea0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986158"
---
# <a name="single-sign-on-event-11069"></a><span data-ttu-id="d1f25-102">单一登录： 事件 11069</span><span class="sxs-lookup"><span data-stu-id="d1f25-102">Single Sign-On: Event 11069</span></span>
## <a name="details"></a><span data-ttu-id="d1f25-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d1f25-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d1f25-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d1f25-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="d1f25-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d1f25-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="d1f25-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d1f25-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="d1f25-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d1f25-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="d1f25-108">11069</span><span class="sxs-lookup"><span data-stu-id="d1f25-108">11069</span></span>                                                                                                         |
|  <span data-ttu-id="d1f25-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d1f25-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="d1f25-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d1f25-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="d1f25-111">组件</span><span class="sxs-lookup"><span data-stu-id="d1f25-111">Component</span></span>    |                                                                                                          <span data-ttu-id="d1f25-112">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f25-112">N/A</span></span>                                                                                                          |
|  <span data-ttu-id="d1f25-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d1f25-113">Symbolic Name</span></span>  |                                                                                             <span data-ttu-id="d1f25-114">SSO_WARN_PS_PCNS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="d1f25-114">SSO_WARN_PS_PCNS_NOT_ALLOWED</span></span>                                                                                              |
|  <span data-ttu-id="d1f25-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d1f25-115">Message Text</span></span>   | <span data-ttu-id="d1f25-116">此 SSO 服务器当前未配置为允许从 PCNS 更改 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="d1f25-116">This SSO server is currently not configured to allow Windows password changes from PCNS.</span></span> <span data-ttu-id="d1f25-117">使用“ssoconfig-allowPS PCNS yes”或 SSO 管理 MMC。%r</span><span class="sxs-lookup"><span data-stu-id="d1f25-117">Use 'ssoconfig -allowPS PCNS yes' or the SSO Administration MMC.%r</span></span><br /><br /> <span data-ttu-id="d1f25-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d1f25-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="d1f25-119">客户端用户： %2</span><span class="sxs-lookup"><span data-stu-id="d1f25-119">Client User: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d1f25-120">解释</span><span class="sxs-lookup"><span data-stu-id="d1f25-120">Explanation</span></span>  
 <span data-ttu-id="d1f25-121">此 SSO 服务器当前未配置为允许从 PCNS 更改 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="d1f25-121">This SSO server is currently not configured to allow Windows password changes from PCNS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d1f25-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="d1f25-122">User Action</span></span>  
 <span data-ttu-id="d1f25-123">若要允许从 PCNS，Windows 密码更改，在**服务器管理单元**，**密码同步属性**选项卡上，选择**允许从 PCNS 进行密码同步。**</span><span class="sxs-lookup"><span data-stu-id="d1f25-123">To allow Windows password changes from PCNS, in the **Servers Snap-In**, **Password Sync Properties** tab, select **Allow Password Sync from PCNS.**</span></span>  
  
 <span data-ttu-id="d1f25-124">有关详细信息，请参阅[如何使用服务器管理单元中](../core/how-to-use-the-servers-snap-in.md)。</span><span class="sxs-lookup"><span data-stu-id="d1f25-124">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>