---
title: 步骤 2： 创建适用于 V2.4 的通用架构 |Microsoft Docs
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
ms.openlocfilehash: 0b19d735a792fff91197eb0336501264c6e9c772
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995798"
---
# <a name="step-2-create-common-schemas-for-v24"></a><span data-ttu-id="05ac6-102">步骤 2： 创建适用于 V2.4 的通用架构</span><span class="sxs-lookup"><span data-stu-id="05ac6-102">Step 2: Create Common Schemas for V2.4</span></span>
<span data-ttu-id="05ac6-103">于 V2.4 架构是通常引用的架构，用于验证查询和响应消息实例。</span><span class="sxs-lookup"><span data-stu-id="05ac6-103">The V2.4 schemas are commonly referenced schemas, which you use to validate the query and response message instances.</span></span>  
  
### <a name="to-create-the-common-schemas-for-v24"></a><span data-ttu-id="05ac6-104">若要创建适用于 V2.4 的通用架构</span><span class="sxs-lookup"><span data-stu-id="05ac6-104">To create the common schemas for V2.4</span></span>  
  
1. <span data-ttu-id="05ac6-105">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="05ac6-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="05ac6-106">在新建项目对话框中，在**项目类型**列表中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。</span><span class="sxs-lookup"><span data-stu-id="05ac6-106">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="05ac6-107">在中**模板**列表中，选择**BTAHL7V24Common 项目**。</span><span class="sxs-lookup"><span data-stu-id="05ac6-107">In the **Templates** list, select **BTAHL7V24Common Project**.</span></span>  
  
4. <span data-ttu-id="05ac6-108">在中**名称**字段中，键入**Interrogative_24Schemas**。</span><span class="sxs-lookup"><span data-stu-id="05ac6-108">In the **Name** field, type **Interrogative_24Schemas**.</span></span>  
  
5. <span data-ttu-id="05ac6-109">在解决方案字段中，选择**将添加到解决方案**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="05ac6-109">In the Solution field, select **Add to Solution**, and then click **OK**.</span></span>  
  
    <span data-ttu-id="05ac6-110">在解决方案资源管理器，请注意，在项目中包含三个架构 （datatypes_24.xsd、 segments_24.xsd 和 tablevalues_24.xsd）。</span><span class="sxs-lookup"><span data-stu-id="05ac6-110">In Solution Explorer, notice that three schemas (datatypes_24.xsd, segments_24.xsd, and tablevalues_24.xsd) are included in the project.</span></span>  
  
6. <span data-ttu-id="05ac6-111">在解决方案资源管理器中右键单击**Interrogative_24Schemas**项目，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="05ac6-111">In Solution Explorer, right-click **Interrogative_24Schemas** project,and then click **Properties**.</span></span>  
  
7. <span data-ttu-id="05ac6-112">在 Interrogative_24Schemas 属性页对话框中，单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="05ac6-112">In the Interrogative_24Schemas Property Pages dialog box, click **Assembly**.</span></span>  
  
8. <span data-ttu-id="05ac6-113">在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="05ac6-113">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
9. <span data-ttu-id="05ac6-114">在中**程序集密钥文件**对话框中，浏览到\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\ 的快捷键询问教程中，单击**key.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="05ac6-114">In the **Assembly Key File** dialog box, browse to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
10. <span data-ttu-id="05ac6-115">在 Interrogative_24Schemas 属性页对话框中，单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="05ac6-115">In the Interrogative_24Schemas Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
11. <span data-ttu-id="05ac6-116">在解决方案资源管理器中右键单击**Interrogative_24Schemas**项目，并单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="05ac6-116">In Solution Explorer, right-click **Interrogative_24Schemas** project, and then click **Deploy**.</span></span> <span data-ttu-id="05ac6-117">单击**确定**到对话框，询问您要将更改保存到解决方案。</span><span class="sxs-lookup"><span data-stu-id="05ac6-117">Click **OK** to the dialog box asking you to save changes to the solution.</span></span> <span data-ttu-id="05ac6-118">请确保在输出窗口中将显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="05ac6-118">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05ac6-119">如果未显示正确的消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决您的架构。</span><span class="sxs-lookup"><span data-stu-id="05ac6-119">If the correct message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
    <span data-ttu-id="05ac6-120">请继续执行[步骤 3： 创建和部署触发器事件 （消息） 项目](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)。</span><span class="sxs-lookup"><span data-stu-id="05ac6-120">Proceed to [Step 3: Create and Deploy a Trigger Event (Message) Project](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md).</span></span>