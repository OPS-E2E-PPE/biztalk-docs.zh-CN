---
title: "将博士 Edwards OneWorld 架构导入到 BizTalk Server 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generating schemas
- importing schemas
- schemas, generating
- schemas, importing into BizTalk Server projects
ms.assetid: 5bcaa276-8c76-4212-b373-de86e3008a69
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35b0d7fec5acc991ae6c141f57297b7511281be3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-jd-edwards-oneworld-schemas-into-biztalk-server-projects"></a><span data-ttu-id="83429-102">将 JD Edwards OneWorld 架构导入到 BizTalk Server 项目中</span><span class="sxs-lookup"><span data-stu-id="83429-102">Importing JD Edwards OneWorld Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="83429-103">本主题讨论如何浏览 JD Edwards OneWorld 服务器，并将架构导入到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目中。</span><span class="sxs-lookup"><span data-stu-id="83429-103">This topic discusses browsing a JD Edwards OneWorld server and importing the schemas into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83429-104">您必须确保已设置 arglist。</span><span class="sxs-lookup"><span data-stu-id="83429-104">You must ensure that you set the arglist.</span></span> <span data-ttu-id="83429-105">在业务流程中生成架构之前，您必须先更新 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="83429-105">You must update the jdearglist.txt before you generate the schemas in the orchestration.</span></span> <span data-ttu-id="83429-106">有关详细信息，请参阅[处理字符串值](../core/handling-string-values1.md)。</span><span class="sxs-lookup"><span data-stu-id="83429-106">For more information, see [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83429-107">每次更改 jdearglist 时，都必须为该业务对象重新生成架构。</span><span class="sxs-lookup"><span data-stu-id="83429-107">Each time that you change the jdearglist, you must regenerate the schemas for that business object.</span></span>  
  
 <span data-ttu-id="83429-108">在创建 JD Edwards OneWorld 逻辑系统之后，您可以通过打开 BizTalk Server 项目中的 Microsoft 适配器向导来浏览 JD Edwards OneWorld。</span><span class="sxs-lookup"><span data-stu-id="83429-108">After creating the JD Edwards OneWorld logical system, you can browse JD Edwards OneWorld by opening the Microsoft Adapter Wizard from a BizTalk Server project.</span></span>  
  
### <a name="to-import-schemas"></a><span data-ttu-id="83429-109">若要导入架构</span><span class="sxs-lookup"><span data-stu-id="83429-109">To import schemas</span></span>  
  
1.  <span data-ttu-id="83429-110">打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="83429-110">Open [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="83429-111">右键单击[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，指向**添加**，然后选择**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="83429-111">Right-click the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project, point to **Add**, and select **Add Generated Items**.</span></span>  
  
3.  <span data-ttu-id="83429-112">单击**添加适配器**，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="83429-112">Click **Add adapter**, and select **Open**.</span></span>  
  
4.  <span data-ttu-id="83429-113">选择适配器，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="83429-113">Select the adapter, and click **Next**.</span></span>  
  
     <span data-ttu-id="83429-114">博士。</span><span class="sxs-lookup"><span data-stu-id="83429-114">The JD.</span></span> <span data-ttu-id="83429-115">Edwards OneWorld XE 系统将显示在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="83429-115">Edwards OneWorld XE system appears in the browser.</span></span>  
  
     ![](../core/media/jdedadapter-04-jdebrowse.gif "JDEdAdapter_04_JDEBrowse")  
  
     <span data-ttu-id="83429-116">适配器向导会显示所有已定义的系统树。</span><span class="sxs-lookup"><span data-stu-id="83429-116">The Adapter Wizard displays a tree of all of the defined systems.</span></span> <span data-ttu-id="83429-117">JD Edwards OneWorld 的模块太多，无法显示在一个较长的列表中。</span><span class="sxs-lookup"><span data-stu-id="83429-117">JD Edwards OneWorld has too many modules to show in one long list.</span></span> <span data-ttu-id="83429-118">这些模块根据其名称的前三个字符组合在一起。</span><span class="sxs-lookup"><span data-stu-id="83429-118">The modules are grouped together according to the first three characters of their name.</span></span>  
  
    -   <span data-ttu-id="83429-119">层次结构的第一层是该模块名称所有三个字符前缀的列表。</span><span class="sxs-lookup"><span data-stu-id="83429-119">The first level of the hierarchy is the list of all three-character prefixes for the module names.</span></span>  
  
    -   <span data-ttu-id="83429-120">第二层列出所有共享相同三字符前缀的模块。</span><span class="sxs-lookup"><span data-stu-id="83429-120">The second level lists all the modules that share the same three-character prefix.</span></span>  
  
    -   <span data-ttu-id="83429-121">最后一层列出属于某个模块的业务功能。</span><span class="sxs-lookup"><span data-stu-id="83429-121">The last level lists the business functions belonging to a module.</span></span> <span data-ttu-id="83429-122">当您展开服务图标时，可以查看其操作。</span><span class="sxs-lookup"><span data-stu-id="83429-122">When you expand the services icon you can view its operations.</span></span>  
  
     <span data-ttu-id="83429-123">展开某项操作后，将显示输入/输出参数。</span><span class="sxs-lookup"><span data-stu-id="83429-123">Expanding an operation displays the input/output arguments.</span></span>  
  
     <span data-ttu-id="83429-124">您可以展开输入/输出参数以查看该参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="83429-124">You can expand the input/output arguments to view the data types of the arguments.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83429-125">如果服务器对象定义发生更改，您必须重新生成架构以刷新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="83429-125">If the server object definitions change, you must regenerate the schema to refresh the data it contains.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83429-126">如果您在生成架构后更改了 jdearglist.txt，则必须重新生成架构以刷新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="83429-126">If you change jdearglist.txt after generating your schema, you must regenerate the schema to refresh the data it contains.</span></span> <span data-ttu-id="83429-127">有关 jdearglist.txt 的信息，请参阅[处理字符串值](../core/handling-string-values1.md)。</span><span class="sxs-lookup"><span data-stu-id="83429-127">For information on jdearglist.txt, see to [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
## <a name="generating-schemas"></a><span data-ttu-id="83429-128">生成架构</span><span class="sxs-lookup"><span data-stu-id="83429-128">Generating Schemas</span></span>  
 <span data-ttu-id="83429-129">使用以下过程来生成架构。</span><span class="sxs-lookup"><span data-stu-id="83429-129">Use the following procedure to generate schemas.</span></span>  
  
#### <a name="to-generate-schemas"></a><span data-ttu-id="83429-130">若要生成架构</span><span class="sxs-lookup"><span data-stu-id="83429-130">To generate schemas</span></span>  
  
1.  <span data-ttu-id="83429-131">选择要导入架构的项目。</span><span class="sxs-lookup"><span data-stu-id="83429-131">Select the item for which you want to import schemas.</span></span>  
  
2.  <span data-ttu-id="83429-132">单击 （或拖动） 若要向其中添加项**传输**窗格中 （对于一个到 J.Edwards OneWorld 的入站调用）。</span><span class="sxs-lookup"><span data-stu-id="83429-132">Click (or drag) to add the item to the **Transmit** pane (for an inbound to J. Edwards OneWorld call).</span></span>  
  
3.  <span data-ttu-id="83429-133">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="83429-133">Click **OK**.</span></span>  
  
     <span data-ttu-id="83429-134">将为选定 JD Edwards OneWorld 项目生成的构架导入到 BizTalk Server 项目。</span><span class="sxs-lookup"><span data-stu-id="83429-134">Schemas generated for the selected JD Edwards OneWorld item are imported into the BizTalk Server project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83429-135">在使用通讯簿 (N0100041) 的字段名称是**cActionCode**。</span><span class="sxs-lookup"><span data-stu-id="83429-135">When using AddressBook (N0100041) the field name is **cActionCode**.</span></span> <span data-ttu-id="83429-136">此操作是 XML 文件自身的一部分。</span><span class="sxs-lookup"><span data-stu-id="83429-136">The action is part of the XML file itself.</span></span> <span data-ttu-id="83429-137">这些代码为：</span><span class="sxs-lookup"><span data-stu-id="83429-137">The codes are:</span></span>  
>   
>  <span data-ttu-id="83429-138">-A 的添加</span><span class="sxs-lookup"><span data-stu-id="83429-138">--A for Add</span></span>  
>   
>  <span data-ttu-id="83429-139">--C 表示更改</span><span class="sxs-lookup"><span data-stu-id="83429-139">--C for Change</span></span>  
>   
>  <span data-ttu-id="83429-140">-D 删除</span><span class="sxs-lookup"><span data-stu-id="83429-140">--D for Delete</span></span>  
>   
>  <span data-ttu-id="83429-141">--I 表示查询</span><span class="sxs-lookup"><span data-stu-id="83429-141">--I for Inquiry</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83429-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83429-142">See Also</span></span>  
 [<span data-ttu-id="83429-143">创建博士 Edwards OneWorld 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="83429-143">Creating JD Edwards OneWorld Send Handlers</span></span>](../core/creating-jd-edwards-oneworld-send-handlers.md)