---
title: 如何添加标签和注释 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.functiod.general
ms.assetid: 58ff3a07-cbb6-4817-b301-d2b434ed2ad9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5720402e548992044eda26366c8b7b50bb95746a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970811"
---
# <a name="how-to-label-and-comment-a-functoid"></a><span data-ttu-id="997ae-102">如何标签和注释 Functoid</span><span class="sxs-lookup"><span data-stu-id="997ae-102">How to Label and Comment a Functoid</span></span>
<span data-ttu-id="997ae-103">标签和注释对于记录映射中 functoid 或链接的作用非常有用。</span><span class="sxs-lookup"><span data-stu-id="997ae-103">Labels and comments are helpful to document the purpose of a functoid or a link in a map.</span></span> <span data-ttu-id="997ae-104">你可以使用**标签**属性，以提供 functoid 的名称。</span><span class="sxs-lookup"><span data-stu-id="997ae-104">You can use the **Label** property to provide a name for a functoid.</span></span> <span data-ttu-id="997ae-105">**注释**属性使您能够提供有关 functoid，关于由它所执行的操作通常相关信息的其他信息。</span><span class="sxs-lookup"><span data-stu-id="997ae-105">The **Comments** property enables you to provide additional information about the functoid, typically relevant information about the operation being performed by it.</span></span>  
  
 <span data-ttu-id="997ae-106">下图显示了 functoid 的标签和注释。</span><span class="sxs-lookup"><span data-stu-id="997ae-106">The following figure shows the label and comments for a functoid.</span></span> <span data-ttu-id="997ae-107">functoid 从源架构中添加两个输入（Field1 和 Field3），并将结果输出到目标架构中的 Field4。</span><span class="sxs-lookup"><span data-stu-id="997ae-107">The functoid adds two inputs (Field1 and Field3) from the source schema and outputs the result to Field4 in the target schema.</span></span> <span data-ttu-id="997ae-108">在此例中，functoid 标签是“Add Field1 and Field3”，注释是“The addition is an output to Field4”。</span><span class="sxs-lookup"><span data-stu-id="997ae-108">In this example, the functoid label is “Add Field1 and Field3” and the comment is “The addition is an output to Field4”.</span></span>  
  
 <span data-ttu-id="997ae-109">![插入 functoid 标签和注释](../core/media/label.gif "Label_")</span><span class="sxs-lookup"><span data-stu-id="997ae-109">![Inserting functoid labels and comments](../core/media/label.gif "Label_")</span></span>  
  
 <span data-ttu-id="997ae-110">因为 functoid 可能是非常复杂的映射的一部分，所以适当地标记和另外提供相关注释非常重要。</span><span class="sxs-lookup"><span data-stu-id="997ae-110">Because a functoid can be a part of very complex mapping, it is important to label it properly and also to provide relevant comments.</span></span> <span data-ttu-id="997ae-111">您可以标记 functoid 和链接。</span><span class="sxs-lookup"><span data-stu-id="997ae-111">You can label both functoids and links.</span></span> <span data-ttu-id="997ae-112">有关如何标记链接的信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)。</span><span class="sxs-lookup"><span data-stu-id="997ae-112">For information on how to label a link, see [How to Label a Link](../core/how-to-label-a-link.md).</span></span>  
  
 <span data-ttu-id="997ae-113">您可以通过以下方法标记和注释 functoid：</span><span class="sxs-lookup"><span data-stu-id="997ae-113">You can label and comment a functoid in the following ways:</span></span>  
  
-   <span data-ttu-id="997ae-114">通过使用**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="997ae-114">By using the **Configure \<Functoid\> Functoid** dialog box.</span></span>  
  
-   <span data-ttu-id="997ae-115">通过使用**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="997ae-115">By using the **Properties** window.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="997ae-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="997ae-116">Prerequisites</span></span>  
 <span data-ttu-id="997ae-117">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="997ae-117">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-label-and-comment-a-functoid-from-configure-dialog-box"></a><span data-ttu-id="997ae-118">从“配置”对话框标记和注释 functoid</span><span class="sxs-lookup"><span data-stu-id="997ae-118">To label and comment a functoid from Configure dialog box</span></span>  
  
1.  <span data-ttu-id="997ae-119">右键单击你希望标签和注释，，然后单击 functoid**配置 Functoid 输入**。</span><span class="sxs-lookup"><span data-stu-id="997ae-119">Right-click the functoid you want to label and comment, and then click **Configure Functoid Inputs**.</span></span>  
  
2.  <span data-ttu-id="997ae-120">在**配置\<Functoid\> Functoid**对话框中，单击**标签和注释**选项卡。</span><span class="sxs-lookup"><span data-stu-id="997ae-120">In the **Configure \<Functoid\> Functoid** dialog box, click the **Label and Comments** tab.</span></span>  
  
3.  <span data-ttu-id="997ae-121">输入以下信息，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="997ae-121">Enter the following information, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="997ae-122">**标签 –** 输入新名称。</span><span class="sxs-lookup"><span data-stu-id="997ae-122">**Label –** Enter the new name.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="997ae-123">最大允许的字符数为 256。</span><span class="sxs-lookup"><span data-stu-id="997ae-123">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="997ae-124">如果指定超过 256 个字符的字符串，则接受前 256 个字符和其余部分将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="997ae-124">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
    -   <span data-ttu-id="997ae-125">**注释 –** functoid 输入的备注。</span><span class="sxs-lookup"><span data-stu-id="997ae-125">**Comments –** Enter the comments for the functoid.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="997ae-126">最大允许的字符数为 1024年。</span><span class="sxs-lookup"><span data-stu-id="997ae-126">The maximum number of characters allowed is 1024.</span></span> <span data-ttu-id="997ae-127">如果指定超过 1024年个字符的字符串，则接受首先 1024年个字符，并丢弃其余部分。</span><span class="sxs-lookup"><span data-stu-id="997ae-127">If a string with more than 1024 characters is specified, the first 1024 characters are accepted and the rest are discarded.</span></span>  
  
### <a name="to-label-and-comment-a-functoid-from-properties-window"></a><span data-ttu-id="997ae-128">从“属性”窗口为 functoid 添加标签和注释</span><span class="sxs-lookup"><span data-stu-id="997ae-128">To label and comment a functoid from Properties window</span></span>  
  
1.  <span data-ttu-id="997ae-129">选择要添加标记和注释的 functoid。</span><span class="sxs-lookup"><span data-stu-id="997ae-129">Select the functoid you want to label and comment.</span></span>  
  
2.  <span data-ttu-id="997ae-130">在**属性**窗口中，输入以下信息，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="997ae-130">In the **Properties** window, enter the following information, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="997ae-131">**标签 –** 输入新名称。</span><span class="sxs-lookup"><span data-stu-id="997ae-131">**Label –** Enter the new name.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="997ae-132">最大允许的字符数为 256。</span><span class="sxs-lookup"><span data-stu-id="997ae-132">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="997ae-133">如果指定超过 256 个字符的字符串，则接受前 256 个字符和其余部分将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="997ae-133">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
    -   <span data-ttu-id="997ae-134">**注释 –** functoid 输入的备注。</span><span class="sxs-lookup"><span data-stu-id="997ae-134">**Comments –** Enter the comments for the functoid.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="997ae-135">最大允许的字符数为 1024年。</span><span class="sxs-lookup"><span data-stu-id="997ae-135">The maximum number of characters allowed is 1024.</span></span> <span data-ttu-id="997ae-136">如果指定超过 1024年个字符的字符串，则接受首先 1024年个字符，并丢弃其余部分。</span><span class="sxs-lookup"><span data-stu-id="997ae-136">If a string with more than 1024 characters is specified, the first 1024 characters are accepted and the rest are discarded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="997ae-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="997ae-137">See Also</span></span>  
 [<span data-ttu-id="997ae-138">编辑 Functoid 属性和输入参数</span><span class="sxs-lookup"><span data-stu-id="997ae-138">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)