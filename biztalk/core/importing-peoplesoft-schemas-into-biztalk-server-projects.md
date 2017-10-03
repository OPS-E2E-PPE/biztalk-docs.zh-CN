---
title: "将 PeopleSoft 架构导入到 BizTalk Server 项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas, generating
- schemas, importing into BizTalk Server projects
- component interfaces
- BizTalk Server, schemas [PeopleSoft]
- importing schemas into BizTalk Server
ms.assetid: 411f25f4-4431-44e4-84cf-5c515b3e32db
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4946b438adc0d1e4d360b35207ff69e85b4e2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-peoplesoft-schemas-into-biztalk-server-projects"></a><span data-ttu-id="0221e-102">将 PeopleSoft 架构导入到 BizTalk Server 项目中 </span><span class="sxs-lookup"><span data-stu-id="0221e-102">Importing PeopleSoft Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="0221e-103">在创建 PeopleSoft Enterprise 系统之后，可以浏览服务器并将架构导入 BizTalk Server 项目。</span><span class="sxs-lookup"><span data-stu-id="0221e-103">When you have created the PeopleSoft Enterprise system, you can browse the server and import schemas into a BizTalk Server project.</span></span>  
  
## <a name="browsing-a-peoplesoft-server-system"></a><span data-ttu-id="0221e-104">浏览 PeopleSoft 服务器系统</span><span class="sxs-lookup"><span data-stu-id="0221e-104">Browsing a PeopleSoft Server System</span></span>  
 <span data-ttu-id="0221e-105">使用适配器向导浏览 PeopleSoft 服务器。</span><span class="sxs-lookup"><span data-stu-id="0221e-105">Use the Adapter Wizard to browse a PeopleSoft server.</span></span>  
  
#### <a name="to-browse-a-peoplesoft-server-system"></a><span data-ttu-id="0221e-106">若要浏览 PeopleSoft 服务器系统</span><span class="sxs-lookup"><span data-stu-id="0221e-106">To browse a PeopleSoft server system</span></span>  
  
1.  <span data-ttu-id="0221e-107">右键单击 BizTalk Server 项目，然后选择以下选项之一。</span><span class="sxs-lookup"><span data-stu-id="0221e-107">Right-click a BizTalk Server project, and select one of the following options.</span></span>  
  
    -   <span data-ttu-id="0221e-108">如果已经为你的对象生成的架构，选择**添加**，单击**添加架构，** ，然后选择现有的架构将添加到您的业务流程。</span><span class="sxs-lookup"><span data-stu-id="0221e-108">If you already have a schema generated for your object, select **Add**, click **Add Schema,** and then select the existing schema to add to your orchestration,.</span></span>  
  
    -   <span data-ttu-id="0221e-109">如果你没有为你的对象生成的架构，则选择**添加**，然后单击**添加生成的项**，适配器，然后选择。</span><span class="sxs-lookup"><span data-stu-id="0221e-109">If you do not have a schema generated for your object, select **Add**, then click **Add Generated Items**, and then select the adapter.</span></span> <span data-ttu-id="0221e-110">这是中输入的相同名称**AdapterProperties**对话框。</span><span class="sxs-lookup"><span data-stu-id="0221e-110">This is the same name entered in the **AdapterProperties** dialog box.</span></span> <span data-ttu-id="0221e-111">有关详细信息，请参阅 BizTalk 主帮助中的“适配器属性对话框”。</span><span class="sxs-lookup"><span data-stu-id="0221e-111">For more information, see "Adapter Properties Dialog Box" in the main BizTalk help.</span></span>  
  
2.  <span data-ttu-id="0221e-112">单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="0221e-112">Click Next.</span></span>  
  
     <span data-ttu-id="0221e-113">此时 PeopleSoft Enterprise 系统将显示在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="0221e-113">The PeopleSoft Enterprise system appears in the browser.</span></span>  
  
     ![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")  
  
### <a name="component-interfaces"></a><span data-ttu-id="0221e-114">组件接口</span><span class="sxs-lookup"><span data-stu-id="0221e-114">Component Interfaces</span></span>  
 <span data-ttu-id="0221e-115">在**组件接口**(CI) 文件夹中，你可以在系统中查看所有可用组件接口。</span><span class="sxs-lookup"><span data-stu-id="0221e-115">In the **Component Interfaces** (CI) folder, you can view all the available component interfaces in the system.</span></span> <span data-ttu-id="0221e-116">组件接口声明它所支持的方法和属性集。</span><span class="sxs-lookup"><span data-stu-id="0221e-116">A component interface declares the set of methods and properties that it supports.</span></span> <span data-ttu-id="0221e-117">组件接口不实现行为或属性。</span><span class="sxs-lookup"><span data-stu-id="0221e-117">A component interface does not implement behavior or properties.</span></span> <span data-ttu-id="0221e-118">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器公开了标准方法，例如 CreateEx、DeleteOnly、Find、Get 和 UpdateEx。</span><span class="sxs-lookup"><span data-stu-id="0221e-118">Microsoft BizTalk Adapter for PeopleSoft Enterprise exposes standard methods, for example, CreateEx, DeleteOnly, Find, Get, and UpdateEx.</span></span> <span data-ttu-id="0221e-119">有关这些方法的说明，请参阅[附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="0221e-119">For a description of these methods, see [Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md).</span></span>  
  
## <a name="generating-schemas"></a><span data-ttu-id="0221e-120">生成架构</span><span class="sxs-lookup"><span data-stu-id="0221e-120">Generating Schemas</span></span>  
 <span data-ttu-id="0221e-121">请按照以下步骤生成架构。</span><span class="sxs-lookup"><span data-stu-id="0221e-121">Follow these steps to generate schemas.</span></span>  
  
#### <a name="to-generate-the-schemas"></a><span data-ttu-id="0221e-122">若要生成架构</span><span class="sxs-lookup"><span data-stu-id="0221e-122">To generate the schemas</span></span>  
  
-   <span data-ttu-id="0221e-123">选择你想要导入架构的项目：**消息**，**查询**，或**组件接口**。</span><span class="sxs-lookup"><span data-stu-id="0221e-123">Select the item for which you want to import schemas: a **Message**, **Query**, or **Component Interface**.</span></span>  
  
     <span data-ttu-id="0221e-124">BizTalk Server 为选定项目生成架构，然后将其导入 BizTalk Server 项目。</span><span class="sxs-lookup"><span data-stu-id="0221e-124">BizTalk Server generates the schemas for the selected item and imports them into a BizTalk Server project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0221e-125">如果服务器对象定义更改，您必须重新生成架构以更新它包含的数据。</span><span class="sxs-lookup"><span data-stu-id="0221e-125">If the server object definitions change, you must regenerate the schema to update the data it contains.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0221e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0221e-126">See Also</span></span>  
 [<span data-ttu-id="0221e-127">创建 PeopleSoft 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="0221e-127">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)