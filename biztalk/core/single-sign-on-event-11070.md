---
title: "单一登录： 事件 11070 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb669df9-710a-4792-bdd4-cca0c03fcda2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb0d2a868d5c8bf47cbcb5389bf2d16dadf4010a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11070"></a><span data-ttu-id="0b5ff-102">单一登录： 事件 11070</span><span class="sxs-lookup"><span data-stu-id="0b5ff-102">Single Sign-On: Event 11070</span></span>
## <a name="details"></a><span data-ttu-id="0b5ff-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0b5ff-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b5ff-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0b5ff-104">Product Name</span></span>|<span data-ttu-id="0b5ff-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0b5ff-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0b5ff-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0b5ff-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0b5ff-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0b5ff-107">Event ID</span></span>|<span data-ttu-id="0b5ff-108">11070</span><span class="sxs-lookup"><span data-stu-id="0b5ff-108">11070</span></span>|  
|<span data-ttu-id="0b5ff-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0b5ff-109">Event Source</span></span>|<span data-ttu-id="0b5ff-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0b5ff-110">ENTSSO</span></span>|  
|<span data-ttu-id="0b5ff-111">组件</span><span class="sxs-lookup"><span data-stu-id="0b5ff-111">Component</span></span>|<span data-ttu-id="0b5ff-112">N/A</span><span class="sxs-lookup"><span data-stu-id="0b5ff-112">N/A</span></span>|  
|<span data-ttu-id="0b5ff-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0b5ff-113">Symbolic Name</span></span>|<span data-ttu-id="0b5ff-114">SSO_WARN_PS_MIIS_NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="0b5ff-114">SSO_WARN_PS_MIIS_NOT_ALLOWED</span></span>|  
|<span data-ttu-id="0b5ff-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0b5ff-115">Message Text</span></span>|<span data-ttu-id="0b5ff-116">此 SSO 服务器当前未配置为允许从 MIIS 执行 Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="0b5ff-116">This SSO server is currently not configured to allow Windows password changes from MIIS.</span></span> <span data-ttu-id="0b5ff-117">请使用“ssoconfig -allowPS MIIS yes”或 SSO 管理 MMC。%r</span><span class="sxs-lookup"><span data-stu-id="0b5ff-117">Use 'ssoconfig -allowPS MIIS yes' or the SSO Administration MMC.%r</span></span><br /><br /> <span data-ttu-id="0b5ff-118">跟踪 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="0b5ff-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="0b5ff-119">客户端用户： %2</span><span class="sxs-lookup"><span data-stu-id="0b5ff-119">Client User: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0b5ff-120">解释</span><span class="sxs-lookup"><span data-stu-id="0b5ff-120">Explanation</span></span>  
 <span data-ttu-id="0b5ff-121">此 SSO 服务器当前未配置为允许从 MIIS 执行 Windows 密码更改。</span><span class="sxs-lookup"><span data-stu-id="0b5ff-121">This SSO server is currently not configured to allow Windows password changes from MIIS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b5ff-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="0b5ff-122">User Action</span></span>  
 <span data-ttu-id="0b5ff-123">若要允许从 miis 进行，在中使用 Windows 密码更改**服务器管理单元中**，**密码同步属性**选项卡上，选择**允许从 miis 进行的密码同步。**</span><span class="sxs-lookup"><span data-stu-id="0b5ff-123">To allow Windows password changes from MIIS, in the **Servers Snap-In**, **Password Sync Properties** tab, select **Allow Password Sync from MIIS.**</span></span>  
  
 <span data-ttu-id="0b5ff-124">有关详细信息，请参阅[如何使用服务器管理单元](../core/how-to-use-the-servers-snap-in.md)。</span><span class="sxs-lookup"><span data-stu-id="0b5ff-124">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>