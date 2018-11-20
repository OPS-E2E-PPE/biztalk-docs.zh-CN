---
title: 如何创建新的管道 |Microsoft Docs
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
ms.openlocfilehash: 00f19818dd5df6cafaf51298a0463ea745736ab5
ms.sourcegitcommit: c3070a7a3f332857357f056dc632829b43869c17
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2018
ms.locfileid: "51630386"
---
# <a name="how-to-create-a-new-pipeline"></a><span data-ttu-id="dce0e-102">如何创建新管道</span><span class="sxs-lookup"><span data-stu-id="dce0e-102">How to Create a New Pipeline</span></span>
<span data-ttu-id="dce0e-103">可以向项目添加管道模板来创建新的管道。</span><span class="sxs-lookup"><span data-stu-id="dce0e-103">You can add a pipeline template to your project to create a new pipeline.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="dce0e-104">不应添加到包含使用该管道组件的项目的解决方案的自定义管道组件的实现包含一个项目。</span><span class="sxs-lookup"><span data-stu-id="dce0e-104">You should not add a project that contains an implementation of a custom pipeline component to a solution that contains a project that uses that pipeline component.</span></span> <span data-ttu-id="dce0e-105">如果添加，则下次重新生成该解决方案时，您将收到一条错误消息，指明输出 dll 正由另一个进程使用。</span><span class="sxs-lookup"><span data-stu-id="dce0e-105">If you do, the next time you rebuild the solution you will get an error saying the output dll is being used by another process.</span></span>  
  
### <a name="to-create-a-new-pipeline"></a><span data-ttu-id="dce0e-106">创建新的管道</span><span class="sxs-lookup"><span data-stu-id="dce0e-106">To create a new pipeline</span></span>  
  
1. <span data-ttu-id="dce0e-107">在解决方案资源管理器中，选择要在其中创建管道的项目。</span><span class="sxs-lookup"><span data-stu-id="dce0e-107">In Solution Explorer, select the project in which you want to create the pipeline.</span></span>  
  
2. <span data-ttu-id="dce0e-108">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="dce0e-108">On the **Project** menu, click **Add New Item**.</span></span>  
  
3. <span data-ttu-id="dce0e-109">在中**添加新项**对话框中，选择**接收管道**或**发送管道**通过一次单击模板。</span><span class="sxs-lookup"><span data-stu-id="dce0e-109">In the **Add New Item** dialog box, select a **Receive Pipeline** or **Send Pipeline** template by clicking it once.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="dce0e-110">如果双击模板，该管道将自动创建具有默认名称，将出现在**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="dce0e-110">If you double-click the template, the pipeline will automatically be created with the default name that appears in the **Name** field.</span></span>  
  
4. <span data-ttu-id="dce0e-111">在中**名称**字段中，键入管道的名称。</span><span class="sxs-lookup"><span data-stu-id="dce0e-111">In the **Name** field, type a name for the pipeline.</span></span>  
  
5. <span data-ttu-id="dce0e-112">单击 **“打开”**。</span><span class="sxs-lookup"><span data-stu-id="dce0e-112">Click **Open**.</span></span>  
  
    <span data-ttu-id="dce0e-113">此时，新的管道将显示在解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="dce0e-113">The new pipeline appears in Solution Explorer.</span></span> <span data-ttu-id="dce0e-114">设计图面将显示管道阶段和一组默认的组件。</span><span class="sxs-lookup"><span data-stu-id="dce0e-114">The design surface displays pipeline stages and a default set of components.</span></span>  
  
   <span data-ttu-id="dce0e-115">有关向管道添加管道组件的信息，请参阅[如何将组件添加到管道](../core/how-to-add-a-component-to-a-pipeline.md)。</span><span class="sxs-lookup"><span data-stu-id="dce0e-115">For information about adding pipeline components to the pipeline, see [How to Add a Component to a Pipeline](../core/how-to-add-a-component-to-a-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce0e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dce0e-116">See Also</span></span>  
 <span data-ttu-id="dce0e-117">[如何打开管道](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="dce0e-117">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="dce0e-118">[如何保存管道](../core/how-to-save-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="dce0e-118">[How to Save a Pipeline](../core/how-to-save-a-pipeline.md) </span></span>  
 <span data-ttu-id="dce0e-119">[如何使用工具箱](../core/how-to-use-the-toolbox.md) </span><span class="sxs-lookup"><span data-stu-id="dce0e-119">[How to Use the Toolbox](../core/how-to-use-the-toolbox.md) </span></span>  
 <span data-ttu-id="dce0e-120">[如何使用键盘导航](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="dce0e-120">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="dce0e-121">使用管道设计器创建管道</span><span class="sxs-lookup"><span data-stu-id="dce0e-121">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)