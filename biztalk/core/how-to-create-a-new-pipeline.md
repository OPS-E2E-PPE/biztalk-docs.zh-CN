---
title: 如何创建一条新管道 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipelines, warnings
- Pipeline Designer, warnings
- pipelines, creating
ms.assetid: bd95325e-1a72-4705-80f6-37ac092d11a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83c1df14c0015ac26b99ad8f0760fe18438e8024
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248757"
---
# <a name="how-to-create-a-new-pipeline"></a><span data-ttu-id="992ef-102">如何创建新管道</span><span class="sxs-lookup"><span data-stu-id="992ef-102">How to Create a New Pipeline</span></span>
<span data-ttu-id="992ef-103">可以向项目添加管道模板来创建新的管道。</span><span class="sxs-lookup"><span data-stu-id="992ef-103">You can add a pipeline template to your project to create a new pipeline.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="992ef-104">不应添加一个包含包含使用该 pipleine 组件的项目的解决方案的一个自定义管道组件的实现项目。</span><span class="sxs-lookup"><span data-stu-id="992ef-104">You should not add a project that contains an implementation of a custom pipeline component to a solution that contains a project that uses that pipleine component.</span></span> <span data-ttu-id="992ef-105">如果添加，则下次重新生成该解决方案时，您将收到一条错误消息，指明输出 dll 正由另一个进程使用。</span><span class="sxs-lookup"><span data-stu-id="992ef-105">If you do, the next time you rebuild the solution you will get an error saying the output dll is being used by another process.</span></span>  
  
### <a name="to-create-a-new-pipeline"></a><span data-ttu-id="992ef-106">创建新的管道</span><span class="sxs-lookup"><span data-stu-id="992ef-106">To create a new pipeline</span></span>  
  
1.  <span data-ttu-id="992ef-107">在解决方案资源管理器中，选择要在其中创建管道的项目。</span><span class="sxs-lookup"><span data-stu-id="992ef-107">In Solution Explorer, select the project in which you want to create the pipeline.</span></span>  
  
2.  <span data-ttu-id="992ef-108">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="992ef-108">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="992ef-109">在**添加新项**对话框中，选择**接收管道**或**发送管道**通过一次单击它的模板。</span><span class="sxs-lookup"><span data-stu-id="992ef-109">In the **Add New Item** dialog box, select a **Receive Pipeline** or **Send Pipeline** template by clicking it once.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="992ef-110">如果您双击模板，管道将自动创建具有默认名称，将出现在**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="992ef-110">If you double-click the template, the pipeline will automatically be created with the default name that appears in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="992ef-111">在**名称**字段中，键入管道的名称。</span><span class="sxs-lookup"><span data-stu-id="992ef-111">In the **Name** field, type a name for the pipeline.</span></span>  
  
5.  <span data-ttu-id="992ef-112">单击 **“打开”**。</span><span class="sxs-lookup"><span data-stu-id="992ef-112">Click **Open**.</span></span>  
  
     <span data-ttu-id="992ef-113">此时，新的管道将显示在解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="992ef-113">The new pipeline appears in Solution Explorer.</span></span> <span data-ttu-id="992ef-114">设计图面将显示管道阶段和一组默认的组件。</span><span class="sxs-lookup"><span data-stu-id="992ef-114">The design surface displays pipeline stages and a default set of components.</span></span>  
  
 <span data-ttu-id="992ef-115">有关将管道组件添加到管道的信息，请参阅[如何将组件添加到管道](../core/how-to-add-a-component-to-a-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="992ef-115">For information about adding pipeline components to the pipeline, see [How to Add a Component to a Pipeline](../core/how-to-add-a-component-to-a-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="992ef-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="992ef-116">See Also</span></span>  
 <span data-ttu-id="992ef-117">[如何打开管道](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="992ef-117">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="992ef-118">[如何保存管道](../core/how-to-save-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="992ef-118">[How to Save a Pipeline](../core/how-to-save-a-pipeline.md) </span></span>  
 <span data-ttu-id="992ef-119">[如何使用工具箱](../core/how-to-use-the-toolbox.md) </span><span class="sxs-lookup"><span data-stu-id="992ef-119">[How to Use the Toolbox](../core/how-to-use-the-toolbox.md) </span></span>  
 <span data-ttu-id="992ef-120">[如何使用键盘导航](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="992ef-120">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="992ef-121">使用管道设计器中创建管道</span><span class="sxs-lookup"><span data-stu-id="992ef-121">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)