---
title: 适配器组和组适配器 |Microsoft 文档
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
ms.openlocfilehash: fcf10f50857026893245cc567783b649f614c4f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225373"
---
# <a name="adapter-groups-and-group-adapters"></a><span data-ttu-id="557d9-102">适配器组和组适配器</span><span class="sxs-lookup"><span data-stu-id="557d9-102">Adapter Groups and Group Adapters</span></span>
<span data-ttu-id="557d9-103">*适配器组*是一种管理机制，可用于收集和组织的适配器集。</span><span class="sxs-lookup"><span data-stu-id="557d9-103">An *adapter group* is an administration mechanism that you can use to collect and organize a set of adapters.</span></span> <span data-ttu-id="557d9-104">与此相反，*组适配器*是服务的适配器组中的所有适配器的组件。</span><span class="sxs-lookup"><span data-stu-id="557d9-104">In contrast, a *group adapter* is a component that services all adapters in an adapter group.</span></span> <span data-ttu-id="557d9-105">例如，您可以编写一组全部使用相同的 COM 组件，通过 TCP/IP 传输密码同步的适配器。</span><span class="sxs-lookup"><span data-stu-id="557d9-105">For example, you might write a set of adapters that all use the same COM component to transmit password synchronizations over TCP/IP.</span></span> <span data-ttu-id="557d9-106">这一组适配器称为适配器组，而为所有这些适配器提供服务的组件称为组适配器。</span><span class="sxs-lookup"><span data-stu-id="557d9-106">Your set of adapters is called the adapter group, whereas the component that services them all is called a group adapter.</span></span> <span data-ttu-id="557d9-107">适配器组在配置存储中进行描述。</span><span class="sxs-lookup"><span data-stu-id="557d9-107">Adapter groups are described in the configuration store.</span></span> <span data-ttu-id="557d9-108">你可以通过使用来检索信息和适配器组上的更新`ISSOPSAdapter.ReceiveNotification`。</span><span class="sxs-lookup"><span data-stu-id="557d9-108">You can retrieve information and updates on an adapter group by using `ISSOPSAdapter.ReceiveNotification`.</span></span>  
  
 <span data-ttu-id="557d9-109">组适配器与适配器组同名。</span><span class="sxs-lookup"><span data-stu-id="557d9-109">A group adapter has the same name as the adapter group.</span></span> <span data-ttu-id="557d9-110">除了命名限制之外，组适配器在其他方面与普通的适配器是相同的。</span><span class="sxs-lookup"><span data-stu-id="557d9-110">Other than the naming restriction, a group adapter is otherwise identical to a normal adapter.</span></span> <span data-ttu-id="557d9-111">例如，组适配器可以具有其配置文件中所描述的独立的访问组和配置属性。</span><span class="sxs-lookup"><span data-stu-id="557d9-111">For example, a group adapter can have independent access groups and configuration properties, as described by its configuration file.</span></span> <span data-ttu-id="557d9-112">组适配器很可能与适配器组中的某个适配器位于同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="557d9-112">A group adapter is most likely on the same computer as any adapters in the adapter group.</span></span> <span data-ttu-id="557d9-113">不过，目前这并不是强制性的规定。</span><span class="sxs-lookup"><span data-stu-id="557d9-113">However, this is not currently enforced.</span></span> <span data-ttu-id="557d9-114">同样，同一适配器组中的所有适配器可以位于同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="557d9-114">Likewise, all adapters in the same adapter group can be expected to be on the same computer.</span></span>  
  
 <span data-ttu-id="557d9-115">通过使用`ISSOPSAdapter.InitializeAdapter`，您可以访问并在启动期间初始化组适配器。</span><span class="sxs-lookup"><span data-stu-id="557d9-115">By using `ISSOPSAdapter.InitializeAdapter`, you can access and initialize a group adapter during startup.</span></span> <span data-ttu-id="557d9-116">在初始化组适配器时，系统会通知当前系统上的适配器组中所有适配器的组适配器。</span><span class="sxs-lookup"><span data-stu-id="557d9-116">When you initialize a group adapter, the system informs the group adapter of all adapters in the adapter group on the current system.</span></span> <span data-ttu-id="557d9-117">此外，在适配器组中添加、删除、启用或禁用适配器时，系统将向组适配器发送通知。</span><span class="sxs-lookup"><span data-stu-id="557d9-117">In addition, the system sends notifications to the group adapter any time an adapter is added, deleted, enabled, or disabled in the adapter group.</span></span> <span data-ttu-id="557d9-118">不过，组适配器不接收任何密码更改通知。</span><span class="sxs-lookup"><span data-stu-id="557d9-118">However, the group adapter does not receive any password change notifications.</span></span>  
  
 <span data-ttu-id="557d9-119">适配器组和组适配器均可使用管理工具进行选择。</span><span class="sxs-lookup"><span data-stu-id="557d9-119">Adapter groups and group adapters are optional using the Administration tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="557d9-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="557d9-120">See Also</span></span>  
 [<span data-ttu-id="557d9-121">密码同步适配器</span><span class="sxs-lookup"><span data-stu-id="557d9-121">Password Sync Adapters</span></span>](../core/password-sync-adapters.md)