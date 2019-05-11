---
title: 创建新的消息模板 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, templates
- templates, creating
- creating, templates
ms.assetid: 8c601d2b-b7a5-4ac4-9d98-fd9960038340
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cdd76cf788447aa496ac986c9ed9a287958f3b5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378517"
---
# <a name="creating-a-new-message-template"></a><span data-ttu-id="f9d36-102">创建新的消息模板</span><span class="sxs-lookup"><span data-stu-id="f9d36-102">Creating a New Message Template</span></span>
<span data-ttu-id="f9d36-103">可以通过现有模板创建新的消息模板。</span><span class="sxs-lookup"><span data-stu-id="f9d36-103">You can create a new message template from an existing template.</span></span> <span data-ttu-id="f9d36-104">这使自定义窗体，如一份已向其中输入一些数据的标准 SWIFT 窗体上创建新的消息实例的创建者。</span><span class="sxs-lookup"><span data-stu-id="f9d36-104">This enables a creator to create a new message instance on a custom form, such as a copy of a standard SWIFT form that already has some data entered into it.</span></span> <span data-ttu-id="f9d36-105">使用新的模板，创建者无需输入所有所需使用一个空窗体时的数据。</span><span class="sxs-lookup"><span data-stu-id="f9d36-105">Using the new template, the creator does not have to enter all of the data required when using an empty form.</span></span>  
  
 <span data-ttu-id="f9d36-106">从具有使用相应的现有模板生成的消息实例创建一个新的模板。</span><span class="sxs-lookup"><span data-stu-id="f9d36-106">You create a new template from a message instance that you have generated using the corresponding existing template.</span></span> <span data-ttu-id="f9d36-107">将数据添加到字段的[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中 （如同你已创建新的消息实例），，然后将窗体保存为新模板。</span><span class="sxs-lookup"><span data-stu-id="f9d36-107">You add data to the fields of the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form (as though you were creating a new message instance), and then save the form as a new template.</span></span>  
  
### <a name="to-save-a-modified-existing-template-as-a-new-template"></a><span data-ttu-id="f9d36-108">若要将已修改的现有模板另存为新的模板</span><span class="sxs-lookup"><span data-stu-id="f9d36-108">To save a modified existing template as a new template</span></span>  
  
1. <span data-ttu-id="f9d36-109">在 Internet Explorer 中，打开你的 MRSR 站点置于 http://localhost/sites/bassite 。</span><span class="sxs-lookup"><span data-stu-id="f9d36-109">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  
  
2. <span data-ttu-id="f9d36-110">单击 **“文档”**。</span><span class="sxs-lookup"><span data-stu-id="f9d36-110">Click **Documents**.</span></span>  
  
3. <span data-ttu-id="f9d36-111">在文档页上，单击**新 SWIFT MT 消息**文档库。</span><span class="sxs-lookup"><span data-stu-id="f9d36-111">On the Documents page, click the **New SWIFT MT Messages** document library.</span></span>  
  
4. <span data-ttu-id="f9d36-112">在新 SWIFT MT 消息页上，单击包含你想要使新模板基于模板的类别。</span><span class="sxs-lookup"><span data-stu-id="f9d36-112">On the New SWIFT MT Messages page, click the category containing the template that you want to base your new template on.</span></span>  
  
5. <span data-ttu-id="f9d36-113">指向你想要你的新模板基础，单击右侧的箭头，然后单击该模板**在 Microsoft Office InfoPath 中编辑**。</span><span class="sxs-lookup"><span data-stu-id="f9d36-113">Point to the template that you want to base your new template on, click the arrow to the right, and then click **Edit in Microsoft Office InfoPath**.</span></span>  
  
6. <span data-ttu-id="f9d36-114">在[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]2007年窗口中，在消息表单中，输入你想要将模板的一部分的消息数据。</span><span class="sxs-lookup"><span data-stu-id="f9d36-114">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, in the message form, enter message data that you want to be part of the template.</span></span>  
  
7. <span data-ttu-id="f9d36-115">单击**文件**，然后单击**另存为**。</span><span class="sxs-lookup"><span data-stu-id="f9d36-115">Click **File**, and then click **Save As**.</span></span>  
  
8. <span data-ttu-id="f9d36-116">在弹出窗口，该值指示窗体包含验证错误，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="f9d36-116">In the popup indicating that the form contains validation errors, click **Yes**.</span></span>  
  
9. <span data-ttu-id="f9d36-117">在另存为对话框中，选择的文件夹中的模板**将保存在**文本框中，并输入中的文件名**文件名**文本框。</span><span class="sxs-lookup"><span data-stu-id="f9d36-117">In the Save As dialog box, select the folder for the template in the **Save in** text box, and then enter a file name in the **File name** text box.</span></span> <span data-ttu-id="f9d36-118">单击“保存” 。</span><span class="sxs-lookup"><span data-stu-id="f9d36-118">Click **Save**.</span></span>  
  
10. <span data-ttu-id="f9d36-119">关闭[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]新模板的窗体。</span><span class="sxs-lookup"><span data-stu-id="f9d36-119">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form for the new template.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9d36-120">若要从新的模板创建消息实例，请参阅[创建和提交新消息](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)。</span><span class="sxs-lookup"><span data-stu-id="f9d36-120">To create a message instance from the new template, see [Creating and Submitting a New Message](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md).</span></span>