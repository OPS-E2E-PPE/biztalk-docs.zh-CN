---
title: "步骤 17： 创建 WSClient 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WSClient application
- message enrichment tutorial, WSClient application
- creating, WSClient application
ms.assetid: 2849cd4c-30d0-47ab-8161-fab379d5a548
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54eff7c2a455d9f1129bb40d83c002bac92841bd
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="step-17-create-the-wsclient-application"></a>步骤 17： 创建 WSClient 应用程序
WSClient.exe （Web 服务客户端） 是编写的控制台应用程序[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]，演示了如何将数据发送到作为 Web 服务与先前步骤中发布的业务流程。 WSClient 应用程序接受四个输入参数顺序： 患者的名字、 中间名分别姓氏和身份证号。 若要将患者信息发送到你的 Web 服务，请使用以下命令行语法：  
  
```  
wsclient john henry smith 123456789  
```  
  
### <a name="to-create-the-wsclient-application"></a>若要创建 WSClient 应用程序  
  
1.  在解决方案资源管理器，右键单击**解决方案 BTAHL7V22Common**，单击**添加**，然后单击**新项目**。  
  
2.  在**添加新项目**对话框中，在**项目类型**窗格中，单击**Visual C#**并在**模板**窗格中，单击**控制台应用程序**。  
  
3.  在**名称**字段中，键入**WSClient**。 在**位置**字段中，浏览到 **\<*驱动器*\>: \Tutorial**，然后单击**确定**。 解决方案资源管理器将 WSClient 添加到树中，并且 Program.cs 文件中会出现。  
  
4.  在解决方案资源管理器，右键单击**WSClient**，然后单击**添加 Web 引用**。  
  
5.  在添加 Web 引用对话框中，单击**本地计算机上的 Web 服务**。 本地计算机可用的 Web 服务，搜索，然后将其显示在列表中。  
  
6.  在本地计算机上的 Web 服务的列表中，单击**BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**，单击**Operation_1**，然后单击**添加引用**.  
  
7.  双击 Program.cs。  
  
8.  复制下面的代码，然后将其粘贴到 Program.cs 窗口：  
  
    ```  
    using System;  
  
    namespace WSClient  
    {  
       class Class1  
       {  
          [STAThread]  
          static void Main(string[] args)  
          {  
             try   
             {  
                localhost.DoorbellRoot req=new WSClient.localhost.DoorbellRoot();  
                req.FirstName=args[0];  
                req.MiddleName=args[1];  
                req.LastName=args[2];  
                req.SSN=args[3];  
                localhost.BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort sp=new WSClient.localhost.BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort();  
                sp.Operation_1(req);  
             }  
             catch (Exception ex)  
             {  
                Console.WriteLine(ex.Message);  
             }  
          }  
       }  
    }  
    ```  
  
9. 在解决方案资源管理器，右键单击**WSClient**，然后单击**生成**。 确保在输出窗口中显示一条成功消息。 如果不显示任何成功消息，解决**WSClient**。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]将可执行文件为 WSClient.exe，一个副本放到\<*驱动器*\>: \Tutorial\WSClient\bin\Debug 文件夹。  
  
 继续执行[步骤 18： 测试你的新消息扩充解决方案](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)。  
  
## <a name="see-also"></a>另请参阅  
 [消息充实教程](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)