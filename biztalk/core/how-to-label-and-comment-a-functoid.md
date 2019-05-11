---
title: 如何标签和注释 Functoid |Microsoft Docs
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
ms.openlocfilehash: db30ca1b7bee06c633245e05808ad521b27e51d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384867"
---
# <a name="how-to-label-and-comment-a-functoid"></a><span data-ttu-id="54c74-102">如何标签和注释 Functoid</span><span class="sxs-lookup"><span data-stu-id="54c74-102">How to Label and Comment a Functoid</span></span>
<span data-ttu-id="54c74-103">标签和注释有助于记录 functoid 或映射中的链接的用途。</span><span class="sxs-lookup"><span data-stu-id="54c74-103">Labels and comments are helpful to document the purpose of a functoid or a link in a map.</span></span> <span data-ttu-id="54c74-104">可以使用**标签**属性为 functoid 提供一个名称。</span><span class="sxs-lookup"><span data-stu-id="54c74-104">You can use the **Label** property to provide a name for a functoid.</span></span> <span data-ttu-id="54c74-105">**注释**属性使您能够提供有关该 functoid，有关它所执行的操作通常相关信息的其他信息。</span><span class="sxs-lookup"><span data-stu-id="54c74-105">The **Comments** property enables you to provide additional information about the functoid, typically relevant information about the operation being performed by it.</span></span>  
  
 <span data-ttu-id="54c74-106">下图显示的标签和注释 functoid 的。</span><span class="sxs-lookup"><span data-stu-id="54c74-106">The following figure shows the label and comments for a functoid.</span></span> <span data-ttu-id="54c74-107">该 functoid 将源架构中添加两个输入 （Field1 和 Field3），并将结果输出到 Field4 目标架构中。</span><span class="sxs-lookup"><span data-stu-id="54c74-107">The functoid adds two inputs (Field1 and Field3) from the source schema and outputs the result to Field4 in the target schema.</span></span> <span data-ttu-id="54c74-108">在此示例中，functoid 标签是"Add Field1 and Field3"，注释是"The addition is an output to Field4"。</span><span class="sxs-lookup"><span data-stu-id="54c74-108">In this example, the functoid label is “Add Field1 and Field3” and the comment is “The addition is an output to Field4”.</span></span>  
  
 <span data-ttu-id="54c74-109">![插入 functoid 标签和注释](../core/media/label.gif "Label_")</span><span class="sxs-lookup"><span data-stu-id="54c74-109">![Inserting functoid labels and comments](../core/media/label.gif "Label_")</span></span>  
  
 <span data-ttu-id="54c74-110">因为 functoid 可能是非常复杂的映射的一部分，很重要，所以适当地标记和另外提供相关注释。</span><span class="sxs-lookup"><span data-stu-id="54c74-110">Because a functoid can be a part of very complex mapping, it is important to label it properly and also to provide relevant comments.</span></span> <span data-ttu-id="54c74-111">可以标记 functoid 和链接。</span><span class="sxs-lookup"><span data-stu-id="54c74-111">You can label both functoids and links.</span></span> <span data-ttu-id="54c74-112">有关如何标记链接的信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)。</span><span class="sxs-lookup"><span data-stu-id="54c74-112">For information on how to label a link, see [How to Label a Link](../core/how-to-label-a-link.md).</span></span>  
  
 <span data-ttu-id="54c74-113">可以标记和注释 functoid 按以下方式：</span><span class="sxs-lookup"><span data-stu-id="54c74-113">You can label and comment a functoid in the following ways:</span></span>  
  
-   <span data-ttu-id="54c74-114">通过使用**配置\<Functoid\> Functoid**对话框。</span><span class="sxs-lookup"><span data-stu-id="54c74-114">By using the **Configure \<Functoid\> Functoid** dialog box.</span></span>  
  
-   <span data-ttu-id="54c74-115">通过使用**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="54c74-115">By using the **Properties** window.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="54c74-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="54c74-116">Prerequisites</span></span>  
 <span data-ttu-id="54c74-117">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="54c74-117">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-label-and-comment-a-functoid-from-configure-dialog-box"></a><span data-ttu-id="54c74-118">添加标记和注释 functoid 从配置对话框</span><span class="sxs-lookup"><span data-stu-id="54c74-118">To label and comment a functoid from Configure dialog box</span></span>  
  
1.  <span data-ttu-id="54c74-119">右键单击您要添加标记和注释，然后单击该 functoid**配置 Functoid 输入**。</span><span class="sxs-lookup"><span data-stu-id="54c74-119">Right-click the functoid you want to label and comment, and then click **Configure Functoid Inputs**.</span></span>  
  
2.  <span data-ttu-id="54c74-120">在中**配置\<Functoid\> Functoid**对话框中，单击**标签和注释**选项卡。</span><span class="sxs-lookup"><span data-stu-id="54c74-120">In the **Configure \<Functoid\> Functoid** dialog box, click the **Label and Comments** tab.</span></span>  
  
3.  <span data-ttu-id="54c74-121">输入以下信息，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="54c74-121">Enter the following information, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="54c74-122">**标签-** 输入新名称。</span><span class="sxs-lookup"><span data-stu-id="54c74-122">**Label –** Enter the new name.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="54c74-123">最大允许的字符数为 256。</span><span class="sxs-lookup"><span data-stu-id="54c74-123">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="54c74-124">如果指定超过 256 个字符的字符串，则接受前 256 个字符，并丢弃剩余部分。</span><span class="sxs-lookup"><span data-stu-id="54c74-124">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
    -   <span data-ttu-id="54c74-125">**注释-** functoid 输入注释。</span><span class="sxs-lookup"><span data-stu-id="54c74-125">**Comments –** Enter the comments for the functoid.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="54c74-126">最大允许的字符数为 1024年。</span><span class="sxs-lookup"><span data-stu-id="54c74-126">The maximum number of characters allowed is 1024.</span></span> <span data-ttu-id="54c74-127">如果指定超过 1024年个字符的字符串，则接受前面 1024 个字符，并丢弃剩余部分。</span><span class="sxs-lookup"><span data-stu-id="54c74-127">If a string with more than 1024 characters is specified, the first 1024 characters are accepted and the rest are discarded.</span></span>  
  
### <a name="to-label-and-comment-a-functoid-from-properties-window"></a><span data-ttu-id="54c74-128">添加标记和注释 functoid 从属性窗口</span><span class="sxs-lookup"><span data-stu-id="54c74-128">To label and comment a functoid from Properties window</span></span>  
  
1.  <span data-ttu-id="54c74-129">选择要添加标记和注释的 functoid。</span><span class="sxs-lookup"><span data-stu-id="54c74-129">Select the functoid you want to label and comment.</span></span>  
  
2.  <span data-ttu-id="54c74-130">在中**属性**窗口中，输入以下信息，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="54c74-130">In the **Properties** window, enter the following information, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="54c74-131">**标签-** 输入新名称。</span><span class="sxs-lookup"><span data-stu-id="54c74-131">**Label –** Enter the new name.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="54c74-132">最大允许的字符数为 256。</span><span class="sxs-lookup"><span data-stu-id="54c74-132">The maximum number of characters allowed is 256.</span></span> <span data-ttu-id="54c74-133">如果指定超过 256 个字符的字符串，则接受前 256 个字符，并丢弃剩余部分。</span><span class="sxs-lookup"><span data-stu-id="54c74-133">If a string with more than 256 characters is specified, the first 256 characters are accepted and the rest are discarded.</span></span>  
  
    -   <span data-ttu-id="54c74-134">**注释-** functoid 输入注释。</span><span class="sxs-lookup"><span data-stu-id="54c74-134">**Comments –** Enter the comments for the functoid.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="54c74-135">最大允许的字符数为 1024年。</span><span class="sxs-lookup"><span data-stu-id="54c74-135">The maximum number of characters allowed is 1024.</span></span> <span data-ttu-id="54c74-136">如果指定超过 1024年个字符的字符串，则接受前面 1024 个字符，并丢弃剩余部分。</span><span class="sxs-lookup"><span data-stu-id="54c74-136">If a string with more than 1024 characters is specified, the first 1024 characters are accepted and the rest are discarded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c74-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="54c74-137">See Also</span></span>  
 [<span data-ttu-id="54c74-138">编辑 Functoid 属性和输入参数</span><span class="sxs-lookup"><span data-stu-id="54c74-138">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)