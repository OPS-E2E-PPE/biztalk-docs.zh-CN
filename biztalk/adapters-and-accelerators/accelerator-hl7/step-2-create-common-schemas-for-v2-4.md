---
title: 步骤 2： 为 V2.4 创建通用架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, common schemas
ms.assetid: 333ae85a-a307-4ab1-97f4-4d7b986e91de
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60b199bcd350a3341640baa05b875347c4f04bb5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-create-common-schemas-for-v24"></a><span data-ttu-id="efc98-102">步骤 2： 为 V2.4 创建通用架构</span><span class="sxs-lookup"><span data-stu-id="efc98-102">Step 2: Create Common Schemas for V2.4</span></span>
<span data-ttu-id="efc98-103">V2.4 架构是经常引用的架构，用于验证查询和响应消息实例。</span><span class="sxs-lookup"><span data-stu-id="efc98-103">The V2.4 schemas are commonly referenced schemas, which you use to validate the query and response message instances.</span></span>  
  
### <a name="to-create-the-common-schemas-for-v24"></a><span data-ttu-id="efc98-104">若要为 V2.4 创建通用架构</span><span class="sxs-lookup"><span data-stu-id="efc98-104">To create the common schemas for V2.4</span></span>  
  
1.  <span data-ttu-id="efc98-105">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="efc98-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="efc98-106">在新建项目对话框中，在**项目类型**列表中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。</span><span class="sxs-lookup"><span data-stu-id="efc98-106">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="efc98-107">在**模板**列表中，选择**BTAHL7V24Common 项目**。</span><span class="sxs-lookup"><span data-stu-id="efc98-107">In the **Templates** list, select **BTAHL7V24Common Project**.</span></span>  
  
4.  <span data-ttu-id="efc98-108">在**名称**字段中，键入**Interrogative_24Schemas**。</span><span class="sxs-lookup"><span data-stu-id="efc98-108">In the **Name** field, type **Interrogative_24Schemas**.</span></span>  
  
5.  <span data-ttu-id="efc98-109">在解决方案字段中，选择**将添加到解决方案**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="efc98-109">In the Solution field, select **Add to Solution**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="efc98-110">在解决方案资源管理器，请注意，在项目中包含三个架构 （datatypes_24.xsd、 segments_24.xsd 和 tablevalues_24.xsd）。</span><span class="sxs-lookup"><span data-stu-id="efc98-110">In Solution Explorer, notice that three schemas (datatypes_24.xsd, segments_24.xsd, and tablevalues_24.xsd) are included in the project.</span></span>  
  
6.  <span data-ttu-id="efc98-111">在解决方案资源管理器，右键单击**Interrogative_24Schemas**项目，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="efc98-111">In Solution Explorer, right-click **Interrogative_24Schemas** project,and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="efc98-112">在 Interrogative_24Schemas 属性页对话框中，单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="efc98-112">In the Interrogative_24Schemas Property Pages dialog box, click **Assembly**.</span></span>  
  
8.  <span data-ttu-id="efc98-113">在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="efc98-113">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
9. <span data-ttu-id="efc98-114">在**程序集密钥文件**对话框中，浏览到\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\ 快捷键Interrogative 教程，则单击**key.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="efc98-114">In the **Assembly Key File** dialog box, browse to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="efc98-115">在 Interrogative_24Schemas 属性页对话框中，单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="efc98-115">In the Interrogative_24Schemas Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
11. <span data-ttu-id="efc98-116">在解决方案资源管理器，右键单击**Interrogative_24Schemas**项目，，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="efc98-116">In Solution Explorer, right-click **Interrogative_24Schemas** project, and then click **Deploy**.</span></span> <span data-ttu-id="efc98-117">单击**确定**到对话框，询问你要将更改保存到解决方案。</span><span class="sxs-lookup"><span data-stu-id="efc98-117">Click **OK** to the dialog box asking you to save changes to the solution.</span></span> <span data-ttu-id="efc98-118">确保输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="efc98-118">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="efc98-119">如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决你的架构。</span><span class="sxs-lookup"><span data-stu-id="efc98-119">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="efc98-120">继续执行[步骤 3： 创建和部署的触发器事件 （消息） 项目](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)。</span><span class="sxs-lookup"><span data-stu-id="efc98-120">Proceed to [Step 3: Create and Deploy a Trigger Event (Message) Project](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md).</span></span>