---
title: 配置信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], planning
- Call Rules shape [Orchestration Designer], configuring
ms.assetid: aa4924c6-4270-473b-aa0a-6d8b18375a39
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9d58c810f4c0a01046d900f8654556f523f7a27
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356488"
---
# <a name="configuration-information"></a><span data-ttu-id="50901-102">配置信息</span><span class="sxs-lookup"><span data-stu-id="50901-102">Configuration Information</span></span>
<span data-ttu-id="50901-103">本主题介绍如何配置**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="50901-103">This topic describes how to configure the **Call Rules** shape.</span></span>  
  
## <a name="orchestration-variables-and-fact-types"></a><span data-ttu-id="50901-104">业务流程变量和事实类型</span><span class="sxs-lookup"><span data-stu-id="50901-104">Orchestration variables and fact types</span></span>  
 <span data-ttu-id="50901-105">在业务流程中位置**调用规则**驻留形状中，你必须具有匹配策略中使用的类型的变量。</span><span class="sxs-lookup"><span data-stu-id="50901-105">In the orchestration where the **Call Rules** shape resides, you must have variables that match types used in the policy.</span></span> <span data-ttu-id="50901-106">如果没有正确的变量类型，不能提供该策略的正确参数。</span><span class="sxs-lookup"><span data-stu-id="50901-106">If you do not have the correct types of variables, you cannot supply the correct parameters to the policy.</span></span> <span data-ttu-id="50901-107">假设您有**调用规则**形状在业务流程、 CallMyRules，并且您使用 CallMyRules 调用 MyPolicy。</span><span class="sxs-lookup"><span data-stu-id="50901-107">Suppose that you have a **Call Rules** shape in an orchestration, CallMyRules, and you use CallMyRules to call MyPolicy.</span></span> <span data-ttu-id="50901-108">如果在 MyPolicy 中使用.NET 类 MyClass，则必须在业务流程中创建 MyAssembly.MyClass 类型的变量。</span><span class="sxs-lookup"><span data-stu-id="50901-108">If a .NET class, MyClass, is used in MyPolicy, you must create a variable of a MyAssembly.MyClass type in the orchestration.</span></span> <span data-ttu-id="50901-109">同样，如果具有**DataConnection**绑定，必须创建的变量**Microsoft.RuleEngine.DataConnection**业务流程中的类型。</span><span class="sxs-lookup"><span data-stu-id="50901-109">Similarly, if MyPolicy has **DataConnection** bindings, you must create a variable of a **Microsoft.RuleEngine.DataConnection** type in the orchestration.</span></span>  
  
 <span data-ttu-id="50901-110">除了在业务流程中创建此类变量，还必须创建这些变量的实例。</span><span class="sxs-lookup"><span data-stu-id="50901-110">In addition to creating the variables in the orchestration, you must also create instances for these variables.</span></span> <span data-ttu-id="50901-111">您可以执行此操作通过添加**表达式**向业务流程的形状。</span><span class="sxs-lookup"><span data-stu-id="50901-111">You can do this by adding an **Expression** shape to your orchestration.</span></span> <span data-ttu-id="50901-112">使用前面的示例中，您应实例化 MyAssembly.MyClass 实例和一个**DataConnection**实例。</span><span class="sxs-lookup"><span data-stu-id="50901-112">Using the preceding example, you should instantiate a MyAssembly.MyClass instance and a **DataConnection** instance.</span></span> <span data-ttu-id="50901-113">若要实例化**DataConnection**实例，则执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="50901-113">To instantiate the **DataConnection** instance, you do the following:</span></span>  
  
-   <span data-ttu-id="50901-114">创建**SqlConnection**实例，并将其分配给 MySqlCon。</span><span class="sxs-lookup"><span data-stu-id="50901-114">Create a **SqlConnection** instance and assign it to MySqlCon.</span></span>  
  
-   <span data-ttu-id="50901-115">创建**DataConnection**实例，并将其分配给 dataConnection (变量**DataConnection**类型)，如以下代码片段中所示：</span><span class="sxs-lookup"><span data-stu-id="50901-115">Create a **DataConnection** instance and assign it to dataConnection (variable of **DataConnection** type), as shown in the following code fragment:</span></span>  
  
    ```  
    dataConnection = new Microsoft.RuleEngine.DataConnection("NameOfSqlDatabaseHere", "NameOfYourTableHere", MySqlCon);  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="50901-116">如果没有匹配的事实类型的变量，这些类型将不会显示作为中的参数**指定策略参数**列表框中的**CallRules 策略配置**对话框。</span><span class="sxs-lookup"><span data-stu-id="50901-116">If you do not have variables matching the fact types, these types will not appear as parameters in the **Specify policy parameters** list box in the **CallRules policy configuration** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50901-117">业务流程引擎会自动将转换为到 BRE 策略的参数指定的消息变量**TypedXmlDocument**对象，并将它们添加到工作内存中的规则引擎在执行该策略之前。</span><span class="sxs-lookup"><span data-stu-id="50901-117">The orchestration engine automatically converts the message variables you specify as parameters to a BRE policy into **TypedXmlDocument** objects, and asserts them into working memory of the rule engine prior to executing the policy.</span></span> <span data-ttu-id="50901-118">因此，不需要声明 TypedXmlDocument 类型的变量，如你对.NET 和数据库事实。</span><span class="sxs-lookup"><span data-stu-id="50901-118">Therefore, you do not need to declare variables of type TypedXmlDocument as you did for .NET and database facts.</span></span>  
  
## <a name="message-type-and-document-type"></a><span data-ttu-id="50901-119">消息类型和文档类型</span><span class="sxs-lookup"><span data-stu-id="50901-119">Message type and document type</span></span>  
 <span data-ttu-id="50901-120">您必须确保**DocumentType** （即在业务规则编辑器中实现时） 在业务规则中使用的 XML 节点的属性是与相同**MessageType**中定义的 XML 节点业务流程，则它必须匹配**MessageType**的消息或将其传递到规则引擎的消息部分**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="50901-120">You must ensure that the **DocumentType** property for XML nodes used in your business rule (that you implement in the Business Rule Composer) is the same as the **MessageType** for those XML nodes defined in the orchestration—it must match the **MessageType** of the message or message part that will be passed to the rule engine in the **Call Rules** shape.</span></span>  
  
 <span data-ttu-id="50901-121">例如，如果在 BizTalk 项目中，定义采购订单 (PO) XML 架构**MessageType**为此架构定义**BTSProject.PO** (如果**BTSProject**是命名空间或使用默认命名空间的项目名称）。</span><span class="sxs-lookup"><span data-stu-id="50901-121">For example, if you define a purchase order (PO) XML schema in a BizTalk project, the **MessageType** defined for this schema is **BTSProject.PO** (if **BTSProject** is the namespace or the project name using the default namespace).</span></span>  
  
 <span data-ttu-id="50901-122">情况下**PO\Amount**元素，才能删除为规则的定义，则必须更改其**DocumentType**属性设置为**BTSProject.PO**属性窗口中.</span><span class="sxs-lookup"><span data-stu-id="50901-122">In the case of the **PO\Amount** element, before you drop it into a rule definition, you must change its **DocumentType**property to **BTSProject.PO** in the properties window.</span></span> <span data-ttu-id="50901-123">在选择架构中的任何节点后，可以访问属性窗口**XML 架构**在事实浏览器选项卡。</span><span class="sxs-lookup"><span data-stu-id="50901-123">You can access the properties window when any node in the schema is selected on the **XML Schemas** tab in the Facts Explorer.</span></span> <span data-ttu-id="50901-124">此更改将应用于的所有元素在架构中，但不是保留与架构。</span><span class="sxs-lookup"><span data-stu-id="50901-124">This change is applied for all elements in the schema, but is not persisted with the schema.</span></span> <span data-ttu-id="50901-125">业务规则编辑器启动或重新加载架构时，它必须重置。</span><span class="sxs-lookup"><span data-stu-id="50901-125">It must be reset when the Business Rule Composer is launched or the schema is reloaded.</span></span> <span data-ttu-id="50901-126">这是必需的基于 XML 架构或直接从 XML 架构生成的规则的词汇定义。</span><span class="sxs-lookup"><span data-stu-id="50901-126">This is required for vocabulary definitions based either on XML schemas or on rules built directly from XML schemas.</span></span> <span data-ttu-id="50901-127">如果不这样做，则仍可以执行策略，但**调用规则**形状将无法正常工作，并且消息类型将出现在**指定策略参数**列表框中的**CallRules 策略配置**对话框。</span><span class="sxs-lookup"><span data-stu-id="50901-127">If you do not do this, you can still execute the policy, but the **Call Rules** shape will not work correctly, and message type will not appear in the **Specify policy parameters** list box in the **CallRules policy configuration** dialog box.</span></span>