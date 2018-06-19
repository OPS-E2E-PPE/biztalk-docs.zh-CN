---
title: 调用类的静态成员 |Microsoft 文档
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
ms.openlocfilehash: 2128bf6cb71c773cd31be497765e39b0d7815b4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262269"
---
# <a name="invoking-static-members-of-a-class"></a><span data-ttu-id="59274-102">调用类的静态成员</span><span class="sxs-lookup"><span data-stu-id="59274-102">Invoking Static Members of a Class</span></span>
<span data-ttu-id="59274-103">默认情况下，规则引擎要求你断言 .NET 类的一个实例来执行一项策略，该策略可调用 .NET 类的静态成员。</span><span class="sxs-lookup"><span data-stu-id="59274-103">By default, the rule engine requires you to assert an instance of a .NET class to execute a policy that invokes a static member of the .NET class.</span></span> <span data-ttu-id="59274-104">您可以通过更改的值来修改此行为**StaticSupport**下的注册表项**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**为下表中的值之一。</span><span class="sxs-lookup"><span data-stu-id="59274-104">You can modify this behavior by changing the value of the **StaticSupport** registry key under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0** to one of the values in the following table.</span></span>  
  
|<span data-ttu-id="59274-105">StaticSupport 注册表值</span><span class="sxs-lookup"><span data-stu-id="59274-105">StaticSupport registry value</span></span>|<span data-ttu-id="59274-106">规则引擎行为</span><span class="sxs-lookup"><span data-stu-id="59274-106">Rule engine behavior</span></span>|  
|----------------------------------|--------------------------|  
|<span data-ttu-id="59274-107">0</span><span class="sxs-lookup"><span data-stu-id="59274-107">0</span></span>|<span data-ttu-id="59274-108">默认值。</span><span class="sxs-lookup"><span data-stu-id="59274-108">Default value.</span></span> <span data-ttu-id="59274-109">规则引擎遵循 BizTalk Server 2004 模型，在该模型中，只有断言 .NET 类的某个实例后才能调用静态方法。</span><span class="sxs-lookup"><span data-stu-id="59274-109">The rule engine follows the BizTalk Server 2004 model, where the static method is called only when an instance of the .NET class is asserted.</span></span>|  
|<span data-ttu-id="59274-110">1</span><span class="sxs-lookup"><span data-stu-id="59274-110">1</span></span>|<span data-ttu-id="59274-111">对象实例不是必需的。</span><span class="sxs-lookup"><span data-stu-id="59274-111">An object instance is not required.</span></span> <span data-ttu-id="59274-112">将在评估或执行规则时调用静态方法。</span><span class="sxs-lookup"><span data-stu-id="59274-112">The static method is called when the rule is evaluated or executed.</span></span>|  
|<span data-ttu-id="59274-113">2</span><span class="sxs-lookup"><span data-stu-id="59274-113">2</span></span>|<span data-ttu-id="59274-114">对象实例不是必需的。</span><span class="sxs-lookup"><span data-stu-id="59274-114">An object instance is not required.</span></span> <span data-ttu-id="59274-115">如果所有参数都是常数，则将在策略转换时调用静态方法。</span><span class="sxs-lookup"><span data-stu-id="59274-115">The static method is called at the policy translation time if all parameters are constant.</span></span> <span data-ttu-id="59274-116">这是一种性能优化，因为尽管静态方法在条件中的多个规则中使用，但只会调用一次。</span><span class="sxs-lookup"><span data-stu-id="59274-116">This is a performance optimization because the static method is called only once even though it is used in multiple rules in conditions.</span></span> <span data-ttu-id="59274-117">请注意，用作操作的静态方法将不能在转换时执行，不过用作参数的静态方法可以在转换时执行。</span><span class="sxs-lookup"><span data-stu-id="59274-117">Note that static methods used as actions will not be executed at the translation time, but static methods used as parameters may be executed.</span></span>|  
  
## <a name="adding-and-changing-the-staticsupport-registry-key"></a><span data-ttu-id="59274-118">添加和更改 StaticSupport 注册表项</span><span class="sxs-lookup"><span data-stu-id="59274-118">Adding and Changing the StaticSupport Registry Key</span></span>  
 <span data-ttu-id="59274-119">如果看不到**StaticSupport**下的注册表项**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**，应将其添加通过执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="59274-119">If you do not see the **StaticSupport** registry key under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**, you should add it by performing the following steps.</span></span>  
  
 <span data-ttu-id="59274-120">**若要添加 StaticSupport 注册表项**</span><span class="sxs-lookup"><span data-stu-id="59274-120">**To add the StaticSupport registry key**</span></span>  
  
1.  <span data-ttu-id="59274-121">单击**启动**，单击**运行**，类型**RegEdit**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="59274-121">Click **Start**, click **Run**, type **RegEdit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="59274-122">展开**HKEY_LOCAL_MACHINE**，展开**软件**，展开**Microsoft**，展开**业务规则**，然后选择**3.0**。</span><span class="sxs-lookup"><span data-stu-id="59274-122">Expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Microsoft**, expand **BusinessRules**, and then select **3.0**.</span></span>  
  
3.  <span data-ttu-id="59274-123">在右窗格中，右键单击，指向**新建**，然后单击**DWORD 值**。</span><span class="sxs-lookup"><span data-stu-id="59274-123">In the right pane, right-click, point to **New**, and then click **DWORD value**.</span></span>  
  
4.  <span data-ttu-id="59274-124">有关**名称**，类型**StaticSupport**。</span><span class="sxs-lookup"><span data-stu-id="59274-124">For **Name**, type **StaticSupport**.</span></span>  
  
 <span data-ttu-id="59274-125">如果**StaticSupport**注册表项已存在，并且你需要更改它的值，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="59274-125">If the **StaticSupport** registry key already exists, and you need to change its value, perform the following steps.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="59274-126">如果 BizTalk 安装在 64 位计算机上，则可以添加**StaticSupport**注册表项使用以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="59274-126">If BizTalk is installed on a 64-bit machine, then you can add **StaticSupport** registry key using either of the following options:</span></span>  
>   
>  -   <span data-ttu-id="59274-127">你需要在 HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0 下查找。</span><span class="sxs-lookup"><span data-stu-id="59274-127">You need to look under HKLM\Software\Wow6432Node\Microsoft\BusinessRules\3.0.</span></span> <span data-ttu-id="59274-128">如果此项存在，则可以添加**StaticSupport**此处。</span><span class="sxs-lookup"><span data-stu-id="59274-128">If this key exists, then you can add **StaticSupport** here.</span></span>  
> -   <span data-ttu-id="59274-129">另一种方法是将**StaticSupport**中**BTNTsvc [64].exe.config**文件，如下所此处的任何设置覆盖什么是在注册表中。</span><span class="sxs-lookup"><span data-stu-id="59274-129">Another option is to put **StaticSupport** in the **BTNTsvc[64].exe.config** file, as any settings here override what's in the Registry.</span></span>  <span data-ttu-id="59274-130">此外还可以得出的结论就是，此选项是一个首选选项，因为它会将默认行为中的更改仅隔离到 BizTalk，而注册表设置是针对操作系统的全局设置。</span><span class="sxs-lookup"><span data-stu-id="59274-130">Further, one can also make the argument that this option is preferred since it isolates the change in default behavior to BizTalk only, whereas Registry settings are global to the Operating System.</span></span>  
  
 <span data-ttu-id="59274-131">**若要更改 StaticSupport 注册表项的值**</span><span class="sxs-lookup"><span data-stu-id="59274-131">**To change the value of the StaticSupport registry key**</span></span>  
  
1.  <span data-ttu-id="59274-132">单击**启动**，单击**运行**，类型**RegEdit**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="59274-132">Click **Start**, click **Run**, type **RegEdit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="59274-133">展开**HKEY_LOCAL_MACHINE**，展开**软件**，展开**Microsoft**，展开**业务规则**，然后展开**3.0**。</span><span class="sxs-lookup"><span data-stu-id="59274-133">Expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Microsoft**, expand **BusinessRules**, and then expand **3.0**.</span></span>  
  
3.  <span data-ttu-id="59274-134">双击**StaticSupport**注册表项，或右键单击它，然后单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="59274-134">Double-click the **StaticSupport** registry key, or right-click it and then click **Modify**.</span></span>