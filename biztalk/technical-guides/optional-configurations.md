---
title: 可选配置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f4b0b51-2cad-4cb5-b6cd-4db92bd199fa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b19646c9c83eff4a3171b4d25763a6b581d45b1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976755"
---
# <a name="optional-configurations"></a><span data-ttu-id="ddedc-102">可选配置</span><span class="sxs-lookup"><span data-stu-id="ddedc-102">Optional Configurations</span></span>
<span data-ttu-id="ddedc-103">BizTalk Server 管理包导入后，监视窗格的导航窗格中显示自动发现的对象类型。</span><span class="sxs-lookup"><span data-stu-id="ddedc-103">After you import the BizTalk Server Management Pack, the navigation pane of the Monitoring pane displays the object types that are discovered automatically.</span></span> <span data-ttu-id="ddedc-104">对象类型的列表，请参阅[对象管理包发现](../technical-guides/objects-the-management-pack-discovers.md)部分。</span><span class="sxs-lookup"><span data-stu-id="ddedc-104">For a list of object types, see [Objects the Management Pack Discovers](../technical-guides/objects-the-management-pack-discovers.md) section.</span></span> <span data-ttu-id="ddedc-105">你可以修改由发现的对象的默认发现配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包。</span><span class="sxs-lookup"><span data-stu-id="ddedc-105">You can modify the default discovery configuration of objects discovered by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack.</span></span> <span data-ttu-id="ddedc-106">使用 Operations Manager 2007 R2/2012年的替代功能更改配置设置。</span><span class="sxs-lookup"><span data-stu-id="ddedc-106">You use the overrides feature of Operations Manager 2007 R2/2012 to change configuration settings.</span></span>  
  
 <span data-ttu-id="ddedc-107">对于不自动发现的对象类型，你可以启用自动发现在设置**创作**在操作控制台窗格。</span><span class="sxs-lookup"><span data-stu-id="ddedc-107">For an object type that is not automatically discovered, you can enable setting for automatic discovery in the **Authoring** pane in the Operations Console.</span></span>  
  
#### <a name="to-use-an-override-to-change-the-setting-for-automatic-discovery"></a><span data-ttu-id="ddedc-108">若要使用替代更改自动发现的设置</span><span class="sxs-lookup"><span data-stu-id="ddedc-108">To use an override to change the setting for automatic discovery</span></span>  
  
1.  <span data-ttu-id="ddedc-109">在创作窗格中，展开**管理包对象**，然后单击**对象发现**。</span><span class="sxs-lookup"><span data-stu-id="ddedc-109">In the Authoring pane, expand **Management Pack Objects**, and then click **Object Discoveries**.</span></span>  
  
2.  <span data-ttu-id="ddedc-110">在 Operations Manager 工具栏上，单击**作用域**，筛选以仅包括 BizTalk Server 对象的详细信息窗格中显示的对象。</span><span class="sxs-lookup"><span data-stu-id="ddedc-110">On the Operations Manager toolbar, click **Scope**, and filter the objects that appear in the details pane to include only BizTalk Server objects.</span></span>  
  
3.  <span data-ttu-id="ddedc-111">在详细信息窗格中，单击你想要更改的设置的对象类型。</span><span class="sxs-lookup"><span data-stu-id="ddedc-111">In the details pane, click the object type you want to change the setting for.</span></span>  
  
4.  <span data-ttu-id="ddedc-112">在 Operations Manager 工具栏上，单击**重写**，单击**替代对象发现**，然后单击**对于的所有对象类型：** \< *对象类型的名称*\>，**对于组，对于特定对象类型：** \<*对象类型的名称*\>，或**对于另一种类型的所有对象**。</span><span class="sxs-lookup"><span data-stu-id="ddedc-112">On the Operations Manager toolbar, click **Overrides**, click **Override the Object Discovery**, and then click either **For all objects of type:** \<*name of object type*\>, **For a group, For a specific object of type:** \<*name of object type*\>, or **For all objects of another type**.</span></span>  
  
5.  <span data-ttu-id="ddedc-113">在**替代属性**对话框中，单击**重写**框**已启用**你想要更改的参数。</span><span class="sxs-lookup"><span data-stu-id="ddedc-113">In the **Override Properties** dialog box, click the **Override** box for the **Enabled** parameter you want to change.</span></span>  
  
6.  <span data-ttu-id="ddedc-114">下**管理包**，单击**新建**若要创建管理包的未密封的版本，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ddedc-114">Under **Management Pack**, click **New** to create an unsealed version of the Management Pack, and then click **OK**.</span></span>  
  
 <span data-ttu-id="ddedc-115">更改替代设置后，对象类型将被自动发现，并将显示在下的监视窗格中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ddedc-115">After you change the override setting, the object type will be automatically discovered and will appear in the Monitoring pane under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ddedc-116">有关设置替代的信息，请参阅[在 Operations Manager 2007 R2/2012年中重写](http://go.microsoft.com/fwlink/?LinkId=86870)(http://go.microsoft.com/fwlink/?LinkId=86870)。</span><span class="sxs-lookup"><span data-stu-id="ddedc-116">For information about setting overrides, see [Overrides in Operations Manager 2007 R2/2012](http://go.microsoft.com/fwlink/?LinkId=86870) (http://go.microsoft.com/fwlink/?LinkId=86870).</span></span>