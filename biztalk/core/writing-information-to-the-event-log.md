---
title: "向事件日志中写入信息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d7398dc-29d8-4a7a-bab4-c8f128b47dca
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f848cafd6ee9247511db3b9a6dad7dc5da91236b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="writing-information-to-the-event-log"></a>将信息写入事件日志
您可能要通过将信息写入默认的应用程序日志或自定义的事件日志，监控您的 BizTalk 应用程序内的不同业务流程的进度。 在以下情况下将信息写入事件日志可能会很有用：  
  
-   您要使用 Windows 提供的工具以标准方法访问应用程序消息。  
  
-   您想要将来自服务器环境的其他消息与信息一起存档，以便获得更完整的历史记录。  
  
-   您想要能够使用与事件日志交互的工具监控您的应用程序。  
  
> [!NOTE]
>  System.Diagnostics.EventLog.WriteEntry 方法对消息字符串有大小限制。 如果消息字符串超过 32766 个字节，则会发生异常。  
  
## <a name="writing-to-the-application-log"></a>写入应用程序日志  
 你可以写入应用程序日志或任何其他日志从你的代码通过使用**System.Diagnostics.EventLog**在下面的示例所示：  
  
```  
System.Diagnostics.EventLog.WriteEntry("Orchestration Debug", System.String.Format("The Value = {0}", iResult));  
```  
  
 同样，您还可以写入以下内容：  
  
```  
EventLog appLog = new EventLog();   
appLog.Source = "This Application's Name";  
appLog.WriteEntry("An entry to the Application event log.");  
```  
  
 如果你使用的自定义日志，则应使用**SourceExists**方法，以确保它存在之前向其中写入。  
  
## <a name="writing-to-a-custom-log"></a>写入自定义日志  
 写入自定义日志类似于写入应用程序日志，但有一个例外，就是您必须首先创建自定义日志。 用于创建自定义日志的代码十分简单：  
  
```  
// Create the source, if it does not already exist. if(!EventLog.SourceExists("MySource"))   
{   
  //An event log source should not be created and immediately used.  
  //There is a latency time to enable the source, it should be created  
  //prior to executing the application that uses the source.  
  EventLog.CreateEventSource("MySource", "MyNewLog");  
}  
```  
  
 但是，您不应假定代码将基于具有创建新事件日志的安全权限的帐户运行。 创建事件日志需要管理员权限，并且应在单独的实用程序中完成，最好作为 .msi 安装的一部分完成。 有关进行无导出的.msi 安装使用自定义脚本的详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。