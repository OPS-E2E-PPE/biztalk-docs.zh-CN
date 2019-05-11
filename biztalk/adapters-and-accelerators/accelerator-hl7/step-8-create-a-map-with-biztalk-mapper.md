---
title: 步骤 8：与 BizTalk 映射器创建映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, maps
- creating, maps
- maps, creating
- BizTalk Mapper
ms.assetid: 785426c7-5651-48be-b3f4-7f9d8051ba23
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 973dde183178be48feeea2613c0cf6964c9f3efa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287864"
---
# <a name="step-8-create-a-map-with-biztalk-mapper"></a><span data-ttu-id="0f86b-102">步骤 8：与 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="0f86b-102">Step 8: Create a Map with BizTalk Mapper</span></span>
<span data-ttu-id="0f86b-103">在此步骤中，使用 BizTalk 映射器创建映射。</span><span class="sxs-lookup"><span data-stu-id="0f86b-103">In this step, you use the BizTalk Mapper to create a map.</span></span> <span data-ttu-id="0f86b-104">就使用此映射来创建将数据 （字段） 相关联的链接请求被拒绝文档中的数据中的补货请求文档中。</span><span class="sxs-lookup"><span data-stu-id="0f86b-104">You use this map to create links that associate the data (fields) in a replenishment request document to the data in a request denied document.</span></span>  
  
### <a name="to-create-a-map"></a><span data-ttu-id="0f86b-105">若要创建映射</span><span class="sxs-lookup"><span data-stu-id="0f86b-105">To create a map</span></span>  
  
1. <span data-ttu-id="0f86b-106">在解决方案资源管理器中右键单击**BTAHL7 项目**，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="0f86b-106">In Solution Explorer, right-click **BTAHL7 Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2. <span data-ttu-id="0f86b-107">在中**添加新项**对话框中**类别**窗格中，单击**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="0f86b-107">In the **Add New Item** dialog box, in the **Categories** pane, click **Map Files**.</span></span>  
  
3. <span data-ttu-id="0f86b-108">在中**名称**字段中，键入**DoorbellMap**以该映射，然后单击**添加**启动 BizTalk 映射器。</span><span class="sxs-lookup"><span data-stu-id="0f86b-108">In the **Name** field, type **DoorbellMap** to name the map, and then click **Add** to start BizTalk Mapper.</span></span>  
  
4. <span data-ttu-id="0f86b-109">在中**源架构**窗格 （左侧），单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="0f86b-109">In the **Source Schema** pane (left side), click **Open Source Schema**.</span></span>  
  
5. <span data-ttu-id="0f86b-110">在 BizTalk 类型选取器对话框中，展开**BTAHL7 项目**，展开**架构**，单击**BTAHL7_Project.Doorbell**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="0f86b-110">In the BizTalk Type Picker dialog box, expand **BTAHL7 Project**, expand **Schemas**, click **BTAHL7_Project.Doorbell**, and then click **OK**.</span></span>  
  
6. <span data-ttu-id="0f86b-111">在中**目标架构**窗格 （右侧），单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="0f86b-111">In the **Destination Schema** pane (right side), click **Open Destination Schema**.</span></span>  
  
7. <span data-ttu-id="0f86b-112">在 BizTalk 类型选取器中，展开**BTAHL7 项目**，展开**架构**，单击**BTAHL7Schemas.ADT_A04_22_GLO_DEF**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="0f86b-112">In the BizTalk Type Picker, expand **BTAHL7 Project**, expand **Schemas**, click **BTAHL7Schemas.ADT_A04_22_GLO_DEF**, and then click **OK**.</span></span>  
  
8. <span data-ttu-id="0f86b-113">在中**目标架构**窗格 （右侧），展开**ADT_A04_22_GLO_DEF**，展开**PID_PatientIdentification**，然后展开**PID.5_PatientName**.</span><span class="sxs-lookup"><span data-stu-id="0f86b-113">In the **Destination Schema** pane (right side), expand **ADT_A04_22_GLO_DEF**, expand **PID_PatientIdentification**, and expand **PID.5_PatientName**.</span></span>  
  
9. <span data-ttu-id="0f86b-114">在中**源架构**窗格 （左侧），展开**DoorbellRoot**。</span><span class="sxs-lookup"><span data-stu-id="0f86b-114">In the **Source Schema** pane (left side), expand **DoorbellRoot**.</span></span> <span data-ttu-id="0f86b-115">拖动**LastName**字段**PN_0_FamilyName**字段中**目标架构**窗格。</span><span class="sxs-lookup"><span data-stu-id="0f86b-115">Drag the **LastName** field to the **PN_0_FamilyName** field in the **Destination Schema** pane.</span></span>  
  
10. <span data-ttu-id="0f86b-116">在中**源架构**窗格中，拖动**FirstName**字段**PN_1_GivenName**字段中**目标架构**窗格。</span><span class="sxs-lookup"><span data-stu-id="0f86b-116">In the **Source Schema** pane, drag the **FirstName** field to the **PN_1_GivenName** field in the **Destination Schema** pane.</span></span>  
  
11. <span data-ttu-id="0f86b-117">在中**源架构**窗格中，拖动**MiddleName**字段**PN_2_MiddleInitialOrName**字段中**目标架构**窗格.</span><span class="sxs-lookup"><span data-stu-id="0f86b-117">In the **Source Schema** pane, drag the **MiddleName** field to the **PN_2_MiddleInitialOrName** field in the **Destination Schema** pane.</span></span>  
  
12. <span data-ttu-id="0f86b-118">在中**目标架构**窗格中，展开**PID_3_PatientIdInternalId**。</span><span class="sxs-lookup"><span data-stu-id="0f86b-118">In the **Destination Schema** pane, expand **PID_3_PatientIdInternalId**.</span></span>  
  
13. <span data-ttu-id="0f86b-119">在中**源架构**窗格中，拖动**SSN**字段**CM_PAT_ID_0_PatientID**中**目标架构**窗格。</span><span class="sxs-lookup"><span data-stu-id="0f86b-119">In the **Source Schema** pane, drag the **SSN** field to the **CM_PAT_ID_0_PatientID** in the **Destination Schema** pane.</span></span>  
  
14. <span data-ttu-id="0f86b-120">在中**文件**菜单上，单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="0f86b-120">In the **File** menu, click **Save All**.</span></span>  
  
    <span data-ttu-id="0f86b-121">在典型的消息扩充方案中，如果任何患者信息已丢失，则会调用患者记录数据库中您的业务流程和添加缺少的信息，然后使用的其他信息以完成映射。</span><span class="sxs-lookup"><span data-stu-id="0f86b-121">In a typical message enrichment scenario, if any patient information were missing, you would make a call to a Patient Records database in your orchestration and add the missing information, then use the additional information to complete the mapping.</span></span> <span data-ttu-id="0f86b-122">例如，由于入站的 XML 门铃触发器事件消息未提供，因此可能会从患者记录数据库中，检索患者的家庭地址。</span><span class="sxs-lookup"><span data-stu-id="0f86b-122">For example, you might retrieve the home address of a patient from the Patient Records database, since the inbound XML doorbell trigger event message did not provide it.</span></span>  
  
    <span data-ttu-id="0f86b-123">请继续执行[步骤 9:验证并生成映射项目](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)。</span><span class="sxs-lookup"><span data-stu-id="0f86b-123">Proceed to [Step 9: Validate and Build the Map Project](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f86b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f86b-124">See Also</span></span>  
 [<span data-ttu-id="0f86b-125">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="0f86b-125">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)