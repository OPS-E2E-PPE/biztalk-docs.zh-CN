---
title: 可选配置 |Microsoft Docs
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
ms.openlocfilehash: f1ee8c10485522db82040210eff2a7afbc785d25
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992462"
---
# <a name="optional-configurations"></a><span data-ttu-id="b8232-102">可选配置</span><span class="sxs-lookup"><span data-stu-id="b8232-102">Optional Configurations</span></span>
<span data-ttu-id="b8232-103">导入 BizTalk Server 管理包后，监视窗格的导航窗格中显示自动发现的对象类型。</span><span class="sxs-lookup"><span data-stu-id="b8232-103">After you import the BizTalk Server Management Pack, the navigation pane of the Monitoring pane displays the object types that are discovered automatically.</span></span> <span data-ttu-id="b8232-104">对象类型的列表，请参阅[对象管理包发现](../technical-guides/objects-the-management-pack-discovers.md)部分。</span><span class="sxs-lookup"><span data-stu-id="b8232-104">For a list of object types, see [Objects the Management Pack Discovers](../technical-guides/objects-the-management-pack-discovers.md) section.</span></span> <span data-ttu-id="b8232-105">您可以修改发现的对象的默认发现配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包。</span><span class="sxs-lookup"><span data-stu-id="b8232-105">You can modify the default discovery configuration of objects discovered by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack.</span></span> <span data-ttu-id="b8232-106">使用 Operations Manager 2007 R2/2012年的替代功能更改配置设置。</span><span class="sxs-lookup"><span data-stu-id="b8232-106">You use the overrides feature of Operations Manager 2007 R2/2012 to change configuration settings.</span></span>  
  
 <span data-ttu-id="b8232-107">对于不自动发现的对象类型，可以启用针对自动发现在设置**创作**操作控制台窗格中的。</span><span class="sxs-lookup"><span data-stu-id="b8232-107">For an object type that is not automatically discovered, you can enable setting for automatic discovery in the **Authoring** pane in the Operations Console.</span></span>  
  
#### <a name="to-use-an-override-to-change-the-setting-for-automatic-discovery"></a><span data-ttu-id="b8232-108">若要使用替代更改自动发现的设置</span><span class="sxs-lookup"><span data-stu-id="b8232-108">To use an override to change the setting for automatic discovery</span></span>  
  
1. <span data-ttu-id="b8232-109">在创作窗格中，展开**管理包对象**，然后单击**对象发现**。</span><span class="sxs-lookup"><span data-stu-id="b8232-109">In the Authoring pane, expand **Management Pack Objects**, and then click **Object Discoveries**.</span></span>  
  
2. <span data-ttu-id="b8232-110">在 Operations Manager 工具栏上，单击**作用域**，筛选显示在详细信息窗格中，若要仅包括 BizTalk Server 对象的对象。</span><span class="sxs-lookup"><span data-stu-id="b8232-110">On the Operations Manager toolbar, click **Scope**, and filter the objects that appear in the details pane to include only BizTalk Server objects.</span></span>  
  
3. <span data-ttu-id="b8232-111">在详细信息窗格中，单击想要更改的设置的对象类型。</span><span class="sxs-lookup"><span data-stu-id="b8232-111">In the details pane, click the object type you want to change the setting for.</span></span>  
  
4. <span data-ttu-id="b8232-112">在 Operations Manager 工具栏上，单击**重写**，单击**替代对象发现**，然后单击**对于所有对象类型：** \< *对象类型的名称*\>，**为特定对象类型的组：** \<*对象类型的名称*\>，或**对于另一种类型的所有对象**。</span><span class="sxs-lookup"><span data-stu-id="b8232-112">On the Operations Manager toolbar, click **Overrides**, click **Override the Object Discovery**, and then click either **For all objects of type:** \<*name of object type*\>, **For a group, For a specific object of type:** \<*name of object type*\>, or **For all objects of another type**.</span></span>  
  
5. <span data-ttu-id="b8232-113">在中**重写属性**对话框中，单击**重写**框**已启用**你想要更改的参数。</span><span class="sxs-lookup"><span data-stu-id="b8232-113">In the **Override Properties** dialog box, click the **Override** box for the **Enabled** parameter you want to change.</span></span>  
  
6. <span data-ttu-id="b8232-114">下**管理包**，单击**新建**若要创建管理包的未密封的版本，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b8232-114">Under **Management Pack**, click **New** to create an unsealed version of the Management Pack, and then click **OK**.</span></span>  
  
   <span data-ttu-id="b8232-115">更改替代设置后，对象类型将被自动发现，并会在下的监视窗格中显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b8232-115">After you change the override setting, the object type will be automatically discovered and will appear in the Monitoring pane under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   <span data-ttu-id="b8232-116">有关设置替代的信息，请参阅[Operations Manager 2007 R2/2012年中重写](http://go.microsoft.com/fwlink/?LinkId=86870)(http://go.microsoft.com/fwlink/?LinkId=86870)。</span><span class="sxs-lookup"><span data-stu-id="b8232-116">For information about setting overrides, see [Overrides in Operations Manager 2007 R2/2012](http://go.microsoft.com/fwlink/?LinkId=86870) (http://go.microsoft.com/fwlink/?LinkId=86870).</span></span>