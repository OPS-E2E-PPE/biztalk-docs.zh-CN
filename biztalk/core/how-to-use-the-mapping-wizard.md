---
title: 如何使用映射向导 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35b96cea-ead7-43de-8411-62d2c7d6620e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6b016eb0599924d4927868b6a19d3b57389e5c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257357"
---
# <a name="how-to-use-the-mapping-wizard"></a><span data-ttu-id="b68eb-102">如何使用映射向导</span><span class="sxs-lookup"><span data-stu-id="b68eb-102">How to Use the Mapping Wizard</span></span>
<span data-ttu-id="b68eb-103">此版本的企业单一登录包括了映射向导，可使用该向导为关联应用程序轻松创建映射。</span><span class="sxs-lookup"><span data-stu-id="b68eb-103">This version of Enterprise Single Sign-On includes the Mapping Wizard, which allows you to easily create mappings for affiliate applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b68eb-104">只有当外部 UserID 基于 Windows 域帐户时，才能使用映射向导。</span><span class="sxs-lookup"><span data-stu-id="b68eb-104">You can only use the Mapping Wizard if the External UserID is based on the Windows domain account.</span></span>  
  
### <a name="to-start-the-mapping-wizard"></a><span data-ttu-id="b68eb-105">若要启动映射向导</span><span class="sxs-lookup"><span data-stu-id="b68eb-105">To start the Mapping Wizard</span></span>  
  
1.  <span data-ttu-id="b68eb-106">打开企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="b68eb-106">Open Enterprise Single Sign-On.</span></span>  
  
2.  <span data-ttu-id="b68eb-107">在作用域窗格中，单击**Affiliate 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="b68eb-107">In the scope pane, click **Affiliate Applications**.</span></span>  
  
3.  <span data-ttu-id="b68eb-108">右键单击适当的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="b68eb-108">Right click the appropriate affiliate application.</span></span>  
  
4.  <span data-ttu-id="b68eb-109">单击**创建映射**。</span><span class="sxs-lookup"><span data-stu-id="b68eb-109">Click **Create Mappings**.</span></span> <span data-ttu-id="b68eb-110">将显示映射向导。</span><span class="sxs-lookup"><span data-stu-id="b68eb-110">The Mapping Wizard appears.</span></span>  
  
5.  <span data-ttu-id="b68eb-111">**欢迎使用映射向导**</span><span class="sxs-lookup"><span data-stu-id="b68eb-111">**Welcome to the Mapping Wizard**</span></span>  
  
    -   <span data-ttu-id="b68eb-112">验证这是正确的关联应用程序，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b68eb-112">Verify that this is the correct affiliate application, and click **Next**.</span></span>  
  
6.  <span data-ttu-id="b68eb-113">**映射文件选项**页</span><span class="sxs-lookup"><span data-stu-id="b68eb-113">**Mappings File Option** page</span></span>  
  
    -   <span data-ttu-id="b68eb-114">ENTSSO 通过一个 XML 文件来管理映射。</span><span class="sxs-lookup"><span data-stu-id="b68eb-114">ENTSSO manages mappings through an XML file.</span></span> <span data-ttu-id="b68eb-115">可以选择创建新文件或者使用现有文件。</span><span class="sxs-lookup"><span data-stu-id="b68eb-115">You can choose to create a new file or use an existing one.</span></span>  
  
7.  <span data-ttu-id="b68eb-116">**文件位置**页</span><span class="sxs-lookup"><span data-stu-id="b68eb-116">**Files Location** page</span></span>  
  
    -   <span data-ttu-id="b68eb-117">选择要使用的文件。</span><span class="sxs-lookup"><span data-stu-id="b68eb-117">Select the files to be used.</span></span>  
  
    -   <span data-ttu-id="b68eb-118">你必须单击**验证**验证在继续之前的文件。</span><span class="sxs-lookup"><span data-stu-id="b68eb-118">You must click **Validate** to validate the files before proceeding.</span></span> <span data-ttu-id="b68eb-119">验证状态会显示在**状态**窗口。</span><span class="sxs-lookup"><span data-stu-id="b68eb-119">The validation status appears in the **Status** window.</span></span>  
  
8.  <span data-ttu-id="b68eb-120">**帐户**页</span><span class="sxs-lookup"><span data-stu-id="b68eb-120">**Accounts** page</span></span>  
  
    -   <span data-ttu-id="b68eb-121">选择一个或多个要帐户生成新的映射文件中，然后单击**验证**。</span><span class="sxs-lookup"><span data-stu-id="b68eb-121">Choose one or more accounts to generate the new mappings file, and click **Validate**.</span></span>  
  
9. <span data-ttu-id="b68eb-122">**外部用户名称**页</span><span class="sxs-lookup"><span data-stu-id="b68eb-122">**External User Name** page</span></span>  
  
    -   <span data-ttu-id="b68eb-123">定义如何从 Windows 用户帐户生成外部用户名。</span><span class="sxs-lookup"><span data-stu-id="b68eb-123">Define how the external user name is generated from the Windows user account.</span></span> <span data-ttu-id="b68eb-124">在框中进行选择时，你可以看到如何名称都将显示在**示例**框。</span><span class="sxs-lookup"><span data-stu-id="b68eb-124">As you make selections in the boxes, you can see how the names will appear in the **Example** box.</span></span>  
  
10. <span data-ttu-id="b68eb-125">**生成**页</span><span class="sxs-lookup"><span data-stu-id="b68eb-125">**Generate** page</span></span>  
  
    -   <span data-ttu-id="b68eb-126">单击**启动**生成映射文件。</span><span class="sxs-lookup"><span data-stu-id="b68eb-126">Click **Start** to generate the mappings file.</span></span> <span data-ttu-id="b68eb-127">（在创建映射之前，您可以在下一页上根据需要查看或编辑该文件。）结果显示在下方的三个窗口中。</span><span class="sxs-lookup"><span data-stu-id="b68eb-127">(You will have an opportunity on the next page to view or edit the file as necessary before mappings are created.) Results are displayed in the three windows below.</span></span>  
  
    -   <span data-ttu-id="b68eb-128">**数**中所选帐户的映射是一个近似值，因为帐户可能嵌套在其他帐户。</span><span class="sxs-lookup"><span data-stu-id="b68eb-128">The **Number** of mappings in selected accounts is an approximation, because accounts may be nested in other accounts.</span></span>  
  
    -   <span data-ttu-id="b68eb-129">单击**查看日志文件**检查任何错误或警告可能已经发生的。</span><span class="sxs-lookup"><span data-stu-id="b68eb-129">Click **View Log File** to examine any errors or warnings that might have occurred.</span></span>  
  
11. <span data-ttu-id="b68eb-130">**选项**页</span><span class="sxs-lookup"><span data-stu-id="b68eb-130">**Options** page</span></span>  
  
    -   <span data-ttu-id="b68eb-131">您的文件已经创建。</span><span class="sxs-lookup"><span data-stu-id="b68eb-131">Your file has been created.</span></span> <span data-ttu-id="b68eb-132">单击**查看/编辑映射文件**必要。</span><span class="sxs-lookup"><span data-stu-id="b68eb-132">Click **View/Edit Mappings File** if desired.</span></span>  
  
    -   <span data-ttu-id="b68eb-133">单击**启用映射**如果你想要自动启用的映射。</span><span class="sxs-lookup"><span data-stu-id="b68eb-133">Click **Enable mappings** if you want the mappings to be automatically enabled.</span></span> <span data-ttu-id="b68eb-134">（如果不单击此选项，则必须手动启用它们。）</span><span class="sxs-lookup"><span data-stu-id="b68eb-134">(If you do not click this, you will have to enable them manually.)</span></span>  
  
    -   <span data-ttu-id="b68eb-135">单击**设置密码**自动设置这些映射的密码。</span><span class="sxs-lookup"><span data-stu-id="b68eb-135">Click **Set Password** to automatically set the password for these mappings.</span></span>  
  
12. <span data-ttu-id="b68eb-136">**创建**页</span><span class="sxs-lookup"><span data-stu-id="b68eb-136">**Create** page</span></span>  
  
    -   <span data-ttu-id="b68eb-137">在创建映射之前, 单击**视图映射文件**必要。</span><span class="sxs-lookup"><span data-stu-id="b68eb-137">Before creating the mappings, click **View Mappings File** if desired.</span></span>  
  
    -   <span data-ttu-id="b68eb-138">准备就绪后，单击**启动**执行映射操作。</span><span class="sxs-lookup"><span data-stu-id="b68eb-138">When you are ready, click **Start** to perform the mapping operation.</span></span> <span data-ttu-id="b68eb-139">您的状态显示在下方的三个框中。</span><span class="sxs-lookup"><span data-stu-id="b68eb-139">Your status is displayed in the three boxes below.</span></span>  
  
    -   <span data-ttu-id="b68eb-140">单击**查看日志文件**检查任何错误或警告可能已经发生的。</span><span class="sxs-lookup"><span data-stu-id="b68eb-140">Click **View Log File** to examine any errors or warnings that might have occurred.</span></span>  
  
13. <span data-ttu-id="b68eb-141">**完成映射向导屏幕**</span><span class="sxs-lookup"><span data-stu-id="b68eb-141">**Completing the Mapping Wizard screen**</span></span>  
  
14. <span data-ttu-id="b68eb-142">选择所需，任何选项，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="b68eb-142">Select any options desired, and then click **Finish**.</span></span>