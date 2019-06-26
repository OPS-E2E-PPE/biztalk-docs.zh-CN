---
title: 演练：使用数据库和.NET 事实 |Microsoft Docs
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 676d6e46-d9f8-477e-979e-1ac051ad4451
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 453d7e657c2e2a416729a68700098be9b69a3a86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395959"
---
# <a name="walkthrough-using-database-and-net-facts"></a><span data-ttu-id="a4d8f-102">演练：使用数据库和.NET 事实</span><span class="sxs-lookup"><span data-stu-id="a4d8f-102">Walkthrough: Using Database and .NET Facts</span></span>
<span data-ttu-id="a4d8f-103">本演练提供使用业务规则编辑器来创建使用数据库和.NET 事实的策略的分步过程。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-103">This walkthrough provides step-by-step procedures for using the Business Rule Composer to create a policy that uses database and .NET facts.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="a4d8f-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="a4d8f-104">Prerequisites</span></span>  
 <span data-ttu-id="a4d8f-105">必须设置的值**StaticSupport**为 1 或 2 才能执行本演练的注册表项。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-105">You must set the value of the **StaticSupport** registry key to 1 or 2 before performing the walkthrough.</span></span> <span data-ttu-id="a4d8f-106">这可以使策略调用.NET 类的静态方法而无需客户端来断言该类的实例。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-106">This allows the policy to invoke the static methods of a .NET class without requiring the client to assert an instance of the class.</span></span> <span data-ttu-id="a4d8f-107">有关详细信息，请参阅[类的调用静态成员](../core/invoking-static-members-of-a-class.md)。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-107">For more information, see [Invoking Static Members of a Class](../core/invoking-static-members-of-a-class.md).</span></span>  

## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="a4d8f-108">本演练概述</span><span class="sxs-lookup"><span data-stu-id="a4d8f-108">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="a4d8f-109">本演练包含五个过程，如下表中所述。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-109">This walkthrough contains five procedures, as described in the following table.</span></span>  

|<span data-ttu-id="a4d8f-110">过程标题</span><span class="sxs-lookup"><span data-stu-id="a4d8f-110">Procedure title</span></span>|<span data-ttu-id="a4d8f-111">过程说明</span><span class="sxs-lookup"><span data-stu-id="a4d8f-111">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="a4d8f-112">若要创建 TestDB 数据库和 PO 表</span><span class="sxs-lookup"><span data-stu-id="a4d8f-112">To create the TestDB database and the PO table</span></span>|<span data-ttu-id="a4d8f-113">提供创建的分步说明**TestDB**数据库并**PO**表。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-113">Provides step-by-step instructions for creating the **TestDB** database and the **PO** table.</span></span>|  
|<span data-ttu-id="a4d8f-114">若要创建 POUtility 组件</span><span class="sxs-lookup"><span data-stu-id="a4d8f-114">To create the POUtility component</span></span>|<span data-ttu-id="a4d8f-115">提供创建的分步说明**POUtility**组件。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-115">Provides step-by-step instructions for creating the **POUtility** component.</span></span>|  
|<span data-ttu-id="a4d8f-116">若要创建 ProcessPurchaseOrderDbNet 业务策略</span><span class="sxs-lookup"><span data-stu-id="a4d8f-116">To create the ProcessPurchaseOrderDbNet business policy</span></span>|<span data-ttu-id="a4d8f-117">提供创建的分步说明**ProcessPurchaseOrderDbNet**策略。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-117">Provides step-by-step instructions for creating the **ProcessPurchaseOrderDbNet** policy.</span></span>|  
|<span data-ttu-id="a4d8f-118">若要使用业务规则编辑器测试 ProcessPurchaseOrderDbNet 策略</span><span class="sxs-lookup"><span data-stu-id="a4d8f-118">To test the ProcessPurchaseOrderDbNet policy by using the Business Rule Composer</span></span>|<span data-ttu-id="a4d8f-119">提供使用业务规则编辑器来测试的分步说明**ProcessPurchaseOrderDbNet**策略。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-119">Provides step-by-step instructions for using the Business Rule Composer to test the **ProcessPurchaseOrderDbNet** policy.</span></span>|  
|<span data-ttu-id="a4d8f-120">若要使用 Policy.Execute 方法测试 ProcessPurchaseOrderDbNet 策略</span><span class="sxs-lookup"><span data-stu-id="a4d8f-120">To test the ProcessPurchaseOrderDbNet policy by using the Policy.Execute method</span></span>|<span data-ttu-id="a4d8f-121">提供用于测试的分步说明**ProcessPurchaseOrderDbNet**通过使用策略**Policy.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-121">Provides step-by-step instructions for testing the **ProcessPurchaseOrderDbNet** policy by using the **Policy.Execute** method.</span></span>|  

### <a name="to-create-the-testdb-database-and-the-po-table"></a><span data-ttu-id="a4d8f-122">若要创建 TestDB 数据库和 PO 表</span><span class="sxs-lookup"><span data-stu-id="a4d8f-122">To create the TestDB database and the PO table</span></span>  

1.  <span data-ttu-id="a4d8f-123">打开 SQL Server Management Studio  。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-123">Open **SQL Server Management Studio**.</span></span>  

2.  <span data-ttu-id="a4d8f-124">验证服务器名称和身份验证，然后单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-124">Verify the server name and authentication, and then click **Connect**.</span></span>  

3.  <span data-ttu-id="a4d8f-125">在左侧的对象资源管理器窗口中，右键单击计算机名称，然后单击**新查询**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-125">In the Object Explorer window on the left, right-click the computer name, and then click **New Query**.</span></span>  

4.  <span data-ttu-id="a4d8f-126">将以下 SQL 语句复制到查询窗口：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-126">Copy the following SQL statements to the query window:</span></span>  

    ```  
    CREATE DATABASE [TestDB]  
    GO  

    Use TestDB  
    CREATE TABLE [dbo].[PO]([PONumber] [nvarchar](50) NOT NULL,  
    [Quantity] [int] NOT NULL,  
    [Status] [nchar](10) NULL  
    CONSTRAINT [PK_PO] PRIMARY KEY CLUSTERED ([PONumber] ASC))   
    GO  

    INSERT INTO PO VALUES ('PO1', 400, NULL)  
    INSERT INTO PO VALUES ('PO2', 700, NULL)  
    GO  
    ```  

5.  <span data-ttu-id="a4d8f-127">按 F5 执行 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-127">Press F5 to execute the SQL query.</span></span>  

6.  <span data-ttu-id="a4d8f-128">在对象资源管理器窗口中，展开计算机名称，展开**数据库**，然后确认**TestDB**存在。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-128">In the Object Explorer window, expand the computer name, expand **Databases**, and then verify that **TestDB** exists.</span></span>  

7.  <span data-ttu-id="a4d8f-129">展开**TestDB**，展开**表**，然后验证**dbo。PO**存在。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-129">Expand **TestDB**, expand **Tables**, and then verify that **dbo.PO** exists.</span></span>  

8.  <span data-ttu-id="a4d8f-130">右键单击**dbo。采购订单**，然后单击**打开表**以验证表中是否存在以下数据。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-130">Right-click **dbo.PO**, and then click **Open Table** to verify that the following data exists in the table.</span></span>  

    |<span data-ttu-id="a4d8f-131">PONumber</span><span class="sxs-lookup"><span data-stu-id="a4d8f-131">PONumber</span></span>|<span data-ttu-id="a4d8f-132">Quantity</span><span class="sxs-lookup"><span data-stu-id="a4d8f-132">Quantity</span></span>|<span data-ttu-id="a4d8f-133">“登录属性”</span><span class="sxs-lookup"><span data-stu-id="a4d8f-133">Status</span></span>|  
    |--------------|--------------|------------|  
    |<span data-ttu-id="a4d8f-134">PO1</span><span class="sxs-lookup"><span data-stu-id="a4d8f-134">PO1</span></span>|<span data-ttu-id="a4d8f-135">400</span><span class="sxs-lookup"><span data-stu-id="a4d8f-135">400</span></span>|<span data-ttu-id="a4d8f-136">NULL</span><span class="sxs-lookup"><span data-stu-id="a4d8f-136">NULL</span></span>|  
    |<span data-ttu-id="a4d8f-137">PO2</span><span class="sxs-lookup"><span data-stu-id="a4d8f-137">PO2</span></span>|<span data-ttu-id="a4d8f-138">700</span><span class="sxs-lookup"><span data-stu-id="a4d8f-138">700</span></span>|<span data-ttu-id="a4d8f-139">NULL</span><span class="sxs-lookup"><span data-stu-id="a4d8f-139">NULL</span></span>|  

### <a name="to-create-the-poutility-component"></a><span data-ttu-id="a4d8f-140">若要创建 POUtility 组件</span><span class="sxs-lookup"><span data-stu-id="a4d8f-140">To create the POUtility component</span></span>  

1. <span data-ttu-id="a4d8f-141">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-141">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="a4d8f-142">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-142">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  

3. <span data-ttu-id="a4d8f-143">在中**新的项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-143">In the **New Project** dialog box, do the following:</span></span>  


   |             <span data-ttu-id="a4d8f-144">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a4d8f-144">Use this</span></span>              |                             <span data-ttu-id="a4d8f-145">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a4d8f-145">To do this</span></span>                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         <span data-ttu-id="a4d8f-146">**项目类型**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-146">**Project types**</span></span>         |                        <span data-ttu-id="a4d8f-147">单击**Visual C#** 。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-147">Click **Visual C#**.</span></span>                         |
   |           <span data-ttu-id="a4d8f-148">**模板**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-148">**Templates**</span></span>           |                      <span data-ttu-id="a4d8f-149">单击**类库**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-149">Click **Class Library**.</span></span>                       |
   |             <span data-ttu-id="a4d8f-150">**名称**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-150">**Name**</span></span>              |                       <span data-ttu-id="a4d8f-151">类型**POUtilityLib**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-151">Type **POUtilityLib**.</span></span>                        |
   |           <span data-ttu-id="a4d8f-152">**位置**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-152">**Location**</span></span>            |          <span data-ttu-id="a4d8f-153">指定**C:\BRE-Walkthroughs**作为位置。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-153">Specify **C:\BRE-Walkthroughs** as the location.</span></span>           |
   |         <span data-ttu-id="a4d8f-154">**解决方案名称**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-154">**Solution Name**</span></span>         |                       <span data-ttu-id="a4d8f-155">类型**POUtilitySol**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-155">Type **POUtilitySol**.</span></span>                        |
   | <span data-ttu-id="a4d8f-156">**创建解决方案的目录**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-156">**Create directory for solution**</span></span> | <span data-ttu-id="a4d8f-157">选中此复选框以创建解决方案文件的目录。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-157">Select this check box to create a directory for the solution files.</span></span> |


4. <span data-ttu-id="a4d8f-158">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-158">Click **OK**.</span></span> <span data-ttu-id="a4d8f-159">**POUtilityLib**项目应该显示在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-159">The **POUtilityLib** project should appear in Solution Explorer.</span></span> <span data-ttu-id="a4d8f-160">如果看不到解决方案资源管理器，请单击**解决方案资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-160">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  

5. <span data-ttu-id="a4d8f-161">在属性窗口中更改文件的名称**Class1.cs**给**POUtility.cs**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-161">In the Properties window, change the name of the file, **Class1.cs**, to **POUtility.cs**.</span></span>  

6. <span data-ttu-id="a4d8f-162">向类添加公共构造函数，如下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-162">Add a public constructor to the class as shown in the following code:</span></span>  

   ```  
   public POUtility()  
   {  
   }  
   ```  

7. <span data-ttu-id="a4d8f-163">添加名为的静态方法**GetMaxAllowed**到**POUtility**类，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-163">Add a static method named **GetMaxAllowed** to the **POUtility** class as shown in the following code:</span></span>  

   ```  
   public static int GetMaxAllowed()  
   {  
   return 500;  
   }   
   ```  

8. <span data-ttu-id="a4d8f-164">启动**Visual Studio 命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-164">Start **Visual Studio Command Prompt**.</span></span>  

9. <span data-ttu-id="a4d8f-165">将目录更改为**C:\BRE-Walkthroughs\POUtilitySol**，然后执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-165">Change the directory to **C:\BRE-Walkthroughs\POUtilitySol**, and then execute the following command:</span></span>  

     <span data-ttu-id="a4d8f-166">**Sn-k POUtility.snk**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-166">**Sn -k POUtility.snk**</span></span>  

10. <span data-ttu-id="a4d8f-167">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，展开**属性**，然后双击**AssemblyInfo.cs**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-167">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, expand **Properties**, and then double-click **AssemblyInfo.cs**.</span></span>  

11. <span data-ttu-id="a4d8f-168">添加以下语句到**AssemblyInfo.cs**文件的末尾：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-168">Add the following statement to the **AssemblyInfo.cs** file at the end:</span></span>  

    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POUtilitySol\POUtility.snk")]  
    ```  

12. <span data-ttu-id="a4d8f-169">在解决方案资源管理器窗口中，右键单击**POUtilityLib**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-169">In the Solution Explorer window, right-click **POUtilityLib**, and then click **Build**.</span></span>  

13. <span data-ttu-id="a4d8f-170">在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改为**C:\BRE-Walkthroughs\POUtilitySol\POUtilityLib\Bin\Debug**，然后执行以下命令以向 GAC （全局注册 POUtility 组件程序集缓存）。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-170">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt, change the directory to **C:\BRE-Walkthroughs\POUtilitySol\POUtilityLib\Bin\Debug**, and then execute the following command to register the POUtility component with the GAC (global assembly cache).</span></span> <span data-ttu-id="a4d8f-171">如果没有命令提示符下打开，请执行步骤 8 以将其打开。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-171">If you do not have the command prompt open, follow step 8 to open it.</span></span>  

     <span data-ttu-id="a4d8f-172">**Gacutil -i POUtilityLib.dll**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-172">**Gacutil -i POUtilityLib.dll**</span></span>  

### <a name="to-create-the-processpurchaseorderdbnet-business-policy"></a><span data-ttu-id="a4d8f-173">若要创建 ProcessPurchaseOrderDbNet 业务策略</span><span class="sxs-lookup"><span data-stu-id="a4d8f-173">To create the ProcessPurchaseOrderDbNet business policy</span></span>  

1.  <span data-ttu-id="a4d8f-174">上**启动**菜单中，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-174">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="a4d8f-175">如果你有业务规则编辑器已打开，请按 f5 键刷新。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-175">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a4d8f-176">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-176">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="a4d8f-177">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-177">To do this, right-click the application, and then select **Run as administrator**.</span></span>  

2.  <span data-ttu-id="a4d8f-178">在事实浏览器窗口中，单击**数据库**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-178">In the Facts Explorer window, click **Databases**.</span></span>  

3.  <span data-ttu-id="a4d8f-179">右键单击**服务器**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-179">Right-click **Servers**, and then click **Browse**.</span></span>  

4.  <span data-ttu-id="a4d8f-180">验证服务器和身份验证信息，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-180">Verify the server and authentication information, and then click **OK**.</span></span>  

5.  <span data-ttu-id="a4d8f-181">展开**TestDB**，然后展开**PO**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-181">Expand **TestDB**, and then expand **PO**.</span></span>  

6.  <span data-ttu-id="a4d8f-182">在事实浏览器窗口中，单击 **.NET 类**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-182">In the Facts Explorer window, click **.NET Classes**.</span></span>  

7.  <span data-ttu-id="a4d8f-183">右键单击 **。NETAssemblies**，然后单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-183">Right-click **.NETAssemblies**, and then click **Browse**.</span></span>  

8.  <span data-ttu-id="a4d8f-184">选择**POUtility**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-184">Select **POUtility**, and then click **OK**.</span></span>  

9. <span data-ttu-id="a4d8f-185">展开**Class1**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-185">Expand **Class1**.</span></span>  

10. <span data-ttu-id="a4d8f-186">在策略浏览器窗口中，右键单击**策略**，然后单击**添加新策略**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-186">In the Policy Explorer window, right-click **Policies**, and then click **Add New Policy**.</span></span>  

11. <span data-ttu-id="a4d8f-187">更改从策略的名称**Policy1**到**ProcessPurchaseOrderDbNet** ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-187">Change the name of the policy from **Policy1** to **ProcessPurchaseOrderDbNet** and then press ENTER.</span></span> <span data-ttu-id="a4d8f-188">此外可以更改属性窗口中的策略的名称。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-188">You can also change the name of the policy in the Properties window.</span></span>  

12. <span data-ttu-id="a4d8f-189">右键单击**版本 1.0**，然后单击**AddNewRule**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-189">Right-click **Version 1.0**, and then click **AddNewRule**.</span></span>  

13. <span data-ttu-id="a4d8f-190">更改规则的名称**Rule1**到**ApprovalRule** ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-190">Change the name of the rule from **Rule1** to **ApprovalRule** and then press ENTER.</span></span> <span data-ttu-id="a4d8f-191">此外可以更改属性窗口中的规则的名称。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-191">You can also change the name of the rule in the Properties window.</span></span>  

14. <span data-ttu-id="a4d8f-192">在如果窗格 （顶部） 在右侧，右击**条件**，单击**谓词**，然后单击**小于或等于**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-192">In the IF pane (top) on the right, right-click **Conditions**, click **Predicates**, and then click **LessThanEqual**.</span></span>  

15. <span data-ttu-id="a4d8f-193">在事实浏览器窗口中，单击**数据库**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-193">In the Facts Explorer window, click **Databases**.</span></span>  

16. <span data-ttu-id="a4d8f-194">拖动**Quantity**节点从事实浏览器窗口**argument1**如果窗格中。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-194">Drag the **Quantity** node from the Facts Explorer window to **argument1** in the IF pane.</span></span>  

17. <span data-ttu-id="a4d8f-195">在事实浏览器窗口中，单击 **.NET 类**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-195">In the Facts Explorer window, click **.NET Classes**.</span></span>  

18. <span data-ttu-id="a4d8f-196">拖动**GetMaxAllowed**节点从事实浏览器窗口**argument2**如果窗格中。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-196">Drag **GetMaxAllowed** node from the Facts Explorer window to **argument2** in the IF pane.</span></span>  

19. <span data-ttu-id="a4d8f-197">在事实浏览器窗口中，单击**数据库**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-197">In the Facts Explorer window, click **Databases**.</span></span>  

20. <span data-ttu-id="a4d8f-198">拖动**状态**节点从事实浏览器窗口右下角的业务规则编辑器那么窗格。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-198">Drag the **Status** node from the Facts Explorer window to the THEN pane at the bottom right of the Business Rule Composer.</span></span>  

21. <span data-ttu-id="a4d8f-199">在那么窗格中，单击 **\<输入值\>** ，然后键入**已批准**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-199">In the THEN pane, click **\<Enter a value\>** and then type **Approved**.</span></span>  

22. <span data-ttu-id="a4d8f-200">在事实浏览器窗口中，右键单击**版本 1.0**中**ProcessPurchaseOrderDbNet**，然后单击**AddNewRule**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-200">In the Facts Explorer window, right-click **Version 1.0** in **ProcessPurchaseOrderDbNet**, and then click **AddNewRule**.</span></span>  

23. <span data-ttu-id="a4d8f-201">更改规则的名称**Rule1**到**DeniedRule** ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-201">Change the name of the rule from **Rule1** to **DeniedRule** and then press ENTER.</span></span> <span data-ttu-id="a4d8f-202">此外可以更改属性窗口中的规则的名称。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-202">You can also change the name of the rule in the Properties window.</span></span>  

24. <span data-ttu-id="a4d8f-203">在如果窗格 （顶部） 在右侧，右击**条件**，单击**谓词**，然后单击**GreaterThan**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-203">In the IF pane (top) on the right, right-click **Conditions**, click **Predicates**, and then click **GreaterThan**.</span></span>  

25. <span data-ttu-id="a4d8f-204">在事实浏览器窗口中，单击**数据库**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-204">In the Facts Explorer window, click **Databases**.</span></span>  

26. <span data-ttu-id="a4d8f-205">拖动**Quantity**节点从事实浏览器窗口**argument1**如果窗格中。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-205">Drag the **Quantity** node from the Facts Explorer window to **argument1** in the IF pane.</span></span>  

27. <span data-ttu-id="a4d8f-206">在事实浏览器窗口中，单击 **.NET 类**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-206">In the Facts Explorer window, click **.NET Classes**.</span></span>  

28. <span data-ttu-id="a4d8f-207">拖动**GetMaxAllowed**节点从事实浏览器窗口**argument2**如果窗格中。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-207">Drag the **GetMaxAllowed** node from the Facts Explorer window to **argument2** in the IF pane.</span></span>  

29. <span data-ttu-id="a4d8f-208">在事实浏览器窗口中，单击**数据库**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-208">In the Facts Explorer window, click **Databases**.</span></span>  

30. <span data-ttu-id="a4d8f-209">拖动**状态**节点从事实浏览器窗口右下角的业务规则编辑器那么窗格。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-209">Drag the **Status** node from the Facts Explorer window to the THEN pane at the bottom right of the Business Rule Composer.</span></span>  

31. <span data-ttu-id="a4d8f-210">在那么窗格中，单击 **\<输入值\>** ，然后键入**拒绝**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-210">In the THEN pane, click **\<Enter a value\>** and then type **Denied**.</span></span>  

32. <span data-ttu-id="a4d8f-211">在策略浏览器窗口中，右键单击**版本 1.0 （未保存）** ，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-211">In the Policy Explorer window, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  

### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-business-rule-composer"></a><span data-ttu-id="a4d8f-212">若要使用业务规则编辑器测试 ProcessPurchaseOrderDbNet 策略</span><span class="sxs-lookup"><span data-stu-id="a4d8f-212">To test the ProcessPurchaseOrderDbNet policy by using the Business Rule Composer</span></span>  

1.  <span data-ttu-id="a4d8f-213">上**启动**菜单中，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-213">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="a4d8f-214">如果你有业务规则编辑器已打开，请按 f5 键刷新。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-214">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  

2.  <span data-ttu-id="a4d8f-215">在策略浏览器窗口中，展开**策略**，展开**ProcessPurchaseOrderDbNet**，右键单击**版本 1.0**，然后单击**测试策略**.</span><span class="sxs-lookup"><span data-stu-id="a4d8f-215">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrderDbNet**, right-click **Version 1.0**, and then click **Test Policy**.</span></span>  

3.  <span data-ttu-id="a4d8f-216">单击**TestDB:PO （数据连接）** ，然后单击**添加实例**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-216">Click **TestDB:PO (Data Connection)**, and then click **Add Instance**.</span></span>  

4.  <span data-ttu-id="a4d8f-217">在中**连接到 SQL Server**对话框中，验证服务器名称和身份验证信息，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-217">In the **Connect to SQL Server** dialog box, verify the server name and authentication information, and then click **OK**.</span></span>  

5.  <span data-ttu-id="a4d8f-218">在中**选择绑定**对话框框中，展开**TestDB**，单击**PO**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-218">In the **Select Binding** dialog box, expand **TestDB**, click **PO**, and then click **OK**.</span></span>  

6.  <span data-ttu-id="a4d8f-219">单击**测试**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-219">Click **Test**.</span></span>  

7.  <span data-ttu-id="a4d8f-220">在输出窗口中，验证是否同时**ApprovalRule**并**DeniedRule**触发。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-220">In the Output window, verify that both the **ApprovalRule** and the **DeniedRule** are fired.</span></span>  

8.  <span data-ttu-id="a4d8f-221">在 SQL Server Management Studio 中，右键单击**dbo。采购订单**，然后单击**打开表**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-221">In SQL Server Management Studio, right-click **dbo.PO**, and then click **Open Table**.</span></span>  

9. <span data-ttu-id="a4d8f-222">验证的值**状态**字段设置为**Approved**的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-222">Verify that the value of the **Status** field is set to **Approved** for the first record.</span></span>  

10. <span data-ttu-id="a4d8f-223">验证的值**状态**字段设置为**拒绝**第二个记录。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-223">Verify that the value of the **Status** field is set to **Denied** for the second record.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a4d8f-224">如果仍看到的值**状态**字段为 NULL，右键单击包含数据的列表，然后单击**执行 SQL**，刷新视图。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-224">If you still see the value of the **Status** field as NULL, right-click the list containing the data, and then click **Execute SQL**, which refreshes the view.</span></span>  

11. <span data-ttu-id="a4d8f-225">SQL Server Management Studio 保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-225">Keep SQL Server Management Studio open.</span></span>  

### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-policyexecute-method"></a><span data-ttu-id="a4d8f-226">若要使用 Policy.Execute 方法测试 ProcessPurchaseOrderDbNet 策略</span><span class="sxs-lookup"><span data-stu-id="a4d8f-226">To test the ProcessPurchaseOrderDbNet policy by using the Policy.Execute method</span></span>  

1. <span data-ttu-id="a4d8f-227">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-227">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="a4d8f-228">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-228">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  

3. <span data-ttu-id="a4d8f-229">在中**新的项目**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-229">In the **New Project** dialog box, do the following:</span></span>  


   |             <span data-ttu-id="a4d8f-230">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a4d8f-230">Use this</span></span>              |                             <span data-ttu-id="a4d8f-231">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a4d8f-231">To do this</span></span>                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         <span data-ttu-id="a4d8f-232">**项目类型**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-232">**Project types**</span></span>         |                        <span data-ttu-id="a4d8f-233">单击**Visual C#** 。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-233">Click **Visual C#**.</span></span>                         |
   |           <span data-ttu-id="a4d8f-234">**模板**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-234">**Templates**</span></span>           |                   <span data-ttu-id="a4d8f-235">单击**控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-235">Click **Console Application**.</span></span>                    |
   |             <span data-ttu-id="a4d8f-236">**名称**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-236">**Name**</span></span>              |                    <span data-ttu-id="a4d8f-237">类型**TestProcessPODbNet**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-237">Type **TestProcessPODbNet**.</span></span>                     |
   |           <span data-ttu-id="a4d8f-238">**位置**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-238">**Location**</span></span>            |          <span data-ttu-id="a4d8f-239">指定**C:\BRE-Walkthroughs**作为位置。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-239">Specify **C:\BRE-Walkthroughs** as the location.</span></span>           |
   |         <span data-ttu-id="a4d8f-240">**解决方案名称**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-240">**Solution Name**</span></span>         |                   <span data-ttu-id="a4d8f-241">类型**TestProcessPODbNetSol**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-241">Type **TestProcessPODbNetSol**.</span></span>                   |
   | <span data-ttu-id="a4d8f-242">**创建解决方案的目录**</span><span class="sxs-lookup"><span data-stu-id="a4d8f-242">**Create directory for solution**</span></span> | <span data-ttu-id="a4d8f-243">选中此复选框以创建解决方案文件的目录。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-243">Select this check box to create a directory for the solution files.</span></span> |


4. <span data-ttu-id="a4d8f-244">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-244">Click **OK**.</span></span> <span data-ttu-id="a4d8f-245">**TestProcessPODbNet**项目应该显示在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-245">The **TestProcessPODbNet** project should appear in Solution Explorer.</span></span> <span data-ttu-id="a4d8f-246">如果看不到解决方案资源管理器，请单击**解决方案资源管理器**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-246">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  

5. <span data-ttu-id="a4d8f-247">在解决方案资源管理器中右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-247">In Solution Explorer, right-click **References**, and then click **Add Reference**.</span></span>  

6. <span data-ttu-id="a4d8f-248">单击**浏览**，浏览到 **\Program Files\Common Files\Microsoft BizTalk**，然后双击**Microsoft.RuleEngine.dll**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-248">Click **Browse**, browse to **\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.RuleEngine.dll**.</span></span>  

7. <span data-ttu-id="a4d8f-249">将以下代码添加到顶部**Program.cs**之后的现有文件`using`语句：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-249">Add the following code to the top of the **Program.cs** file after the existing `using` statements:</span></span>  

   ```  
   //To use the SQLConnection class  
   using System.Data.SqlClient;  

   //To use the Policy and DataConnection classes  
   using Microsoft.RuleEngine;  
   ```  

8. <span data-ttu-id="a4d8f-250">将以下代码添加到**Main**函数以创建并打开**SQLConnection**对象：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-250">Add the following code to the **Main** function to create and open a **SQLConnection** object:</span></span>  

   ```  
   SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
   cn.Open();  
   ```  

9. <span data-ttu-id="a4d8f-251">将以下代码添加到**Main**函数末尾，以创建**DataConnection**对象基于**SQLConnection**对象上一步中创建：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-251">Add the following code to the **Main** function at the end to create a **DataConnection** object based on the **SQLConnection** object you created in the previous step:</span></span>  

    ```  
    DataConnection dc = new DataConnection("TestDB", "PO", cn);  
    ```  

10. <span data-ttu-id="a4d8f-252">将以下代码添加到**Main**函数末尾，以创建**策略**对象，并执行策略：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-252">Add the following code to the **Main** function at the end to create a **Policy** object and execute the policy:</span></span>  

    ```  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    policy.Execute(dc);  
    ```  

11. <span data-ttu-id="a4d8f-253">将以下代码添加到**Main**函数末尾，以更新数据库：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-253">Add the following code to the **Main** function at the end to update the database:</span></span>  

    ```  
    dc.Update();  
    ```  

12. <span data-ttu-id="a4d8f-254">将以下代码添加到**Main**函数末尾，以关闭到数据库的连接：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-254">Add the following code to the **Main** function at the end to close the connection to the database:</span></span>  

    ```  
    cn.Close();  
    ```  

13. <span data-ttu-id="a4d8f-255">添加 try catch 块来捕获任何异常中生成**Main**方法。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-255">Add a try-catch block to catch any exception generated in the **Main** method.</span></span>  

14. <span data-ttu-id="a4d8f-256">验证的完整代码**Main**函数是下面的代码中所示：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-256">Verify that the complete code for the **Main** function is as shown in the following code:</span></span>  

    ```  
    try  
    {  
    SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
    cn.Open();  
    DataConnection dc = new DataConnection("TestDB", "PO", cn);  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    policy.Execute(dc);  
    dc.Update();  
    cn.Close();  
    }  
    catch (Exception ex)  
    {  
    Console.WriteLine(ex.Message);  
    }  
    ```  

15. <span data-ttu-id="a4d8f-257">上**构建**菜单上，单击**生成 TestProcessPODbNet**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-257">On the **Build** menu, click **Build TestProcessPODbNet**.</span></span>  

16. <span data-ttu-id="a4d8f-258">在业务规则编辑器中，展开**策略**，展开**ProcessPurchaseOrderDbNet**，右键单击**版本 1.0**，然后单击**发布**.</span><span class="sxs-lookup"><span data-stu-id="a4d8f-258">In the Business Rule Composer, expand **Policies**, expand **ProcessPurchaseOrderDbNet**, right-click **Version 1.0**, and then click **Publish**.</span></span>  

17. <span data-ttu-id="a4d8f-259">右键单击**版本 1.0-已发布**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-259">Right-click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  

18. <span data-ttu-id="a4d8f-260">在 SQL Server Management Studio 中，将的值设置**状态**字段**NULL**采购订单记录。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-260">In SQL Server Management Studio, set the value of the **Status** field to **NULL** for both the PO records.</span></span>  

19. <span data-ttu-id="a4d8f-261">在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，按 CTRL + F5 来执行**TestProcessPODbNet**应用程序。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-261">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], Press CTRL+F5 to execute the **TestProcessPODbNet** application.</span></span>  

20. <span data-ttu-id="a4d8f-262">按任意键关闭命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-262">Press any key to close the command prompt window.</span></span>  

21. <span data-ttu-id="a4d8f-263">在 SQL Server Management Studio 中，右键单击包括 PO 记录的表，然后单击**执行 SQL**。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-263">In SQL Server Management Studio, right-click the table with PO records, and then click **Execute SQL**.</span></span>  

22. <span data-ttu-id="a4d8f-264">验证的值**状态**字段设置为**Approved**的第一条记录。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-264">Verify that the value of the **Status** field is set to **Approved** for the first record.</span></span>  

23. <span data-ttu-id="a4d8f-265">验证的值**状态**字段设置为**拒绝**第二个记录。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-265">Verify that the value of the **Status** field is set to **Denied** for the second record.</span></span>  

## <a name="comments"></a><span data-ttu-id="a4d8f-266">注释</span><span class="sxs-lookup"><span data-stu-id="a4d8f-266">Comments</span></span>  

-   <span data-ttu-id="a4d8f-267">如果策略使用.NET 类的非静态方法，您需要使用断言.NET 类，通过使用业务规则编辑器测试策略的实例的事实创建器组件。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-267">If a policy uses the non-static methods of a .NET class, you need to use a fact creator component that asserts an instance of the .NET class to test the policy by using the Business Rule Composer.</span></span>  

-   <span data-ttu-id="a4d8f-268">它是非常重要，记住业务规则编辑器创建的实例**DataConnection**对象，并将其添加到规则引擎工作内存会自动为您。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-268">It is very important to remember that the Business Rule Composer creates an instance of the **DataConnection** object and asserts it into the working memory of the rule engine automatically for you.</span></span> <span data-ttu-id="a4d8f-269">但是，当调用从客户端 （BizTalk 或非 BizTalk） 应用程序中，策略**DataConnection**对象不为您自动创建。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-269">However, when you invoke the policy from a client (BizTalk or non-BizTalk) application, the **DataConnection** object is not created automatically for you.</span></span> <span data-ttu-id="a4d8f-270">创建客户端应**DataConnection**对象，并将其作为参数或事实传递到规则引擎以执行策略。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-270">The client should create a **DataConnection** object and pass it as a parameter or fact to the rule engine to execute the policy.</span></span>  

-   <span data-ttu-id="a4d8f-271">可以使用**DebugTrackingInterceptor**类跟踪策略执行详细信息。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-271">You can use the **DebugTrackingInterceptor** class to track the policy execution details.</span></span> <span data-ttu-id="a4d8f-272">下面的示例代码演示如何创建的实例**DebugTrackingInterceptor**类，并使用它执行策略时：</span><span class="sxs-lookup"><span data-stu-id="a4d8f-272">The following sample code shows how to create an instance of the **DebugTrackingInterceptor** class, and use it when executing the policy:</span></span>  

    ```  
    DebugTrackingInterceptor dti = new DebugTrackingInterceptor("c:\\Trace.txt");  
    policy.Execute(dc, dti);  
    ```  

-   <span data-ttu-id="a4d8f-273">可以使用**SqlTransaction**类，以更新数据库从**ProcessPODbNet**策略以事务的方式。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-273">You can use the **SqlTransaction** class to update the database from the **ProcessPODbNet** policy in a transactional manner.</span></span> <span data-ttu-id="a4d8f-274">下面的代码演示如何开始一个事务，请将事务作为参数传递**DataConnection**对象，并提交数据库更改。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-274">The following code shows how to begin a transaction, pass the transaction as a parameter to the **DataConnection** object, and commit the database changes.</span></span> <span data-ttu-id="a4d8f-275">有关详细信息，请参阅[事务支持](../core/transaction-support.md)。</span><span class="sxs-lookup"><span data-stu-id="a4d8f-275">For more information, see [Transaction Support](../core/transaction-support.md).</span></span>  

    ```  
    SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
    cn.Open();  
    //Begin the transaction  
    SqlTransaction  tn = cn.BeginTransaction();  
    //Pass the transaction object to the DataConnection constructor  
    DataConnection dc = new DataConnection("TestDB", "PO", cn, tn);  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    DebugTrackingInterceptor dti = new DebugTrackingInterceptor("c:\\Trace.txt");  
    policy.Execute(dc, dti);  
    dc.Update();  
    //Commit the database transaction  
    tn.Commit();  
    cn.Close();  
    ```  

## <a name="see-also"></a><span data-ttu-id="a4d8f-276">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4d8f-276">See Also</span></span>  
 [<span data-ttu-id="a4d8f-277">选择事实</span><span class="sxs-lookup"><span data-stu-id="a4d8f-277">Selecting Facts</span></span>](../core/selecting-facts.md)