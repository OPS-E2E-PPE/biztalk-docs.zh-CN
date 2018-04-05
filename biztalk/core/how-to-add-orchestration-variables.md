---
title: 如何添加业务流程变量 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: c387cd56-5443-4de2-bbda-be34b95cbe71
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb8516ceb780e64c4f4a01370de0e7c40098f3da
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-add-orchestration-variables"></a><span data-ttu-id="95547-102">如何添加业务流程变量</span><span class="sxs-lookup"><span data-stu-id="95547-102">How to Add Orchestration Variables</span></span>
<span data-ttu-id="95547-103">业务流程视图窗口可以管理业务流程的属性 (也称为**服务**属性)，参数、 端口、 消息以及其他变量。</span><span class="sxs-lookup"><span data-stu-id="95547-103">The Orchestration View window enables you to manage an orchestration's properties (also known as **Service** properties), parameters, ports, messages, and other variables.</span></span> <span data-ttu-id="95547-104">除了端口和消息，您还可以创建整数变量、布尔型变量、字符串变量或 .NET 类的变量。</span><span class="sxs-lookup"><span data-stu-id="95547-104">In addition to ports and messages, you can create integer variables, Boolean variables, string variables, or variables of a .NET class.</span></span>  
  
 <span data-ttu-id="95547-105">还可以使用“业务流程视图”窗口管理属于您的范围的变量。</span><span class="sxs-lookup"><span data-stu-id="95547-105">You can also use the Orchestration View window to manage the variables that belong to your scopes.</span></span>  
  
### <a name="to-add-a-variable"></a><span data-ttu-id="95547-106">添加变量</span><span class="sxs-lookup"><span data-stu-id="95547-106">To add a variable</span></span>  
  
1.  <span data-ttu-id="95547-107">在业务流程视图窗口中，右键单击**变量**文件夹，然后单击**新变量**。</span><span class="sxs-lookup"><span data-stu-id="95547-107">In the Orchestration View window, right-click the **Variables** folder and then click **New Variable**.</span></span>  
  
     <span data-ttu-id="95547-108">**变量**文件夹扩展，如果折叠状态，并添加一个新的变量。</span><span class="sxs-lookup"><span data-stu-id="95547-108">The **Variables** folder expands, if collapsed, and a new variable is added.</span></span>  
  
2.  <span data-ttu-id="95547-109">在“属性”窗口中，在“标识符”属性中键入名称，为该变量命名。</span><span class="sxs-lookup"><span data-stu-id="95547-109">Name the variable by typing a name in the Identifier property in the Properties window.</span></span>  
  
3.  <span data-ttu-id="95547-110">将该变量与一个类型相关联，如 .NET 类。</span><span class="sxs-lookup"><span data-stu-id="95547-110">Associate the variable with a type, such as a .NET class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95547-111">**类型**下拉列表包含下列预定义的变量类型：**布尔**，**字节**， **datetime**， **十进制**， **double**， **int16**， **int32**， **int64**， **sbyte****单个**，**字符串**， **timespan**， **uint16**， **uint32**，和**uint64**。</span><span class="sxs-lookup"><span data-stu-id="95547-111">The **Types** drop-down list contains the following predefined variable types: **boolean**, **byte**, **datetime**, **decimal**, **double**, **int16**, **int32**, **int64**, **sbyte**, **single**, **string**, **timespan**, **uint16**, **uint32**, and **uint64**.</span></span> <span data-ttu-id="95547-112">你还可以通过选择访问.NET 数据类型和类 **\<.NET 类...\>** ，它可提供**选择项目类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="95547-112">You can also access .NET data types and classes by selecting **\<.NET Class...\>**, which brings up the **Select Artifact Type** dialog box.</span></span>  
  
4.  <span data-ttu-id="95547-113">如果选择预定义变量类型，则可以选择指定该变量的初始值。</span><span class="sxs-lookup"><span data-stu-id="95547-113">If you select a predefined variable type, you have the option of specifying an initial value for the variable.</span></span> <span data-ttu-id="95547-114">在属性窗口中，设置**初始值**属性。</span><span class="sxs-lookup"><span data-stu-id="95547-114">In the Properties window, set the **Initial Value** property.</span></span>  
  
     <span data-ttu-id="95547-115">否则，如果所选类型为 .NET 类，可以选择使用默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="95547-115">Otherwise, if the selected type is a .NET class, you have the option of using a default constructor.</span></span> <span data-ttu-id="95547-116">在“属性”窗口中，设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="95547-116">In the Properties window, set the following property:</span></span>  
  
    |<span data-ttu-id="95547-117">属性</span><span class="sxs-lookup"><span data-stu-id="95547-117">Property</span></span>|<span data-ttu-id="95547-118">Description</span><span class="sxs-lookup"><span data-stu-id="95547-118">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="95547-119">**使用默认构造函数**</span><span class="sxs-lookup"><span data-stu-id="95547-119">**Use Default Constructor**</span></span>|<span data-ttu-id="95547-120">如果默认构造函数可用于 .NET 类，此属性将确定默认构造函数是否将在您初次使用该变量时被调用：</span><span class="sxs-lookup"><span data-stu-id="95547-120">If a default constructor is available for a .NET class, this property determines whether the default constructor will be called when you use the variable for the first time:</span></span><br /><br /> <span data-ttu-id="95547-121">True — 将调用默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="95547-121">True—The default constructor will be called.</span></span> <span data-ttu-id="95547-122">当默认构造函数可用时，这是默认值。</span><span class="sxs-lookup"><span data-stu-id="95547-122">This is the default value when a default constructor is available.</span></span><br /><br /> <span data-ttu-id="95547-123">False — 不会调用默认构造函数；您必须首先在表达式中调用某一构造函数或向变量赋值，然后才可以在您的业务流程中使用它。</span><span class="sxs-lookup"><span data-stu-id="95547-123">False—The default constructor will not be called; you must call a constructor in an expression or make an assignment to the variable before you can use it in your orchestration.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="95547-124">如果默认构造函数需要输入的参数，则可以设置**使用默认构造函数**到**False** ，然后调用的构造函数从**分配**调整; 为示例中， `myVariable = myNamespace.myClass (param1, param2)`。</span><span class="sxs-lookup"><span data-stu-id="95547-124">If the default constructor requires input parameters, you can set **Use Default Constructor** to **False** and then call the constructor from an **Assignment** shape; for example, `myVariable = myNamespace.myClass (param1, param2)`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95547-125">向业务流程添加变量时，在完全定义变量之前，您将在业务流程中看到叹号。</span><span class="sxs-lookup"><span data-stu-id="95547-125">When you add a variable to the orchestration, before it is fully defined, you will see exclamation marks in the orchestration.</span></span> <span data-ttu-id="95547-126">如果在完全定义变量之前删除该变量并且叹号仍然显示在业务流程中，您可以通过创建业务流程参数，然后再删除该参数，强制业务流程删除这些叹号。</span><span class="sxs-lookup"><span data-stu-id="95547-126">If you delete this variable before it is fully defined and the exclamation marks still appear in the orchestration, you can force the orchestration to remove these exclamation marks by creating and then deleting an orchestration parameter.</span></span>  
  
### <a name="to-remove-a-variable"></a><span data-ttu-id="95547-127">若要删除变量</span><span class="sxs-lookup"><span data-stu-id="95547-127">To remove a variable</span></span>  
  
-   <span data-ttu-id="95547-128">在业务流程视图窗口中，右键单击你想要删除，然后单击的变量**删除**。</span><span class="sxs-lookup"><span data-stu-id="95547-128">In the Orchestration View window, right-click the variable you want to remove and then click **Delete**.</span></span>