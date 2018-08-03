---
title: 步骤 2： 创建 Contoso LOB 应用程序架构为价格与可用性项目使用 BizTalk 编辑器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOB schemas
ms.assetid: 70e26dc9-4299-4d30-8f8b-5cc3469a2025
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f899a6614ea5d5d28c555be1b39e72b5880fe3ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999326"
---
# <a name="step-2-creating-the-contoso-lob-application-schemas-for-the-price-and-availability-project-using-biztalk-editor"></a><span data-ttu-id="aa2b5-102">步骤 2： 创建 Contoso LOB 应用程序架构为价格与可用性项目使用 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="aa2b5-102">Step 2: Creating the Contoso LOB Application Schemas for the Price and Availability Project Using BizTalk Editor</span></span>
<span data-ttu-id="aa2b5-103">在此步骤中，将生成用于查询 Contoso ERP 系统中特定产品的价格与可用性的架构。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-103">In this step, you generate the schema to use to query the Contoso ERP system for the price and availability of a particular product.</span></span> <span data-ttu-id="aa2b5-104">通过使用 BizTalk server 的 Microsoft® SQL 适配器生成此架构。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-104">You generate this schema by using the Microsoft® SQL Adapter for BizTalk Server.</span></span>  

### <a name="to-update-the-sql-stored-procedure-for-schema-generation"></a><span data-ttu-id="aa2b5-105">更新 SQL 存储过程以生成架构</span><span class="sxs-lookup"><span data-stu-id="aa2b5-105">To update the SQL stored procedure for schema generation</span></span>  

1.  <span data-ttu-id="aa2b5-106">单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-106">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  

2.  <span data-ttu-id="aa2b5-107">在 Microsoft SQL Server Management Studio 中，展开**数据库**，展开**Contoso**，展开**可编程性**，然后展开**存储过程**.</span><span class="sxs-lookup"><span data-stu-id="aa2b5-107">In the Microsoft SQL Server Management Studio, expand **Databases**, expand **Contoso**, expand **Programmability**, and then expand **Stored Procedures**.</span></span>  

3.  <span data-ttu-id="aa2b5-108">右键单击**dbo。SP_GetInventoryForProductID**，然后单击**修改**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-108">Right-click **dbo.SP_GetInventoryForProductID**, and then click **Modify**.</span></span>  

4.  <span data-ttu-id="aa2b5-109">在查询窗口中，紧接在“for xml auto”后面插入逗号、空格和“xmldata”。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-109">In the query window, insert a comma, a space, and then "xmldata" immediately following "for xml auto".</span></span> <span data-ttu-id="aa2b5-110">该代码行应为如下所示：</span><span class="sxs-lookup"><span data-stu-id="aa2b5-110">The line of code should be the following:</span></span>  

    ```  
    for xml auto, xmldata  
    ```  

5.  <span data-ttu-id="aa2b5-111">单击**Execute**若要将所做的更改保存到存储过程。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-111">Click **Execute** to save the changes to the stored procedure.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="aa2b5-112">保持 Microsoft SQL Server Management Studio 为打开状态，以执行下一个过程。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-112">Leave the Microsoft SQL Server Management Studio open for the next procedure.</span></span>  

### <a name="to-create-the-contoso-price-and-availability-schema"></a><span data-ttu-id="aa2b5-113">创建 Contoso 价格与可用性架构</span><span class="sxs-lookup"><span data-stu-id="aa2b5-113">To create the Contoso Price and Availability schema</span></span>  

1. <span data-ttu-id="aa2b5-114">打开 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 中的 Contoso 解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-114">Open the Contoso solution in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  

2. <span data-ttu-id="aa2b5-115">在解决方案资源管理器中右键单击**ContosoPriceAndAvailability**项目，指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-115">In Solution Explorer, right-click the **ContosoPriceAndAvailability** project, point to **Add**, and then click **Add Generated Items**.</span></span>  

3. <span data-ttu-id="aa2b5-116">在添加生成的项对话框中，使用**添加适配器元数据**处于选中状态的左窗格中，单击**添加适配器元数据**在右窗格中，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-116">In the Add Generated Iems dialog box, with **Add Adapter Metadata** selected in the left pane, click **Add Adapter Metadata** in the right pane, and then click **Add**.</span></span>  

4. <span data-ttu-id="aa2b5-117">上**添加适配器向导**页上，选择**SQL**从列表中的已注册的适配器，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-117">On the **Add Adapter Wizard** page, select **SQL** from the list of registered adapters, and then click **Next**.</span></span>  

5. <span data-ttu-id="aa2b5-118">上**数据库信息**页上，单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-118">On the **Database Information** page, click **Set**.</span></span>  

6. <span data-ttu-id="aa2b5-119">在数据链接属性对话框中，在**选择或输入服务器名称**框中，键入**localhost**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-119">In the Data Link Properties dialog box, in the **Select or enter a server name** box, type **localhost**.</span></span> <span data-ttu-id="aa2b5-120">选择**使用 Windows NT 集成安全性**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-120">Select **Use Windows NT Integrated security**.</span></span> <span data-ttu-id="aa2b5-121">有关**选择在服务器上的数据库**，选择**Contoso**数据库从数据库列表。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-121">For **Select the database on the server**, select the **Contoso** database from the database list.</span></span> <span data-ttu-id="aa2b5-122">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-122">Click **OK**.</span></span>  

7. <span data-ttu-id="aa2b5-123">上**数据库信息**页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-123">On the **Database Information** page, click **Next**.</span></span>  

8. <span data-ttu-id="aa2b5-124">上**架构信息**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aa2b5-124">On the **Schema Information** page, do the following:</span></span>  


   |                <span data-ttu-id="aa2b5-125">使用此选项</span><span class="sxs-lookup"><span data-stu-id="aa2b5-125">Use this</span></span>                 |              <span data-ttu-id="aa2b5-126">执行的操作</span><span class="sxs-lookup"><span data-stu-id="aa2b5-126">To do this</span></span>              |
   |-----------------------------------------|--------------------------------------|
   |          <span data-ttu-id="aa2b5-127">**目标命名空间**</span><span class="sxs-lookup"><span data-stu-id="aa2b5-127">**Target namespace**</span></span>           | <span data-ttu-id="aa2b5-128">类型**<http://Contoso.com/Price>**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-128">Type **<http://Contoso.com/Price>**.</span></span> |
   |        <span data-ttu-id="aa2b5-129">**选择端口类型**</span><span class="sxs-lookup"><span data-stu-id="aa2b5-129">**Select the port type**</span></span>         |        <span data-ttu-id="aa2b5-130">选择**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-130">Select **Send port**.</span></span>         |
   | <span data-ttu-id="aa2b5-131">**请求文档根元素名称**</span><span class="sxs-lookup"><span data-stu-id="aa2b5-131">**Request document root element name**</span></span>  |      <span data-ttu-id="aa2b5-132">类型**rootPriceRequest**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-132">Type **rootPriceRequest**.</span></span>      |
   | <span data-ttu-id="aa2b5-133">**响应文档根元素名称**</span><span class="sxs-lookup"><span data-stu-id="aa2b5-133">**Response document root element name**</span></span> |     <span data-ttu-id="aa2b5-134">类型**rootPriceResponse**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-134">Type **rootPriceResponse**.</span></span>      |


9. <span data-ttu-id="aa2b5-135">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-135">Click **Next**.</span></span>  

10. <span data-ttu-id="aa2b5-136">上**语句类型信息**页上，选择**存储过程**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-136">On the **Statement type information** page, select **Stored Procedure**, and then click **Next**.</span></span>  

11. <span data-ttu-id="aa2b5-137">上**语句的信息**页上，对于**\<选择一个存储的过程\>**，选择**SP_GetInventoryForProductID**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-137">On the **Statement Information** page, for **\<Select a stored procedure\>**, select **SP_GetInventoryForProductID** from the drop-down list.</span></span> <span data-ttu-id="aa2b5-138">单击**Generate**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-138">Click **Generate**, and then click **Next**.</span></span>  

12. <span data-ttu-id="aa2b5-139">上**完成 SQL 传输架构生成向导**页上，单击**完成**将架构导入到 ContosoPriceAndAvailability BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-139">On the **Completing the SQL Transport Schema Generation Wizard** page, click **Finish** to import the schema into the ContosoPriceAndAvailability BizTalk project.</span></span>  

13. <span data-ttu-id="aa2b5-140">在解决方案资源管理器，右键单击生成的架构 (SQLService_Price.xsd)，单击**重命名**，然后键入**ContosoPriceAndAvailability.xsd**作为架构的新名称。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-140">In Solution Explorer, right-click the generated schema (SQLService_Price.xsd), click **Rename**, and type **ContosoPriceAndAvailability.xsd** as the new name for the schema.</span></span> <span data-ttu-id="aa2b5-141">单击 **“输入”**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-141">Click **Enter**.</span></span>  

14. <span data-ttu-id="aa2b5-142">在 ContosoPriceAndAvailability 架构的属性窗口中，设置**类型名称**属性设置为**ContosoPriceSchema**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-142">In the Properties window for the ContosoPriceAndAvailability schema, set the **Type Name** property to **ContosoPriceSchema**.</span></span>  

15. <span data-ttu-id="aa2b5-143">默认情况下[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]创建名为 BizTalk 业务流程**BizTalk Orchestration.odx**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-143">By default, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] creates a BizTalk orchestration named **BizTalk Orchestration.odx**.</span></span> <span data-ttu-id="aa2b5-144">右键单击此业务流程，然后依次**删除**因为不需要此业务流程。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-144">Right-click this orchestration, and then click **Delete** because you do not need this orchestration.</span></span> <span data-ttu-id="aa2b5-145">在弹出窗口，该值指示将永久删除该业务流程中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-145">In the popup indicating that the orchestration will be deleted permanently, click **OK**.</span></span>  

16. <span data-ttu-id="aa2b5-146">Microsoft SQL Server Management Studio 中删除`xmldata`谓词和逗号`SP_GetInventoryForProductID`存储过程，在上一步骤中，添加它，然后单击**Execute**。</span><span class="sxs-lookup"><span data-stu-id="aa2b5-146">In the Microsoft SQL Server Management Studio, remove the `xmldata` predicate and the comma from the `SP_GetInventoryForProductID` stored procedure that you added in the previous step, and then click **Execute**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="aa2b5-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa2b5-147">See Also</span></span>  
 [<span data-ttu-id="aa2b5-148">步骤 3：使用 BizTalk 映射器为价格和可用性项目创建 Contoso LOB 应用程序映射</span><span class="sxs-lookup"><span data-stu-id="aa2b5-148">Step 3: Creating the Contoso LOB Application Maps for the Price and Availability Project Using BizTalk Mapper</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-create-contoso-lob-application-map-for-price-and-availability-in-mapper.md)