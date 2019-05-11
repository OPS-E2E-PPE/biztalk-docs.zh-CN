---
title: JD Edwards EnterpriseOne 架构导入到 Visual Studio |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 640d5884-953a-46b6-b9dc-b931392a3059
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be4fd488c762d69a85278af12ef21b25967ff3da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382475"
---
# <a name="importing-schemas-into-biztalk-server-projects"></a><span data-ttu-id="6254e-102">架构导入到 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="6254e-102">Importing Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="6254e-103">本部分讨论浏览 JD Edwards EnterpriseOne 服务器和导入到架构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="6254e-103">This section discusses browsing a JD Edwards EnterpriseOne server and importing the schemas into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6254e-104">您必须确保已设置 arglist。</span><span class="sxs-lookup"><span data-stu-id="6254e-104">You must ensure that you set the arglist.</span></span> <span data-ttu-id="6254e-105">在业务流程中生成架构之前，必须更新 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="6254e-105">You must update jdearglist.txt before you generate the schemas in the orchestration.</span></span> <span data-ttu-id="6254e-106">有关详细信息，请参阅[处理字符串值](../core/handling-string-values2.md)。</span><span class="sxs-lookup"><span data-stu-id="6254e-106">For more information, see [Handling String Values](../core/handling-string-values2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6254e-107">每次更改 jdearglist，您必须重新生成该业务对象的架构。</span><span class="sxs-lookup"><span data-stu-id="6254e-107">Each time that you change the jdearglist, you must regenerate the schemas for that business object.</span></span>  
  
 <span data-ttu-id="6254e-108">创建 JD Edwards EnterpriseOne 端口后，可以浏览 JD Edwards EnterpriseOne 通过启动 Microsoft 适配器向导从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="6254e-108">After creating the JD Edwards EnterpriseOne port, you can browse JD Edwards EnterpriseOne by launching the Microsoft Adapter Wizard from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
## <a name="import-schemas-into-visual-studio"></a><span data-ttu-id="6254e-109">架构导入到 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6254e-109">Import schemas into Visual Studio</span></span>
  
1. <span data-ttu-id="6254e-110">打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6254e-110">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="6254e-111">右键单击名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，指向**添加**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="6254e-111">Right-click the name of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
3. <span data-ttu-id="6254e-112">单击**外**以打开**添加适配器向导**。</span><span class="sxs-lookup"><span data-stu-id="6254e-112">Click **Add** to open the **Add Adapter Wizard**.</span></span>  
  
4. <span data-ttu-id="6254e-113">上**选择适配器**页上，选择你想要导入架构的适配器的名称 (例如， **JDEEnterpriseOne**)。</span><span class="sxs-lookup"><span data-stu-id="6254e-113">On the **Select Adapter** page, select the name of the adapter for which you want to import schemas (for example, **JDEEnterpriseOne**).</span></span>  
  
5. <span data-ttu-id="6254e-114">在中**SQL Server**框中，选择一个 SQL server。</span><span class="sxs-lookup"><span data-stu-id="6254e-114">In the **SQL Server** box, select a SQL server.</span></span>  
  
6. <span data-ttu-id="6254e-115">在中**数据库**框中，选择一个数据库。</span><span class="sxs-lookup"><span data-stu-id="6254e-115">In the **Database** box, select a database.</span></span>  
  
    <span data-ttu-id="6254e-116">默认数据库是作为 SQL server 相同。</span><span class="sxs-lookup"><span data-stu-id="6254e-116">The default database is the same one as your SQL server.</span></span>  
  
7. <span data-ttu-id="6254e-117">在中**端口**框中，选择一个 SQL server，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="6254e-117">In the **Port** box, select a SQL server, and then click **Next**.</span></span>  
  
    <span data-ttu-id="6254e-118">JD Edwards EnterpriseOne 系统会显示在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="6254e-118">The JD Edwards EnterpriseOne system displays in the browser.</span></span>  
  
8. <span data-ttu-id="6254e-119">继续执行下一个过程。</span><span class="sxs-lookup"><span data-stu-id="6254e-119">Continue with the next procedure below.</span></span>  
  
   <span data-ttu-id="6254e-120">添加适配器向导会显示所有已定义的系统的树。</span><span class="sxs-lookup"><span data-stu-id="6254e-120">The Add Adapter Wizard displays a tree of all of the defined systems.</span></span> <span data-ttu-id="6254e-121">JD Edwards EnterpriseOne 具有许多模块。</span><span class="sxs-lookup"><span data-stu-id="6254e-121">JD Edwards EnterpriseOne has many modules.</span></span> <span data-ttu-id="6254e-122">根据其名称的前三个字符，将模块组合在一起。</span><span class="sxs-lookup"><span data-stu-id="6254e-122">The modules are grouped together according to the first three characters of their name.</span></span>  
  
- <span data-ttu-id="6254e-123">在层次结构的第一个级别是该模块名称所有三个字符前缀的列表。</span><span class="sxs-lookup"><span data-stu-id="6254e-123">The first level of the hierarchy is the list of all three-character prefixes for the module names.</span></span>  
  
- <span data-ttu-id="6254e-124">第二层列出所有共享相同三字符前缀的模块。</span><span class="sxs-lookup"><span data-stu-id="6254e-124">The second level lists all the modules that share the same three-character prefix.</span></span>  
  
- <span data-ttu-id="6254e-125">最后一层列出属于某个模块的业务功能。</span><span class="sxs-lookup"><span data-stu-id="6254e-125">The last level lists the business functions belonging to a module.</span></span> <span data-ttu-id="6254e-126">当您展开服务图标时，可以查看其操作。</span><span class="sxs-lookup"><span data-stu-id="6254e-126">When you expand the services icon, you can view its operations.</span></span>  
  
  <span data-ttu-id="6254e-127">展开某项操作显示的输入/输出参数。</span><span class="sxs-lookup"><span data-stu-id="6254e-127">Expanding an operation displays the input/output arguments.</span></span> <span data-ttu-id="6254e-128">您可以展开要查看的自变量的数据类型的输入/输出参数。</span><span class="sxs-lookup"><span data-stu-id="6254e-128">You can expand the input/output arguments to view the data types of the arguments.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6254e-129">如果服务器对象定义发生更改，必须重新生成架构以刷新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="6254e-129">If the server object definitions change, you must regenerate the schema to refresh the data it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6254e-130">如果生成架构后更改了 jdearglist.txt，必须重新生成架构以刷新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="6254e-130">If you change jdearglist.txt after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="6254e-131">有关 jdearglist.txt 的详细信息，请参阅[处理字符串值](../core/handling-string-values2.md)。</span><span class="sxs-lookup"><span data-stu-id="6254e-131">For more information on jdearglist.txt, see [Handling String Values](../core/handling-string-values2.md).</span></span>  
  
## <a name="select-the-schemas"></a><span data-ttu-id="6254e-132">选择架构</span><span class="sxs-lookup"><span data-stu-id="6254e-132">Select the schemas</span></span>  
  
1. <span data-ttu-id="6254e-133">在中**选择导入的服务**页上，展开的顶级节点**业务对象**节点或**业务服务**节点。</span><span class="sxs-lookup"><span data-stu-id="6254e-133">In the **Select Services to Import** page, expand the top level node of the **Business Objects** node or the **Business Services** node.</span></span>  
  
2. <span data-ttu-id="6254e-134">选择你想要导入，然后单击项旁边的复选框**确定**。</span><span class="sxs-lookup"><span data-stu-id="6254e-134">Select the check box next to the items that you want to import, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="6254e-135">为选定的 JD Edwards EnterpriseOne 项目将导入到生成的架构在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="6254e-135">Schemas generated for the selected JD Edwards EnterpriseOne items are imported into your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6254e-136">使用 AddressBook (N0100041) 时的字段名称是**cActionCode**。</span><span class="sxs-lookup"><span data-stu-id="6254e-136">When using AddressBook (N0100041) the field name is **cActionCode**.</span></span> <span data-ttu-id="6254e-137">操作为 XML 文件本身的一部分。</span><span class="sxs-lookup"><span data-stu-id="6254e-137">The action is part of the XML file itself.</span></span> <span data-ttu-id="6254e-138">这些代码为：</span><span class="sxs-lookup"><span data-stu-id="6254e-138">The codes are:</span></span>  
  
-   <span data-ttu-id="6254e-139">A 代表添加</span><span class="sxs-lookup"><span data-stu-id="6254e-139">A for Add</span></span>  
  
-   <span data-ttu-id="6254e-140">C 代表更改</span><span class="sxs-lookup"><span data-stu-id="6254e-140">C for Change</span></span>  
  
-   <span data-ttu-id="6254e-141">D 代表删除</span><span class="sxs-lookup"><span data-stu-id="6254e-141">D for Delete</span></span>  
  
-   <span data-ttu-id="6254e-142">I 代表查询</span><span class="sxs-lookup"><span data-stu-id="6254e-142">I for Inquiry</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="6254e-143">下一步</span><span class="sxs-lookup"><span data-stu-id="6254e-143">Next step</span></span>
[<span data-ttu-id="6254e-144">使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="6254e-144">Use Message Context Properties</span></span>](../core/using-message-context-properties1.md)