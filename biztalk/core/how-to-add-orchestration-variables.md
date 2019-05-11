---
title: 如何添加业务流程变量 |Microsoft Docs
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
ms.openlocfilehash: 876799a7baf58d7dacc8185d09d6f9d63a70127d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343255"
---
# <a name="how-to-add-orchestration-variables"></a><span data-ttu-id="1b24a-102">如何添加业务流程变量</span><span class="sxs-lookup"><span data-stu-id="1b24a-102">How to Add Orchestration Variables</span></span>
<span data-ttu-id="1b24a-103">业务流程视图窗口可以管理业务流程的属性 (也称为**服务**属性)，参数、 端口、 消息和其他变量。</span><span class="sxs-lookup"><span data-stu-id="1b24a-103">The Orchestration View window enables you to manage an orchestration's properties (also known as **Service** properties), parameters, ports, messages, and other variables.</span></span> <span data-ttu-id="1b24a-104">除了端口和消息，可以创建整数变量、 布尔变量、 字符串变量或.NET 类的变量。</span><span class="sxs-lookup"><span data-stu-id="1b24a-104">In addition to ports and messages, you can create integer variables, Boolean variables, string variables, or variables of a .NET class.</span></span>  
  
 <span data-ttu-id="1b24a-105">业务流程视图窗口还可用于管理属于你作用域的变量。</span><span class="sxs-lookup"><span data-stu-id="1b24a-105">You can also use the Orchestration View window to manage the variables that belong to your scopes.</span></span>  
  
### <a name="to-add-a-variable"></a><span data-ttu-id="1b24a-106">添加变量</span><span class="sxs-lookup"><span data-stu-id="1b24a-106">To add a variable</span></span>  
  
1.  <span data-ttu-id="1b24a-107">在业务流程视图窗口中，右键单击**变量**文件夹，然后单击**新变量**。</span><span class="sxs-lookup"><span data-stu-id="1b24a-107">In the Orchestration View window, right-click the **Variables** folder and then click **New Variable**.</span></span>  
  
     <span data-ttu-id="1b24a-108">**变量**文件夹会展开，如果处于折叠状态，并将其添加一个新的变量。</span><span class="sxs-lookup"><span data-stu-id="1b24a-108">The **Variables** folder expands, if collapsed, and a new variable is added.</span></span>  
  
2.  <span data-ttu-id="1b24a-109">通过在属性窗口中的标识符属性中键入一个名称命名该变量。</span><span class="sxs-lookup"><span data-stu-id="1b24a-109">Name the variable by typing a name in the Identifier property in the Properties window.</span></span>  
  
3.  <span data-ttu-id="1b24a-110">将该变量与一个类型，如.NET 类相关联。</span><span class="sxs-lookup"><span data-stu-id="1b24a-110">Associate the variable with a type, such as a .NET class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b24a-111">**类型**下拉列表包含以下预定义的变量类型：**布尔**，**字节**， **datetime**， **十进制**，**双**， **int16**， **int32**， **int64**， **sbyte\*\*\*\*单个**，**字符串**， **timespan**， **uint16**， **uint32**，和**uint64**。</span><span class="sxs-lookup"><span data-stu-id="1b24a-111">The **Types** drop-down list contains the following predefined variable types: **boolean**, **byte**, **datetime**, **decimal**, **double**, **int16**, **int32**, **int64**, **sbyte**, **single**, **string**, **timespan**, **uint16**, **uint32**, and **uint64**.</span></span> <span data-ttu-id="1b24a-112">您还可以通过选择访问.NET 数据类型和类**\<.NET 类...\>**，这会打开**选择项目类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="1b24a-112">You can also access .NET data types and classes by selecting **\<.NET Class...\>**, which brings up the **Select Artifact Type** dialog box.</span></span>  
  
4.  <span data-ttu-id="1b24a-113">如果选择预定义的变量类型，您可以指定该变量的初始值。</span><span class="sxs-lookup"><span data-stu-id="1b24a-113">If you select a predefined variable type, you have the option of specifying an initial value for the variable.</span></span> <span data-ttu-id="1b24a-114">在属性窗口中设置**初始值**属性。</span><span class="sxs-lookup"><span data-stu-id="1b24a-114">In the Properties window, set the **Initial Value** property.</span></span>  
  
     <span data-ttu-id="1b24a-115">否则，如果所选的类型是一个.NET 类，必须使用默认构造函数的选项。</span><span class="sxs-lookup"><span data-stu-id="1b24a-115">Otherwise, if the selected type is a .NET class, you have the option of using a default constructor.</span></span> <span data-ttu-id="1b24a-116">在属性窗口中，设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="1b24a-116">In the Properties window, set the following property:</span></span>  
  
    |<span data-ttu-id="1b24a-117">属性</span><span class="sxs-lookup"><span data-stu-id="1b24a-117">Property</span></span>|<span data-ttu-id="1b24a-118">Description</span><span class="sxs-lookup"><span data-stu-id="1b24a-118">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="1b24a-119">**使用默认构造函数**</span><span class="sxs-lookup"><span data-stu-id="1b24a-119">**Use Default Constructor**</span></span>|<span data-ttu-id="1b24a-120">如果默认构造函数可用于.NET 类，此属性确定当首次使用该变量时，是否将调用默认构造函数：</span><span class="sxs-lookup"><span data-stu-id="1b24a-120">If a default constructor is available for a .NET class, this property determines whether the default constructor will be called when you use the variable for the first time:</span></span><br /><br /> <span data-ttu-id="1b24a-121">True — 将调用默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="1b24a-121">True—The default constructor will be called.</span></span> <span data-ttu-id="1b24a-122">默认构造函数可用时，这是默认值。</span><span class="sxs-lookup"><span data-stu-id="1b24a-122">This is the default value when a default constructor is available.</span></span><br /><br /> <span data-ttu-id="1b24a-123">False — 不会调用默认构造函数;必须在表达式中调用构造函数或之前您可以在业务流程中使用它进行变量赋值。</span><span class="sxs-lookup"><span data-stu-id="1b24a-123">False—The default constructor will not be called; you must call a constructor in an expression or make an assignment to the variable before you can use it in your orchestration.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="1b24a-124">如果默认构造函数要求输入的参数，则可以设置**使用默认构造函数**到**False** ，然后调用从构造函数**分配**形状; 为示例中， `myVariable = myNamespace.myClass (param1, param2)`。</span><span class="sxs-lookup"><span data-stu-id="1b24a-124">If the default constructor requires input parameters, you can set **Use Default Constructor** to **False** and then call the constructor from an **Assignment** shape; for example, `myVariable = myNamespace.myClass (param1, param2)`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b24a-125">当将变量添加到业务流程中，完全定义之前时，你将看到在业务流程中的感叹号。</span><span class="sxs-lookup"><span data-stu-id="1b24a-125">When you add a variable to the orchestration, before it is fully defined, you will see exclamation marks in the orchestration.</span></span> <span data-ttu-id="1b24a-126">如果之前已完全定义和叹号仍然显示在业务流程中删除该变量，则可以强制业务流程，以通过创建并随后将删除将业务流程参数中删除这些叹号。</span><span class="sxs-lookup"><span data-stu-id="1b24a-126">If you delete this variable before it is fully defined and the exclamation marks still appear in the orchestration, you can force the orchestration to remove these exclamation marks by creating and then deleting an orchestration parameter.</span></span>  
  
### <a name="to-remove-a-variable"></a><span data-ttu-id="1b24a-127">若要删除变量</span><span class="sxs-lookup"><span data-stu-id="1b24a-127">To remove a variable</span></span>  
  
-   <span data-ttu-id="1b24a-128">在业务流程视图窗口中，右键单击你想要删除，然后单击的变量**删除**。</span><span class="sxs-lookup"><span data-stu-id="1b24a-128">In the Orchestration View window, right-click the variable you want to remove and then click **Delete**.</span></span>