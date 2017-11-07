---
title: "导入 Visual Studio 博士 Edwards EnterpriseOne 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 640d5884-953a-46b6-b9dc-b931392a3059
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acd61cc8ab63d6859a8e10afb76f93c2f8cb2150
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="importing-schemas-into-biztalk-server-projects"></a><span data-ttu-id="e9bed-102">将架构导入到 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="e9bed-102">Importing Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="e9bed-103">本部分讨论浏览 JD Edwards EnterpriseOne 服务器和将架构导入 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目中。</span><span class="sxs-lookup"><span data-stu-id="e9bed-103">This section discusses browsing a JD Edwards EnterpriseOne server and importing the schemas into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9bed-104">您必须确保已设置 arglist。</span><span class="sxs-lookup"><span data-stu-id="e9bed-104">You must ensure that you set the arglist.</span></span> <span data-ttu-id="e9bed-105">在业务流程中生成架构之前，您必须更新 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="e9bed-105">You must update jdearglist.txt before you generate the schemas in the orchestration.</span></span> <span data-ttu-id="e9bed-106">有关详细信息，请参阅[处理字符串值](../core/handling-string-values2.md)。</span><span class="sxs-lookup"><span data-stu-id="e9bed-106">For more information, see [Handling String Values](../core/handling-string-values2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9bed-107">每次更改 jdearglist 时，都必须为该业务对象重新生成架构。</span><span class="sxs-lookup"><span data-stu-id="e9bed-107">Each time that you change the jdearglist, you must regenerate the schemas for that business object.</span></span>  
  
 <span data-ttu-id="e9bed-108">在创建 JD Edwards EnterpriseOne 端口后，可以通过从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目中启动 Microsoft 适配器向导来浏览 JD Edwards EnterpriseOne。</span><span class="sxs-lookup"><span data-stu-id="e9bed-108">After creating the JD Edwards EnterpriseOne port, you can browse JD Edwards EnterpriseOne by launching the Microsoft Adapter Wizard from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
## <a name="import-schemas-into-visual-studio"></a><span data-ttu-id="e9bed-109">将架构导入 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e9bed-109">Import schemas into Visual Studio</span></span>
  
1.  <span data-ttu-id="e9bed-110">打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e9bed-110">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="e9bed-111">右键单击的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，指向**添加**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="e9bed-111">Right-click the name of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="e9bed-112">单击**添加**以打开**添加适配器向导**。</span><span class="sxs-lookup"><span data-stu-id="e9bed-112">Click **Add** to open the **Add Adapter Wizard**.</span></span>  
  
4.  <span data-ttu-id="e9bed-113">上**选择适配器**页上，选择你想要导入架构的适配器的名称 (例如， **JDEEnterpriseOne**)。</span><span class="sxs-lookup"><span data-stu-id="e9bed-113">On the **Select Adapter** page, select the name of the adapter for which you want to import schemas (for example, **JDEEnterpriseOne**).</span></span>  
  
5.  <span data-ttu-id="e9bed-114">在**SQL Server**框中，选择 SQL server。</span><span class="sxs-lookup"><span data-stu-id="e9bed-114">In the **SQL Server** box, select a SQL server.</span></span>  
  
6.  <span data-ttu-id="e9bed-115">在**数据库**框中，选择一个数据库。</span><span class="sxs-lookup"><span data-stu-id="e9bed-115">In the **Database** box, select a database.</span></span>  
  
     <span data-ttu-id="e9bed-116">默认数据库与 SQL 服务器相同。</span><span class="sxs-lookup"><span data-stu-id="e9bed-116">The default database is the same one as your SQL server.</span></span>  
  
7.  <span data-ttu-id="e9bed-117">在**端口**框中，选择 SQL server，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="e9bed-117">In the **Port** box, select a SQL server, and then click **Next**.</span></span>  
  
     <span data-ttu-id="e9bed-118">浏览器中将显示 JD Edwards EnterpriseOne 系统。</span><span class="sxs-lookup"><span data-stu-id="e9bed-118">The JD Edwards EnterpriseOne system displays in the browser.</span></span>  
  
8.  <span data-ttu-id="e9bed-119">继续执行下一个过程。</span><span class="sxs-lookup"><span data-stu-id="e9bed-119">Continue with the next procedure below.</span></span>  
  
 <span data-ttu-id="e9bed-120">添加适配器向导将显示所有已定义系统的树视图。</span><span class="sxs-lookup"><span data-stu-id="e9bed-120">The Add Adapter Wizard displays a tree of all of the defined systems.</span></span> <span data-ttu-id="e9bed-121">JD Edwards EnterpriseOne 具有许多模块。</span><span class="sxs-lookup"><span data-stu-id="e9bed-121">JD Edwards EnterpriseOne has many modules.</span></span> <span data-ttu-id="e9bed-122">这些模块根据其名称的前三个字符组合在一起。</span><span class="sxs-lookup"><span data-stu-id="e9bed-122">The modules are grouped together according to the first three characters of their name.</span></span>  
  
-   <span data-ttu-id="e9bed-123">层次结构的第一层是该模块名称所有三个字符前缀的列表。</span><span class="sxs-lookup"><span data-stu-id="e9bed-123">The first level of the hierarchy is the list of all three-character prefixes for the module names.</span></span>  
  
-   <span data-ttu-id="e9bed-124">第二层列出所有共享相同三字符前缀的模块。</span><span class="sxs-lookup"><span data-stu-id="e9bed-124">The second level lists all the modules that share the same three-character prefix.</span></span>  
  
-   <span data-ttu-id="e9bed-125">最后一层列出属于某个模块的业务功能。</span><span class="sxs-lookup"><span data-stu-id="e9bed-125">The last level lists the business functions belonging to a module.</span></span> <span data-ttu-id="e9bed-126">当您展开服务图标时，便可以查看其操作。</span><span class="sxs-lookup"><span data-stu-id="e9bed-126">When you expand the services icon, you can view its operations.</span></span>  
  
 <span data-ttu-id="e9bed-127">展开某项操作后，将显示输入/输出参数。</span><span class="sxs-lookup"><span data-stu-id="e9bed-127">Expanding an operation displays the input/output arguments.</span></span> <span data-ttu-id="e9bed-128">您可以展开输入/输出参数以查看该参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e9bed-128">You can expand the input/output arguments to view the data types of the arguments.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9bed-129">如果服务器对象定义发生更改，您必须重新生成架构以刷新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="e9bed-129">If the server object definitions change, you must regenerate the schema to refresh the data it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9bed-130">如果您在生成架构后更改了 jdearglist.txt，则必须重新生成架构以刷新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="e9bed-130">If you change jdearglist.txt after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="e9bed-131">Jdearglist.txt 的详细信息，请参阅[处理字符串值](../core/handling-string-values2.md)。</span><span class="sxs-lookup"><span data-stu-id="e9bed-131">For more information on jdearglist.txt, see [Handling String Values](../core/handling-string-values2.md).</span></span>  
  
## <a name="select-the-schemas"></a><span data-ttu-id="e9bed-132">选择的架构</span><span class="sxs-lookup"><span data-stu-id="e9bed-132">Select the schemas</span></span>  
  
1.  <span data-ttu-id="e9bed-133">在**选择服务添加到导入**页上，展开的顶级节点**业务对象**节点或**业务服务**节点。</span><span class="sxs-lookup"><span data-stu-id="e9bed-133">In the **Select Services to Import** page, expand the top level node of the **Business Objects** node or the **Business Services** node.</span></span>  
  
2.  <span data-ttu-id="e9bed-134">选择你想要导入，然后单击项旁边的复选框**确定**。</span><span class="sxs-lookup"><span data-stu-id="e9bed-134">Select the check box next to the items that you want to import, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="e9bed-135">为选定 JD Edwards EnterpriseOne 项目生成的架构将会导入 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目中。</span><span class="sxs-lookup"><span data-stu-id="e9bed-135">Schemas generated for the selected JD Edwards EnterpriseOne items are imported into your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9bed-136">在使用通讯簿 (N0100041) 的字段名称是**cActionCode**。</span><span class="sxs-lookup"><span data-stu-id="e9bed-136">When using AddressBook (N0100041) the field name is **cActionCode**.</span></span> <span data-ttu-id="e9bed-137">此操作是 XML 文件自身的一部分。</span><span class="sxs-lookup"><span data-stu-id="e9bed-137">The action is part of the XML file itself.</span></span> <span data-ttu-id="e9bed-138">这些代码为：</span><span class="sxs-lookup"><span data-stu-id="e9bed-138">The codes are:</span></span>  
  
-   <span data-ttu-id="e9bed-139">A 代表添加</span><span class="sxs-lookup"><span data-stu-id="e9bed-139">A for Add</span></span>  
  
-   <span data-ttu-id="e9bed-140">C 代表更改</span><span class="sxs-lookup"><span data-stu-id="e9bed-140">C for Change</span></span>  
  
-   <span data-ttu-id="e9bed-141">D 代表删除</span><span class="sxs-lookup"><span data-stu-id="e9bed-141">D for Delete</span></span>  
  
-   <span data-ttu-id="e9bed-142">I 代表查询</span><span class="sxs-lookup"><span data-stu-id="e9bed-142">I for Inquiry</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e9bed-143">下一步</span><span class="sxs-lookup"><span data-stu-id="e9bed-143">Next step</span></span>
[<span data-ttu-id="e9bed-144">使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="e9bed-144">Use Message Context Properties</span></span>](../core/using-message-context-properties1.md)