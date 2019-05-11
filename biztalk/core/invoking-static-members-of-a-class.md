---
title: 调用类的静态成员 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a51171c-8de0-45dd-8659-f674cf27acbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 419b83518a9a5cbda54326cf757458afbcdd369b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329834"
---
# <a name="invoking-static-members-of-a-class"></a><span data-ttu-id="50976-102">调用类的静态成员</span><span class="sxs-lookup"><span data-stu-id="50976-102">Invoking Static Members of a Class</span></span>
<span data-ttu-id="50976-103">默认情况下，规则引擎要求你断言.NET 类来执行策略调用.NET 类的静态成员的实例。</span><span class="sxs-lookup"><span data-stu-id="50976-103">By default, the rule engine requires you to assert an instance of a .NET class to execute a policy that invokes a static member of the .NET class.</span></span> <span data-ttu-id="50976-104">您可以通过更改的值修改此行为**StaticSupport**注册表项下的**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**为下表中的值之一。</span><span class="sxs-lookup"><span data-stu-id="50976-104">You can modify this behavior by changing the value of the **StaticSupport** registry key under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0** to one of the values in the following table.</span></span>  
  
|<span data-ttu-id="50976-105">StaticSupport 注册表值</span><span class="sxs-lookup"><span data-stu-id="50976-105">StaticSupport registry value</span></span>|<span data-ttu-id="50976-106">规则引擎行为</span><span class="sxs-lookup"><span data-stu-id="50976-106">Rule engine behavior</span></span>|  
|----------------------------------|--------------------------|  
|<span data-ttu-id="50976-107">0</span><span class="sxs-lookup"><span data-stu-id="50976-107">0</span></span>|<span data-ttu-id="50976-108">默认值。</span><span class="sxs-lookup"><span data-stu-id="50976-108">Default value.</span></span> <span data-ttu-id="50976-109">规则引擎遵循 BizTalk Server 2004 模型中，仅当断言.NET 类的实例时，调用静态方法。</span><span class="sxs-lookup"><span data-stu-id="50976-109">The rule engine follows the BizTalk Server 2004 model, where the static method is called only when an instance of the .NET class is asserted.</span></span>|  
|<span data-ttu-id="50976-110">1</span><span class="sxs-lookup"><span data-stu-id="50976-110">1</span></span>|<span data-ttu-id="50976-111">对象实例不是必需的。</span><span class="sxs-lookup"><span data-stu-id="50976-111">An object instance is not required.</span></span> <span data-ttu-id="50976-112">计算或执行规则时，被调用静态方法。</span><span class="sxs-lookup"><span data-stu-id="50976-112">The static method is called when the rule is evaluated or executed.</span></span>|  
|<span data-ttu-id="50976-113">2</span><span class="sxs-lookup"><span data-stu-id="50976-113">2</span></span>|<span data-ttu-id="50976-114">对象实例不是必需的。</span><span class="sxs-lookup"><span data-stu-id="50976-114">An object instance is not required.</span></span> <span data-ttu-id="50976-115">如果所有参数都是常量，将在策略转换时调用静态方法。</span><span class="sxs-lookup"><span data-stu-id="50976-115">The static method is called at the policy translation time if all parameters are constant.</span></span> <span data-ttu-id="50976-116">这是一种性能优化，因为即使在条件中的多个规则中使用一次调用静态方法。</span><span class="sxs-lookup"><span data-stu-id="50976-116">This is a performance optimization because the static method is called only once even though it is used in multiple rules in conditions.</span></span> <span data-ttu-id="50976-117">请注意，用作操作的静态方法将不会执行转换时，但可能会执行用作参数的静态方法。</span><span class="sxs-lookup"><span data-stu-id="50976-117">Note that static methods used as actions will not be executed at the translation time, but static methods used as parameters may be executed.</span></span>|  
  
## <a name="adding-and-changing-the-staticsupport-registry-key"></a><span data-ttu-id="50976-118">添加和更改 StaticSupport 注册表项</span><span class="sxs-lookup"><span data-stu-id="50976-118">Adding and Changing the StaticSupport Registry Key</span></span>  
 <span data-ttu-id="50976-119">如果没有看到**StaticSupport**注册表项下的**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**，应将其添加，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="50976-119">If you do not see the **StaticSupport** registry key under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**, you should add it by performing the following steps.</span></span>  
  
 <span data-ttu-id="50976-120">**若要添加 StaticSupport 注册表项**</span><span class="sxs-lookup"><span data-stu-id="50976-120">**To add the StaticSupport registry key**</span></span>  
  
1. <span data-ttu-id="50976-121">单击**启动**，单击**运行**，类型**RegEdit**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="50976-121">Click **Start**, click **Run**, type **RegEdit**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="50976-122">展开**HKEY_LOCAL_MACHINE**，展开**软件**，展开**Microsoft**，展开**BusinessRules**，然后选择**3.0**。</span><span class="sxs-lookup"><span data-stu-id="50976-122">Expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Microsoft**, expand **BusinessRules**, and then select **3.0**.</span></span>  
  
3. <span data-ttu-id="50976-123">在右窗格中，右键单击，指向**新建**，然后单击**DWORD 值**。</span><span class="sxs-lookup"><span data-stu-id="50976-123">In the right pane, right-click, point to **New**, and then click **DWORD value**.</span></span>  
  
4. <span data-ttu-id="50976-124">有关**名称**，类型**StaticSupport**。</span><span class="sxs-lookup"><span data-stu-id="50976-124">For **Name**, type **StaticSupport**.</span></span>  
  
   <span data-ttu-id="50976-125">如果**StaticSupport**注册表项已存在，并且你需要将其值更改，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="50976-125">If the **StaticSupport** registry key already exists, and you need to change its value, perform the following steps.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="50976-126">如果 BizTalk 安装在 64 位计算机上，则可以添加**StaticSupport**注册表项，使用以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="50976-126">If BizTalk is installed on a 64-bit machine, then you can add **StaticSupport** registry key using either of the following options:</span></span>  
> 
> - <span data-ttu-id="50976-127">您需要在 HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0 下查找。</span><span class="sxs-lookup"><span data-stu-id="50976-127">You need to look under HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0.</span></span> <span data-ttu-id="50976-128">如果此项存在，则可以添加**StaticSupport**此处。</span><span class="sxs-lookup"><span data-stu-id="50976-128">If this key exists, then you can add **StaticSupport** here.</span></span>  
>   -   <span data-ttu-id="50976-129">另一个选项是将**StaticSupport**中**BTNTsvc [64].exe.config**文件，因为此处的任何设置将覆盖在注册表中。</span><span class="sxs-lookup"><span data-stu-id="50976-129">Another option is to put **StaticSupport** in the **BTNTsvc[64].exe.config** file, as any settings here override what's in the Registry.</span></span>  <span data-ttu-id="50976-130">此外，一个还可以使自变量，此选项是首选因为隔离行为中的更改默认到 BizTalk，而注册表设置是全局性的操作系统。</span><span class="sxs-lookup"><span data-stu-id="50976-130">Further, one can also make the argument that this option is preferred since it isolates the change in default behavior to BizTalk only, whereas Registry settings are global to the Operating System.</span></span>  
  
 <span data-ttu-id="50976-131">**若要更改 StaticSupport 注册表项的值**</span><span class="sxs-lookup"><span data-stu-id="50976-131">**To change the value of the StaticSupport registry key**</span></span>  
  
1.  <span data-ttu-id="50976-132">单击**启动**，单击**运行**，类型**RegEdit**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="50976-132">Click **Start**, click **Run**, type **RegEdit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="50976-133">展开**HKEY_LOCAL_MACHINE**，展开**软件**，展开**Microsoft**，展开**BusinessRules**，然后展开**3.0**。</span><span class="sxs-lookup"><span data-stu-id="50976-133">Expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Microsoft**, expand **BusinessRules**, and then expand **3.0**.</span></span>  
  
3.  <span data-ttu-id="50976-134">双击**StaticSupport**注册表键，或者右键单击它，然后单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="50976-134">Double-click the **StaticSupport** registry key, or right-click it and then click **Modify**.</span></span>