---
title: 单一登录： 事件 11070 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb669df9-710a-4792-bdd4-cca0c03fcda2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 799e175f6425b91c98f6e96ec9f0bd73d8d0ebdf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994318"
---
# <a name="single-sign-on-event-11070"></a><span data-ttu-id="533ef-102">单一登录： 事件 11070</span><span class="sxs-lookup"><span data-stu-id="533ef-102">Single Sign-On: Event 11070</span></span>
## <a name="details"></a><span data-ttu-id="533ef-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="533ef-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="533ef-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="533ef-104">Product Name</span></span>   |                                                                                               <span data-ttu-id="533ef-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="533ef-105">Enterprise Single Sign-On</span></span>                                                                                               |
| <span data-ttu-id="533ef-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="533ef-106">Product Version</span></span> |                                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    <span data-ttu-id="533ef-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="533ef-107">Event ID</span></span>     |                                                                                                         <span data-ttu-id="533ef-108">11070</span><span class="sxs-lookup"><span data-stu-id="533ef-108">11070</span></span>                                                                                                         |
|  <span data-ttu-id="533ef-109">事件源</span><span class="sxs-lookup"><span data-stu-id="533ef-109">Event Source</span></span>   |                                                                                                        <span data-ttu-id="533ef-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="533ef-110">ENTSSO</span></span>                                                                                                         |
|    <span data-ttu-id="533ef-111">组件</span><span class="sxs-lookup"><span data-stu-id="533ef-111">Component</span></span>    |                                                                                                          <span data-ttu-id="533ef-112">N/A</span><span class="sxs-lookup"><span data-stu-id="533ef-112">N/A</span></span>                                                                                                          |
|  <span data-ttu-id="533ef-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="533ef-113">Symbolic Name</span></span>  |                                                                                             <span data-ttu-id="533ef-114">SSO_WARN_PS_MIIS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="533ef-114">SSO_WARN_PS_MIIS_NOT_ALLOWED</span></span>                                                                                              |
|  <span data-ttu-id="533ef-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="533ef-115">Message Text</span></span>   | <span data-ttu-id="533ef-116">此 SSO 服务器当前未配置为允许从 MIIS 执行 Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="533ef-116">This SSO server is currently not configured to allow Windows password changes from MIIS.</span></span> <span data-ttu-id="533ef-117">请使用“ssoconfig -allowPS MIIS yes”或 SSO 管理 MMC。%r</span><span class="sxs-lookup"><span data-stu-id="533ef-117">Use 'ssoconfig -allowPS MIIS yes' or the SSO Administration MMC.%r</span></span><br /><br /> <span data-ttu-id="533ef-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="533ef-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="533ef-119">客户端用户： %2</span><span class="sxs-lookup"><span data-stu-id="533ef-119">Client User: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="533ef-120">解释</span><span class="sxs-lookup"><span data-stu-id="533ef-120">Explanation</span></span>  
 <span data-ttu-id="533ef-121">此 SSO 服务器当前未配置为允许从 MIIS 执行 Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="533ef-121">This SSO server is currently not configured to allow Windows password changes from MIIS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="533ef-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="533ef-122">User Action</span></span>  
 <span data-ttu-id="533ef-123">若要允许从 MIIS 中的 Windows 密码更改**服务器管理单元**，**密码同步属性**选项卡上，选择**允许从 MIIS 进行密码同步。**</span><span class="sxs-lookup"><span data-stu-id="533ef-123">To allow Windows password changes from MIIS, in the **Servers Snap-In**, **Password Sync Properties** tab, select **Allow Password Sync from MIIS.**</span></span>  
  
 <span data-ttu-id="533ef-124">有关详细信息，请参阅[如何使用服务器管理单元中](../core/how-to-use-the-servers-snap-in.md)。</span><span class="sxs-lookup"><span data-stu-id="533ef-124">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>