---
title: 第 1 步：为在 Purchase_Order 表的插入操作创建请求消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fde018d8-9d9a-42ea-8ee9-e3632450b9d7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ef474e20b44d319ca4ac1d764dfa46b3062231
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367809"
---
# <a name="step-1-create-the-request-message-for-insert-operation-on-purchaseorder-table"></a>第 1 步：为在 Purchase_Order 表的插入操作创建请求消息
![步骤 1，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **若要完成的时间：** 10 分钟。  
  
 **目标：** 在此步骤中，您将添加C#到你的解决方案的类库项目。 此库上创建插入操作的内存中请求消息**Purchase_Order**表。 在后续步骤中，业务流程发送到 SQL Server 以在表中插入记录此消息。  
  
## <a name="prerequisites"></a>先决条件  
 你必须完成中的步骤[第 3 课：执行存储的过程以选择新添加的员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)。  
  
### <a name="to-create-a-request-message-for-insert-operation"></a>若要创建用于插入操作的请求消息  
  
1.  将视觉对象添加C#到你的解决方案的类库项目。 对于项目的名称，键入`UpdatePOMessageCreator`。  
  
2.  重命名**Class1.cs**到**UpdatePOMessageCreator.cs**。  
  
3.  将以下代码复制到.cs 文件中：  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Xml;  
    using System.IO;  
  
    namespace UpdatePOMessageCreator  
    {  
        public class UpdatePOMessageCreator  
        {  
            private static XmlDocument Message;  
            private static string XmlFileLocation;  
            private static string ResponseDoc;  
  
            public static XmlDocument XMLMessageCreator()  
            {  
                XmlFileLocation = "C:\\TestLocation\\CreatePOMessage";  
                try  
                {  
                    ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                    Console.WriteLine("EXCEPTION: " + ex.ToString());  
                    throw ex;  
                }  
  
                //Create Message From XML  
                Message = new XmlDocument();  
  
                Message.PreserveWhitespace = true;  
  
                Message.Load(ResponseDoc);  
  
                return Message;  
            }  
        }  
    }  
  
    ```  
  
     此代码片段上需要用于插入操作的请求消息**Purchase_Order**要 C:\TestLocation\CreatePOMessage 处存在的表。 代码使用请求消息在运行时创建类似的请求消息。  
  
4.  向项目添加强名称密钥文件。 有关创建强名称密钥文件的说明，请参阅[先决条件若要创建 SQL 应用程序使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)。  
  
    1.  在解决方案资源管理器，右键单击**UpdatePOMessageCreator**项目，然后单击**属性**。  
  
    2.  在中**属性**窗口中，单击**签名**。  
  
    3.  在中**签名**选项卡上，选择**程序集签名**复选框。  
  
    4.  从**选择一个强名称密钥文件**列表中，单击**\<浏览\>**。  
  
    5.  导航到在其中创建强名称密钥文件的文件夹，然后单击**打开**。  
  
    6.  单击**保存**上**标准**菜单栏。 关闭**属性**窗口。  
  
5.  生成项目。 右键单击项目，然后单击**生成**。  
  
6.  将此项目的引用添加到解决方案中的 BizTalk 项目。  
  
    1.  在解决方案资源管理器，展开 BizTalk 项目中，右键单击**引用**，然后单击**添加引用**。  
  
    2.  在中**添加引用**对话框中，单击**项目**选项卡。  
  
    3.  从项目名称的列表中选择**UpdatePOMessageCreator**，单击**添加**，然后单击**确定**。  
  
7.  生成项目创建项目的 \bin\Debug 文件夹下的程序集 DLL。 必须将此 DLL 添加到全局程序集缓存 (GAC) 中。  
  
    1.  启动 Visual Studio 命令提示符。  
  
    2.  从命令提示符处，导航到的 \bin\Debug\ 文件夹**UpdatePOMessageCreator**项目。  
  
    3.  在命令提示符处运行以下命令：  
  
        ```  
        gacutil /i UpdatePOMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，您添加了在运行时创建请求消息的 UpdatePOMessageCreator 类库项目。 在 BizTalk 项目中添加对此项目的引用和也添加到 GAC 的程序集 DLL。  
  
## <a name="next-steps"></a>后续步骤  
 在映射到插入操作的请求消息的 UPDATE_EMPLOYEE 存储过程的响应消息**Purchaser_Order**表。  
  
## <a name="see-also"></a>请参阅  
 [步骤 2：将 UPDATE_EMPLOYEE 响应消息插入操作请求消息映射](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)   
 [第 4 课：在采购订单表中执行插入操作](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)