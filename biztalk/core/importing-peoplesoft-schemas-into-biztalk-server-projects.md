---
title: 将 PeopleSoft 架构导入 Visual Studio |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 411f25f4-4431-44e4-84cf-5c515b3e32db
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89534c67d772f8b025289d61ab515f1585791d68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382483"
---
# <a name="import-peoplesoft-schemas-into-biztalk-server-projects"></a><span data-ttu-id="0168d-102">PeopleSoft 架构导入到 BizTalk Server 项目</span><span class="sxs-lookup"><span data-stu-id="0168d-102">Import PeopleSoft Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="0168d-103">创建 PeopleSoft Enterprise 系统后，可以浏览服务器和架构导入到 BizTalk Server 项目。</span><span class="sxs-lookup"><span data-stu-id="0168d-103">When you have created the PeopleSoft Enterprise system, you can browse the server and import schemas into a BizTalk Server project.</span></span>  
  
## <a name="browse-a-peoplesoft-server-system"></a><span data-ttu-id="0168d-104">浏览 PeopleSoft 服务器系统</span><span class="sxs-lookup"><span data-stu-id="0168d-104">Browse a PeopleSoft Server System</span></span>  
  
1.  <span data-ttu-id="0168d-105">右键单击 BizTalk Server 项目，然后选择以下选项之一。</span><span class="sxs-lookup"><span data-stu-id="0168d-105">Right-click a BizTalk Server project, and select one of the following options.</span></span>  
  
    -   <span data-ttu-id="0168d-106">如果你已为对象生成的架构，请选择**外**，单击**添加架构**，然后选择要向业务流程添加的现有架构。</span><span class="sxs-lookup"><span data-stu-id="0168d-106">If you already have a schema generated for your object, select **Add**, click **Add Schema,** and then select the existing schema to add to your orchestration,.</span></span>  
  
    -   <span data-ttu-id="0168d-107">如果不为对象生成的架构，请选择**外**，然后单击**添加生成的项**，然后选择适配器。</span><span class="sxs-lookup"><span data-stu-id="0168d-107">If you do not have a schema generated for your object, select **Add**, then click **Add Generated Items**, and then select the adapter.</span></span> <span data-ttu-id="0168d-108">这是相同的名称中输入**AdapterProperties**对话框。</span><span class="sxs-lookup"><span data-stu-id="0168d-108">This is the same name entered in the **AdapterProperties** dialog box.</span></span> <span data-ttu-id="0168d-109">有关详细信息，请参阅 BizTalk 主帮助中的"适配器属性对话框"。</span><span class="sxs-lookup"><span data-stu-id="0168d-109">For more information, see "Adapter Properties Dialog Box" in the main BizTalk help.</span></span>  
  
2.  <span data-ttu-id="0168d-110">单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="0168d-110">Click Next.</span></span>  
  
     <span data-ttu-id="0168d-111">PeopleSoft Enterprise 系统将显示在浏览器中。</span><span class="sxs-lookup"><span data-stu-id="0168d-111">The PeopleSoft Enterprise system appears in the browser.</span></span>  
  
     <span data-ttu-id="0168d-112">![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")</span><span class="sxs-lookup"><span data-stu-id="0168d-112">![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")</span></span>  
  
### <a name="component-interfaces"></a><span data-ttu-id="0168d-113">组件接口</span><span class="sxs-lookup"><span data-stu-id="0168d-113">Component Interfaces</span></span>  
 <span data-ttu-id="0168d-114">在中**组件接口**(CI) 文件夹中，您可以在系统中查看所有可用组件接口。</span><span class="sxs-lookup"><span data-stu-id="0168d-114">In the **Component Interfaces** (CI) folder, you can view all the available component interfaces in the system.</span></span> <span data-ttu-id="0168d-115">组件接口声明方法和它支持的属性的集。</span><span class="sxs-lookup"><span data-stu-id="0168d-115">A component interface declares the set of methods and properties that it supports.</span></span> <span data-ttu-id="0168d-116">组件接口不实现行为或属性。</span><span class="sxs-lookup"><span data-stu-id="0168d-116">A component interface does not implement behavior or properties.</span></span> <span data-ttu-id="0168d-117">用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器公开了标准方法，例如，CreateEx、 DeleteOnly、 Find、 Get、 和 UpdateEx。</span><span class="sxs-lookup"><span data-stu-id="0168d-117">Microsoft BizTalk Adapter for PeopleSoft Enterprise exposes standard methods, for example, CreateEx, DeleteOnly, Find, Get, and UpdateEx.</span></span> <span data-ttu-id="0168d-118">有关这些方法的说明，请参阅[附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="0168d-118">For a description of these methods, see [Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md).</span></span>  
  
## <a name="generate-schemas"></a><span data-ttu-id="0168d-119">生成架构</span><span class="sxs-lookup"><span data-stu-id="0168d-119">Generate Schemas</span></span>  
  
<span data-ttu-id="0168d-120">选择你想要将架构导入的项：**消息**，**查询**，或**组件接口**。</span><span class="sxs-lookup"><span data-stu-id="0168d-120">Select the item for which you want to import schemas: a **Message**, **Query**, or **Component Interface**.</span></span>  <span data-ttu-id="0168d-121">BizTalk Server 生成的选定项的架构，并将其导入 BizTalk Server 项目。</span><span class="sxs-lookup"><span data-stu-id="0168d-121">BizTalk Server generates the schemas for the selected item and imports them into a BizTalk Server project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0168d-122">如果服务器对象定义发生更改，必须重新生成架构以更新其包含的数据。</span><span class="sxs-lookup"><span data-stu-id="0168d-122">If the server object definitions change, you must regenerate the schema to update the data it contains.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0168d-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="0168d-123">See Also</span></span>  
 [<span data-ttu-id="0168d-124">创建 PeopleSoft 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="0168d-124">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)