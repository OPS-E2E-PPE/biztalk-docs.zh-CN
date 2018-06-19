---
title: 步骤 1： 为 UPDATE_EMPLOYEE 创建请求消息存储过程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dd975d9-4b38-46e0-a926-4b325b0d7b5e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e30225b79b14ffc237798ddde6f3fe40fb4aea9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965987"
---
# <a name="step-1-create-the-request-message-for-updateemployee-stored-procedure"></a>步骤 1： 为 UPDATE_EMPLOYEE 创建请求消息存储过程
![2 的第 1 步](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")  
  
 **完成时间：** 10 分钟  
  
 **目标：** 在此步骤中，你可以将 C# 类库项目添加到你的解决方案。 此库创建的内存中请求消息**UPDATE_EMPLOYEE**存储过程。 在后续步骤中，业务流程将此消息发送到 SQL Server 来执行存储的过程。  
  
## <a name="prerequisites"></a>先决条件  
 你必须已完成中的步骤[第 2 课： 接收和筛选器通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)。  
  
### <a name="to-create-a-request-message-for-updateemployee-stored-procedure"></a>若要针对 UPDATE_EMPLOYEE 创建请求的邮件存储过程  
  
1.  将 Visual C# 类库项目添加到你的解决方案。 有关项目的名称，键入`UpdateEmployeeMessageCreator`。  
  
2.  重命名**Class1.cs**到**UpdateEmployeeMessageCreator.cs**。  
  
3.  将下面的代码复制到.cs 文件中：  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Xml;  
    using System.IO;  
  
    namespace UpdateEmployeeMessageCreator  
    {  
        public class UpdateEmployeeMessageCreator  
        {  
            private static XmlDocument Message;  
            private static string XmlFileLocation;  
            private static string ResponseDoc;  
  
            public static XmlDocument XMLMessageCreator()  
            {  
                XmlFileLocation = "C:\\TestLocation\\CreateEmployeeMessage";  
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
  
     此代码段应该接收的请求消息**UPDATE_EMPLOYEE**存储存在于 C:\TestLocation\CreateEmployeeMessage 的过程。 该代码使用请求消息以在运行时创建的类似的请求消息。  
  
4.  向项目添加一个强名称密钥文件。 请参阅[系统必备组件来创建 SQL 应用程序使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)。  
  
    1.  在解决方案资源管理器，右键单击**UpdateEmployeeMessageCreator**项目，，然后单击**属性**。  
  
    2.  在**属性**窗口中，单击**签名**。  
  
    3.  在**签名**选项卡上，选择**对程序集签名**复选框。  
  
    4.  从**选择强名称密钥文件**列表中，单击**\<浏览\>**。  
  
    5.  导航到您在其中创建强名称密钥文件的文件夹，然后单击**打开**。  
  
    6.  单击**保存**在标准菜单栏上。 关闭**属性**窗口。  
  
5.  生成此项目。 右键单击项目，并依次**生成**。  
  
6.  将此项目的引用添加到解决方案中的 BizTalk 项目。  
  
    1.  在解决方案资源管理器，展开 BizTalk 项目，右键单击**引用**，然后单击**添加引用**。  
  
    2.  在**添加引用**对话框中，单击**项目**选项卡。  
  
    3.  从项目名称的列表，选择**UpdateEmployeeMessageCreator**，单击**添加**，然后单击**确定**。  
  
7.  生成项目创建的项目的 \bin\Debug 文件夹下的程序集 DLL。 你必须将此 DLL 添加到全局程序集缓存 (GAC) 中。  
  
    1.  启动 Visual Studio 命令提示符。  
  
    2.  从命令提示符处，导航到的 \bin\Debug\ 文件夹**UpdateEmployeeMessageCreator**项目。  
  
    3.  在命令提示符处运行以下命令：  
  
        ```  
        gacutil /i UpdateEmployeeMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a>内容回顾  
 在此步骤中，你添加 UpdateEmployeeMessageCreator 类库项目的创建在运行时的请求消息。 在 BizTalk 项目中添加此项目的引用，并还添加到 GAC 的程序集 DLL。  
  
## <a name="next-steps"></a>后续步骤  
 将请求消息发送到 SQL Server 和中所述接收的响应，[步骤 2： 将请求消息发送到 SQL Server 和接收响应](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)。  
  
## <a name="see-also"></a>另请参阅  
 [第 3 课：执行存储过程以选择新添加的员工](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)