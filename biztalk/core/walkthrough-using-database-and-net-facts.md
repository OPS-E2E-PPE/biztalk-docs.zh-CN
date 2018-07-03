---
title: 演练： 使用数据库和.NET 事实 |Microsoft Docs
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
ms.openlocfilehash: 94eb3f34a529950a7344f6cc4579aa6f6909f813
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966950"
---
# <a name="walkthrough-using-database-and-net-facts"></a>演练： 使用数据库和.NET 事实
此演练将介绍使用业务规则编辑器创建使用数据库和 .NET 事实的策略的分步说明。  

## <a name="prerequisites"></a>必要條件  
 必须设置的值**StaticSupport**为 1 或 2 才能执行本演练的注册表项。 这样可以使策略调用 .NET 类的静态方法，而无需客户端来断言该类的实例。 有关详细信息，请参阅[类的调用静态成员](../core/invoking-static-members-of-a-class.md)。  

## <a name="overview-of-this-walkthrough"></a>本演练概述  
 本演练包含五个过程，如下表所述。  

|过程标题|过程说明|  
|---------------------|---------------------------|  
|创建 TestDB 数据库和 PO 表的步骤|提供创建的分步说明**TestDB**数据库并**PO**表。|  
|创建 POUtility 组件的步骤|提供创建的分步说明**POUtility**组件。|  
|创建 ProcessPurchaseOrderDbNet 业务策略的步骤|提供创建的分步说明**ProcessPurchaseOrderDbNet**策略。|  
|使用业务规则编辑器测试 ProcessPurchaseOrderDbNet 策略|提供使用业务规则编辑器来测试的分步说明**ProcessPurchaseOrderDbNet**策略。|  
|使用 Policy.Execute 方法测试 ProcessPurchaseOrderDbNet 策略|提供用于测试的分步说明**ProcessPurchaseOrderDbNet**通过使用策略**Policy.Execute**方法。|  

### <a name="to-create-the-testdb-database-and-the-po-table"></a>创建 TestDB 数据库和 PO 表的步骤  

1.  打开 SQL Server Management Studio。  

2.  验证服务器名称和身份验证，然后单击**Connect**。  

3.  在左侧的对象资源管理器窗口中，右键单击计算机名称，然后单击**新查询**。  

4.  将以下 SQL 语句复制到查询窗口：  

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

5.  按 F5 执行 SQL 查询。  

6.  在对象资源管理器窗口中，展开计算机名称，展开**数据库**，然后确认**TestDB**存在。  

7.  展开**TestDB**，展开**表**，然后验证**dbo。PO**存在。  

8.  右键单击**dbo。采购订单**，然后单击**打开表**以验证表中是否存在以下数据。  

    |PONumber|Quantity|“登录属性”|  
    |--------------|--------------|------------|  
    |PO1|400|NULL|  
    |PO2|700|NULL|  

### <a name="to-create-the-poutility-component"></a>创建 POUtility 组件的步骤  

1. 启动**Microsoft Visual Studio**。  

2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。  

3. 在中**新的项目**对话框框中，执行以下操作：  


   |             使用此选项              |                             执行的操作                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         **项目类型**         |                        单击**Visual C#**。                         |
   |           **模板**           |                      单击**类库**。                       |
   |             **名称**              |                       类型**POUtilityLib**。                        |
   |           **位置**            |          指定**C:\BRE-Walkthroughs**作为位置。           |
   |         **解决方案名称**         |                       类型**POUtilitySol**。                        |
   | **创建解决方案的目录** | 选中此复选框以便为解决方案文件创建目录。 |


4. 单击“确定” 。 **POUtilityLib**项目应该显示在解决方案资源管理器。 如果看不到解决方案资源管理器，请单击**解决方案资源管理器**上**视图**菜单。  

5. 在属性窗口中更改文件的名称**Class1.cs**给**POUtility.cs**。  

6. 向该类添加公共构造函数，如以下代码所示：  

   ```  
   public POUtility()  
   {  
   }  
   ```  

7. 添加名为的静态方法**GetMaxAllowed**到**POUtility**类，如以下代码所示：  

   ```  
   public static int GetMaxAllowed()  
   {  
   return 500;  
   }   
   ```  

8. 启动**Visual Studio 命令提示符**。  

9. 将目录更改为**C:\BRE-Walkthroughs\POUtilitySol**，然后执行以下命令：  

     **Sn-k POUtility.snk**  

10. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，展开**属性**，然后双击**AssemblyInfo.cs**。  

11. 添加以下语句到**AssemblyInfo.cs**文件的末尾：  

    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POUtilitySol\POUtility.snk")]  
    ```  

12. 在解决方案资源管理器窗口中，右键单击**POUtilityLib**，然后单击**生成**。  

13. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]命令提示符下，将目录更改为**C:\BRE-Walkthroughs\POUtilitySol\POUtilityLib\Bin\Debug**，然后执行以下命令以向 GAC （全局注册 POUtility 组件程序集缓存）。 如果没有命令提示符下打开，请执行步骤 8 以将其打开。  

     **Gacutil-i POUtilityLib.dll**  

### <a name="to-create-the-processpurchaseorderdbnet-business-policy"></a>创建 ProcessPurchaseOrderDbNet 业务策略的步骤  

1.  上**启动**菜单中，打开**业务规则编辑器**。 如果已打开业务规则编辑器，请按 F5 刷新。  

    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  

2.  在事实浏览器窗口中，单击**数据库**。  

3.  右键单击**服务器**，然后单击**浏览**。  

4.  验证服务器和身份验证信息，然后依次**确定**。  

5.  展开**TestDB**，然后展开**PO**。  

6.  在事实浏览器窗口中，单击 **.NET 类**。  

7.  右键单击 **。NETAssemblies**，然后单击**浏览**。  

8.  选择**POUtility**，然后单击**确定**。  

9. 展开**Class1**。  

10. 在策略浏览器窗口中，右键单击**策略**，然后单击**添加新策略**。  

11. 更改从策略的名称**Policy1**到**ProcessPurchaseOrderDbNet** ，然后按 ENTER。 你还可以在“属性”窗口中更改策略的名称。  

12. 右键单击**版本 1.0**，然后单击**AddNewRule**。  

13. 更改规则的名称**Rule1**到**ApprovalRule** ，然后按 ENTER。 您还可以在“属性”窗口中更改规则的名称。  

14. 在如果窗格 （顶部） 在右侧，右击**条件**，单击**谓词**，然后单击**小于或等于**。  

15. 在事实浏览器窗口中，单击**数据库**。  

16. 拖动**Quantity**节点从事实浏览器窗口**argument1**如果窗格中。  

17. 在事实浏览器窗口中，单击 **.NET 类**。  

18. 拖动**GetMaxAllowed**节点从事实浏览器窗口**argument2**如果窗格中。  

19. 在事实浏览器窗口中，单击**数据库**。  

20. 拖动**状态**节点从事实浏览器窗口右下角的业务规则编辑器那么窗格。  

21. 在那么窗格中，单击**\<输入值\>** ，然后键入**已批准**。  

22. 在事实浏览器窗口中，右键单击**版本 1.0**中**ProcessPurchaseOrderDbNet**，然后单击**AddNewRule**。  

23. 更改规则的名称**Rule1**到**DeniedRule** ，然后按 ENTER。 您还可以在“属性”窗口中更改规则的名称。  

24. 在如果窗格 （顶部） 在右侧，右击**条件**，单击**谓词**，然后单击**GreaterThan**。  

25. 在事实浏览器窗口中，单击**数据库**。  

26. 拖动**Quantity**节点从事实浏览器窗口**argument1**如果窗格中。  

27. 在事实浏览器窗口中，单击 **.NET 类**。  

28. 拖动**GetMaxAllowed**节点从事实浏览器窗口**argument2**如果窗格中。  

29. 在事实浏览器窗口中，单击**数据库**。  

30. 拖动**状态**节点从事实浏览器窗口右下角的业务规则编辑器那么窗格。  

31. 在那么窗格中，单击**\<输入值\>** ，然后键入**拒绝**。  

32. 在策略浏览器窗口中，右键单击**版本 1.0 （未保存）**，然后单击**保存**。  

### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-business-rule-composer"></a>使用业务规则编辑器测试 ProcessPurchaseOrderDbNet 策略  

1.  上**启动**菜单中，打开**业务规则编辑器**。 如果已打开业务规则编辑器，请按 F5 刷新。  

2.  在策略浏览器窗口中，展开**策略**，展开**ProcessPurchaseOrderDbNet**，右键单击**版本 1.0**，然后单击**测试策略**.  

3.  单击**TestDB:PO （数据连接）**，然后单击**添加实例**。  

4.  在中**连接到 SQL Server**对话框中，验证服务器名称和身份验证信息，然后单击**确定**。  

5.  在中**选择绑定**对话框框中，展开**TestDB**，单击**PO**，然后单击**确定**。  

6.  单击**测试**。  

7.  在输出窗口中，验证是否同时**ApprovalRule**并**DeniedRule**触发。  

8.  在 SQL Server Management Studio 中，右键单击**dbo。采购订单**，然后单击**打开表**。  

9. 验证的值**状态**字段设置为**Approved**的第一条记录。  

10. 验证的值**状态**字段设置为**拒绝**第二个记录。  

    > [!NOTE]
    >  如果仍看到的值**状态**字段为 NULL，右键单击包含数据的列表，然后单击**执行 SQL**，刷新视图。  

11. 使 SQL Server Management Studio 保持打开的状态。  

### <a name="to-test-the-processpurchaseorderdbnet-policy-by-using-the-policyexecute-method"></a>使用 Policy.Execute 方法测试 ProcessPurchaseOrderDbNet 策略  

1. 启动**Microsoft Visual Studio**。  

2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。  

3. 在中**新的项目**对话框框中，执行以下操作：  


   |             使用此选项              |                             执行的操作                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         **项目类型**         |                        单击**Visual C#**。                         |
   |           **模板**           |                   单击**控制台应用程序**。                    |
   |             **名称**              |                    类型**TestProcessPODbNet**。                     |
   |           **位置**            |          指定**C:\BRE-Walkthroughs**作为位置。           |
   |         **解决方案名称**         |                   类型**TestProcessPODbNetSol**。                   |
   | **创建解决方案的目录** | 选中此复选框以便为解决方案文件创建目录。 |


4. 单击“确定” 。 **TestProcessPODbNet**项目应该显示在解决方案资源管理器。 如果看不到解决方案资源管理器，请单击**解决方案资源管理器**上**视图**菜单。  

5. 在解决方案资源管理器中右键单击**引用**，然后单击**添加引用**。  

6. 单击**浏览**，浏览到**\Program Files\Common Files\Microsoft BizTalk**，然后双击**Microsoft.RuleEngine.dll**。  

7. 将以下代码添加到顶部**Program.cs**之后的现有文件`using`语句：  

   ```  
   //To use the SQLConnection class  
   using System.Data.SqlClient;  

   //To use the Policy and DataConnection classes  
   using Microsoft.RuleEngine;  
   ```  

8. 将以下代码添加到**Main**函数以创建并打开**SQLConnection**对象：  

   ```  
   SqlConnection cn = new SqlConnection("Data Source=(local);Initial Catalog=TestDB;Integrated Security=SSPI");  
   cn.Open();  
   ```  

9. 将以下代码添加到**Main**函数末尾，以创建**DataConnection**对象基于**SQLConnection**对象上一步中创建：  

    ```  
    DataConnection dc = new DataConnection("TestDB", "PO", cn);  
    ```  

10. 将以下代码添加到**Main**函数末尾，以创建**策略**对象，并执行策略：  

    ```  
    Policy policy = new Policy("ProcessPurchaseOrderDbNet");  
    policy.Execute(dc);  
    ```  

11. 将以下代码添加到**Main**函数末尾，以更新数据库：  

    ```  
    dc.Update();  
    ```  

12. 将以下代码添加到**Main**函数末尾，以关闭到数据库的连接：  

    ```  
    cn.Close();  
    ```  

13. 添加 try catch 块来捕获任何异常中生成**Main**方法。  

14. 验证的完整代码**Main**函数是下面的代码中所示：  

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

15. 上**构建**菜单上，单击**生成 TestProcessPODbNet**。  

16. 在业务规则编辑器中，展开**策略**，展开**ProcessPurchaseOrderDbNet**，右键单击**版本 1.0**，然后单击**发布**.  

17. 右键单击**版本 1.0-已发布**，然后单击**部署**。  

18. 在 SQL Server Management Studio 中，将的值设置**状态**字段**NULL**采购订单记录。  

19. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，按 CTRL + F5 来执行**TestProcessPODbNet**应用程序。  

20. 按任意键关闭命令提示符窗口。  

21. 在 SQL Server Management Studio 中，右键单击包括 PO 记录的表，然后单击**执行 SQL**。  

22. 验证的值**状态**字段设置为**Approved**的第一条记录。  

23. 验证的值**状态**字段设置为**拒绝**第二个记录。  

## <a name="comments"></a>注释  

-   如果策略使用 .NET 类的非静态方法，你需要使用断言 .NET 类的实例的事实创建器组件，以便通过使用业务规则编辑器来测试该策略。  

-   它是非常重要，记住业务规则编辑器创建的实例**DataConnection**对象，并将其添加到规则引擎工作内存会自动为您。 但是，当调用从客户端 （BizTalk 或非 BizTalk） 应用程序中，策略**DataConnection**对象不为您自动创建。 创建客户端应**DataConnection**对象，并将其作为参数或事实传递到规则引擎以执行策略。  

-   可以使用**DebugTrackingInterceptor**类跟踪策略执行详细信息。 下面的示例代码演示如何创建的实例**DebugTrackingInterceptor**类，并使用它执行策略时：  

    ```  
    DebugTrackingInterceptor dti = new DebugTrackingInterceptor("c:\\Trace.txt");  
    policy.Execute(dc, dti);  
    ```  

-   可以使用**SqlTransaction**类，以更新数据库从**ProcessPODbNet**策略以事务的方式。 下面的代码演示如何开始一个事务，请将事务作为参数传递**DataConnection**对象，并提交数据库更改。 有关详细信息，请参阅[事务支持](../core/transaction-support.md)。  

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

## <a name="see-also"></a>请参阅  
 [选择事实](../core/selecting-facts.md)