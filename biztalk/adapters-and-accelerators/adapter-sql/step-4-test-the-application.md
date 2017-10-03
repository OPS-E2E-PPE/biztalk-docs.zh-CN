---
title: "步骤 4： 测试应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 488b13fa-7a71-4430-bbf5-dbf47ba55562
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 347c2bcf459d7e9ce7b1fb9efc07579be81d989d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-the-application"></a>步骤 4： 测试应用程序
![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **完成时间：** 10 分钟  
  
 **目标：**的方法是插入中的记录在此步骤中，测试应用程序**员工**表**ADAPTER_SAMPLES**数据库。 如果应用程序都运行正常，业务流程会接收的更改的通知**员工**表。 然后，业务流程中提取收到的通知的类型。 如果通知为插入操作，业务流程执行**UPDATE_EMPLOYEE**存储过程并接收响应。 业务流程提取的值**Employee_ID**和**名称**响应并将其到插入**Purchase_Order**表。  
  
## <a name="prerequisites"></a>先决条件  
 在开始之前与此步骤，你必须确保以下方面：  
  
-   要调用的请求消息**UPDATE_EMPLOYEE**存储的过程位于 C:\TestLocation\CreateEmployeeMessage。 请求消息如下所示：  
  
    ```  
    <UPDATE_EMPLOYEE xmlns="http://schemas.microsoft.com/Sql/2008/05/TypedProcedures/dbo" />  
    ```  
  
-   要调用插入操作的请求消息**Purchase_Order**表位于 C:\TestLocation\CreatePOMessage。 请求消息如下所示：  
  
    ```  
    <Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Purchase_Order">  
      <Rows>  
        <Purchase_Order xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
          <Employee_ID>10</Employee_ID><Employee_Name>Employee_Name</Employee_Name>  
        </Purchase_Order>  
      </Rows>  
    </Insert>  
    ```  
  
    > [!NOTE]
    >  值**Employee_ID**和**Employee_Name**字段是占位符。 在运行时业务流程由插入的实际值。  
  
-   你必须已完成[步骤 3： 配置并启动应用程序](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)。  
  
### <a name="to-test-the-application"></a>测试应用程序  
  
1.  插入中的记录**员工**表。 你可以通过从 SQL Server Management Studio 中运行以下语句来实现。  
  
    ```  
    INSERT INTO [ADAPTER_SAMPLES].[dbo].[Employee] ([Name] ,[Designation] ,[Salary])  
    VALUES('John Smith' ,'Manager' ,500000)  
    ```  
  
2.  检查**员工**数据库表中的。 你将注意到，通过添加新的记录**状态**列是"0"。  
  
3.  保留刷新**员工**表记录。 你将注意到，**状态**新记录的列现在设置为"1。  
  
4.  检查**Purchase_Order**表。 你将注意到，将记录具有相同的员工姓名和指派应用时，提供在 Insert 语句中，添加到表。  
  
5.  如果你提供你的电子邮件别名中的 SMTP 端口配置，您也会收到一封电子邮件与插入操作的响应消息。  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 测试 SampleApplication 应用程序的方法是插入中的记录**员工**表。  
  
## <a name="next-steps"></a>后续步骤  
 如果测试成功，祝贺您！ 已完成[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]教程。  
  
 如果测试失败，请认真检查您所做的工作以确保您已添加所有必需的对象并已正确设置其属性。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 3： 配置并启动应用程序](../../adapters-and-accelerators/adapter-sql/step-3-configure-and-start-the-application.md)   
 [第 5 课： 部署解决方案](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)