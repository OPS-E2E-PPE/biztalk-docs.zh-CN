---
title: 适配器组和组适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e0a9423-99dd-4474-afa1-fd8e1d074cd1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33cba4d210f79072f5f36a0a47e8546b2d2db265
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361451"
---
# <a name="adapter-groups-and-group-adapters"></a><span data-ttu-id="e5d66-102">适配器组和组适配器</span><span class="sxs-lookup"><span data-stu-id="e5d66-102">Adapter Groups and Group Adapters</span></span>
<span data-ttu-id="e5d66-103">*适配器组*是一种管理机制，可用于收集和组织一组适配器。</span><span class="sxs-lookup"><span data-stu-id="e5d66-103">An *adapter group* is an administration mechanism that you can use to collect and organize a set of adapters.</span></span> <span data-ttu-id="e5d66-104">与此相反，*组适配器*是服务适配器组中的所有适配器的组件。</span><span class="sxs-lookup"><span data-stu-id="e5d66-104">In contrast, a *group adapter* is a component that services all adapters in an adapter group.</span></span> <span data-ttu-id="e5d66-105">例如，您可能编写的适配器集所有使用相同的 COM 组件通过 TCP/IP 传输密码同步。</span><span class="sxs-lookup"><span data-stu-id="e5d66-105">For example, you might write a set of adapters that all use the same COM component to transmit password synchronizations over TCP/IP.</span></span> <span data-ttu-id="e5d66-106">适配器称为适配器组，而所有这些服务的组件称为组适配器。</span><span class="sxs-lookup"><span data-stu-id="e5d66-106">Your set of adapters is called the adapter group, whereas the component that services them all is called a group adapter.</span></span> <span data-ttu-id="e5d66-107">适配器组所述配置存储区。</span><span class="sxs-lookup"><span data-stu-id="e5d66-107">Adapter groups are described in the configuration store.</span></span> <span data-ttu-id="e5d66-108">可以通过使用检索信息和更新有关适配器组`ISSOPSAdapter.ReceiveNotification`。</span><span class="sxs-lookup"><span data-stu-id="e5d66-108">You can retrieve information and updates on an adapter group by using `ISSOPSAdapter.ReceiveNotification`.</span></span>  
  
 <span data-ttu-id="e5d66-109">组适配器已与适配器组相同的名称。</span><span class="sxs-lookup"><span data-stu-id="e5d66-109">A group adapter has the same name as the adapter group.</span></span> <span data-ttu-id="e5d66-110">以外的命名限制，组适配器在其他方面与普通的适配器。</span><span class="sxs-lookup"><span data-stu-id="e5d66-110">Other than the naming restriction, a group adapter is otherwise identical to a normal adapter.</span></span> <span data-ttu-id="e5d66-111">例如，组适配器可以具有独立的访问组和配置属性，如其配置文件中所述。</span><span class="sxs-lookup"><span data-stu-id="e5d66-111">For example, a group adapter can have independent access groups and configuration properties, as described by its configuration file.</span></span> <span data-ttu-id="e5d66-112">组适配器很有可能与适配器组中的任何适配器所在的计算机上。</span><span class="sxs-lookup"><span data-stu-id="e5d66-112">A group adapter is most likely on the same computer as any adapters in the adapter group.</span></span> <span data-ttu-id="e5d66-113">但是，这是不是当前实施的。</span><span class="sxs-lookup"><span data-stu-id="e5d66-113">However, this is not currently enforced.</span></span> <span data-ttu-id="e5d66-114">同样，可以预期相同的适配器组中所有适配器可在同一计算机上。</span><span class="sxs-lookup"><span data-stu-id="e5d66-114">Likewise, all adapters in the same adapter group can be expected to be on the same computer.</span></span>  
  
 <span data-ttu-id="e5d66-115">通过使用`ISSOPSAdapter.InitializeAdapter`，可以访问并在启动期间初始化组适配器。</span><span class="sxs-lookup"><span data-stu-id="e5d66-115">By using `ISSOPSAdapter.InitializeAdapter`, you can access and initialize a group adapter during startup.</span></span> <span data-ttu-id="e5d66-116">在初始化组适配器时，系统会通知当前系统上的适配器组中的所有适配器的组适配器。</span><span class="sxs-lookup"><span data-stu-id="e5d66-116">When you initialize a group adapter, the system informs the group adapter of all adapters in the adapter group on the current system.</span></span> <span data-ttu-id="e5d66-117">此外，系统将通知发送到组适配器适配器是添加、 删除、 启用或禁用适配器组中的任何时间。</span><span class="sxs-lookup"><span data-stu-id="e5d66-117">In addition, the system sends notifications to the group adapter any time an adapter is added, deleted, enabled, or disabled in the adapter group.</span></span> <span data-ttu-id="e5d66-118">但是，组适配器不接收任何密码更改通知。</span><span class="sxs-lookup"><span data-stu-id="e5d66-118">However, the group adapter does not receive any password change notifications.</span></span>  
  
 <span data-ttu-id="e5d66-119">适配器组和组适配器是可选使用管理工具。</span><span class="sxs-lookup"><span data-stu-id="e5d66-119">Adapter groups and group adapters are optional using the Administration tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d66-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5d66-120">See Also</span></span>  
 [<span data-ttu-id="e5d66-121">密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="e5d66-121">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)