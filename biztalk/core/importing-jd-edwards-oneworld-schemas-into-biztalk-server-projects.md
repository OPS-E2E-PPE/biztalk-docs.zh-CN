---
title: JD Edwards OneWorld 架构导入到 BizTalk Server 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- generating schemas
- importing schemas
- schemas, generating
- schemas, importing into BizTalk Server projects
ms.assetid: 5bcaa276-8c76-4212-b373-de86e3008a69
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa1950409b71ddc7773dc6ad1ddbee3591dc1d63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382456"
---
# <a name="importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects"></a><span data-ttu-id="97057-102">JD Edwards OneWorld 架构导入到 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="97057-102">Importing JD Edwards OneWorld Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="97057-103">本主题讨论浏览 JD Edwards OneWorld 服务器和导入到架构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="97057-103">This topic discusses browsing a JD Edwards OneWorld server and importing the schemas into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97057-104">您必须确保已设置 arglist。</span><span class="sxs-lookup"><span data-stu-id="97057-104">You must ensure that you set the arglist.</span></span> <span data-ttu-id="97057-105">在业务流程中生成架构之前，必须更新 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="97057-105">You must update the jdearglist.txt before you generate the schemas in the orchestration.</span></span> <span data-ttu-id="97057-106">有关详细信息，请参阅[处理字符串值](../core/handling-string-values1.md)。</span><span class="sxs-lookup"><span data-stu-id="97057-106">For more information, see [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97057-107">每次更改 jdearglist，您必须重新生成该业务对象的架构。</span><span class="sxs-lookup"><span data-stu-id="97057-107">Each time that you change the jdearglist, you must regenerate the schemas for that business object.</span></span>  
  
 <span data-ttu-id="97057-108">创建 JD Edwards OneWorld 逻辑系统之后, 可以通过打开 BizTalk Server 项目中的 Microsoft 适配器向导浏览 JD Edwards OneWorld。</span><span class="sxs-lookup"><span data-stu-id="97057-108">After creating the JD Edwards OneWorld logical system, you can browse JD Edwards OneWorld by opening the Microsoft Adapter Wizard from a BizTalk Server project.</span></span>  
  
### <a name="to-import-schemas"></a><span data-ttu-id="97057-109">若要导入架构</span><span class="sxs-lookup"><span data-stu-id="97057-109">To import schemas</span></span>  
  
1. <span data-ttu-id="97057-110">打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97057-110">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="97057-111">右键单击[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，指向**添加**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="97057-111">Right-click the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
3. <span data-ttu-id="97057-112">单击**添加适配器**，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="97057-112">Click **Add adapter**, and select **Open**.</span></span>  
  
4. <span data-ttu-id="97057-113">选择适配器，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="97057-113">Select the adapter, and click **Next**.</span></span>  
  
    <span data-ttu-id="97057-114">JD。</span><span class="sxs-lookup"><span data-stu-id="97057-114">The JD.</span></span> <span data-ttu-id="97057-115">Edwards OneWorld XE 系统将显示在浏览器。</span><span class="sxs-lookup"><span data-stu-id="97057-115">Edwards OneWorld XE system appears in the browser.</span></span>  
  
    <span data-ttu-id="97057-116">![](../core/media/jdedadapter-04-jdebrowse.gif "JDEdAdapter_04_JDEBrowse")</span><span class="sxs-lookup"><span data-stu-id="97057-116">![](../core/media/jdedadapter-04-jdebrowse.gif "JDEdAdapter_04_JDEBrowse")</span></span>  
  
    <span data-ttu-id="97057-117">适配器向导会显示所有已定义的系统的树。</span><span class="sxs-lookup"><span data-stu-id="97057-117">The Adapter Wizard displays a tree of all of the defined systems.</span></span> <span data-ttu-id="97057-118">JD Edwards OneWorld 中有太多的模块，以显示一个长列表中。</span><span class="sxs-lookup"><span data-stu-id="97057-118">JD Edwards OneWorld has too many modules to show in one long list.</span></span> <span data-ttu-id="97057-119">根据其名称的前三个字符，将模块组合在一起。</span><span class="sxs-lookup"><span data-stu-id="97057-119">The modules are grouped together according to the first three characters of their name.</span></span>  
  
   - <span data-ttu-id="97057-120">在层次结构的第一个级别是该模块名称所有三个字符前缀的列表。</span><span class="sxs-lookup"><span data-stu-id="97057-120">The first level of the hierarchy is the list of all three-character prefixes for the module names.</span></span>  
  
   - <span data-ttu-id="97057-121">第二层列出所有共享相同三字符前缀的模块。</span><span class="sxs-lookup"><span data-stu-id="97057-121">The second level lists all the modules that share the same three-character prefix.</span></span>  
  
   - <span data-ttu-id="97057-122">最后一层列出属于某个模块的业务功能。</span><span class="sxs-lookup"><span data-stu-id="97057-122">The last level lists the business functions belonging to a module.</span></span> <span data-ttu-id="97057-123">当您展开服务图标时可以查看其操作。</span><span class="sxs-lookup"><span data-stu-id="97057-123">When you expand the services icon you can view its operations.</span></span>  
  
     <span data-ttu-id="97057-124">展开某项操作显示的输入/输出参数。</span><span class="sxs-lookup"><span data-stu-id="97057-124">Expanding an operation displays the input/output arguments.</span></span>  
  
     <span data-ttu-id="97057-125">您可以展开要查看的自变量的数据类型的输入/输出参数。</span><span class="sxs-lookup"><span data-stu-id="97057-125">You can expand the input/output arguments to view the data types of the arguments.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="97057-126">如果服务器对象定义发生更改，必须重新生成架构以刷新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="97057-126">If the server object definitions change, you must regenerate the schema to refresh the data it contains.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="97057-127">如果生成架构后更改了 jdearglist.txt，必须重新生成架构以刷新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="97057-127">If you change jdearglist.txt after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="97057-128">有关 jdearglist.txt 的信息，请参阅[处理字符串值](../core/handling-string-values1.md)。</span><span class="sxs-lookup"><span data-stu-id="97057-128">For information on jdearglist.txt, see to [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
## <a name="generating-schemas"></a><span data-ttu-id="97057-129">生成架构</span><span class="sxs-lookup"><span data-stu-id="97057-129">Generating Schemas</span></span>  
 <span data-ttu-id="97057-130">使用以下过程来生成架构。</span><span class="sxs-lookup"><span data-stu-id="97057-130">Use the following procedure to generate schemas.</span></span>  
  
#### <a name="to-generate-schemas"></a><span data-ttu-id="97057-131">若要生成架构</span><span class="sxs-lookup"><span data-stu-id="97057-131">To generate schemas</span></span>  
  
1.  <span data-ttu-id="97057-132">选择你想要将架构导入的项。</span><span class="sxs-lookup"><span data-stu-id="97057-132">Select the item for which you want to import schemas.</span></span>  
  
2.  <span data-ttu-id="97057-133">单击 （或拖动） 以将项添加到**传输**窗格 （对于到 J.Edwards OneWorld 的入站调用）。</span><span class="sxs-lookup"><span data-stu-id="97057-133">Click (or drag) to add the item to the **Transmit** pane (for an inbound to J. Edwards OneWorld call).</span></span>  
  
3.  <span data-ttu-id="97057-134">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="97057-134">Click **OK**.</span></span>  
  
     <span data-ttu-id="97057-135">对所选的 JD Edwards OneWorld 项目生成的架构导入 BizTalk Server 项目中。</span><span class="sxs-lookup"><span data-stu-id="97057-135">Schemas generated for the selected JD Edwards OneWorld item are imported into the BizTalk Server project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97057-136">使用 AddressBook (N0100041) 时的字段名称是**cActionCode**。</span><span class="sxs-lookup"><span data-stu-id="97057-136">When using AddressBook (N0100041) the field name is **cActionCode**.</span></span> <span data-ttu-id="97057-137">操作为 XML 文件本身的一部分。</span><span class="sxs-lookup"><span data-stu-id="97057-137">The action is part of the XML file itself.</span></span> <span data-ttu-id="97057-138">这些代码为：</span><span class="sxs-lookup"><span data-stu-id="97057-138">The codes are:</span></span>  
>   
>  <span data-ttu-id="97057-139">-A 代表添加</span><span class="sxs-lookup"><span data-stu-id="97057-139">--A for Add</span></span>  
>   
>  <span data-ttu-id="97057-140">--C 表示更改</span><span class="sxs-lookup"><span data-stu-id="97057-140">--C for Change</span></span>  
>   
>  <span data-ttu-id="97057-141">-D 代表删除</span><span class="sxs-lookup"><span data-stu-id="97057-141">--D for Delete</span></span>  
>   
>  <span data-ttu-id="97057-142">--I 表示查询</span><span class="sxs-lookup"><span data-stu-id="97057-142">--I for Inquiry</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97057-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="97057-143">See Also</span></span>  
 [<span data-ttu-id="97057-144">将项目添加到 BizTalk 管理</span><span class="sxs-lookup"><span data-stu-id="97057-144">Add the artifacts to BizTalk Administration</span></span>](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)