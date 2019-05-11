---
title: 将信息写入到事件日志 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d7398dc-29d8-4a7a-bab4-c8f128b47dca
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae31f6c09e8ffaeb562aa5bd5380dd533173cad0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261987"
---
# <a name="writing-information-to-the-event-log"></a>将信息写入到事件日志
您可能想要通过默认应用程序日志或自定义事件日志写入信息来监视 BizTalk 应用程序中的不同业务流程的进度。 写入事件日志可在以下方案中：  
  
-   你想要使用由 Windows 提供工具以标准方式访问应用程序消息。  
  
-   你想要存档包含更完整的历史记录的服务器环境的其他电子邮件的信息。  
  
-   您希望能够监视应用程序事件日志中使用交互的工具。  
  
> [!NOTE]
>  System.Diagnostics.EventLog.WriteEntry 方法对消息字符串的大小限制。 如果消息字符串超过 32766 个字节，将收到异常。  
  
## <a name="writing-to-the-application-log"></a>向应用程序日志写入  
 您可以在应用程序日志或任何其他日志在代码中使用写入**System.Diagnostics.EventLog**在下面的示例所示：  
  
```  
System.Diagnostics.EventLog.WriteEntry("Orchestration Debug", System.String.Format("The Value = {0}", iResult));  
```  
  
 类似，您还可以执行，  
  
```  
EventLog appLog = new EventLog();   
appLog.Source = "This Application's Name";  
appLog.WriteEntry("An entry to the Application event log.");  
```  
  
 如果使用自定义日志，则应使用**SourceExists**方法，以确保它存在，才能向其中写入。  
  
## <a name="writing-to-a-custom-log"></a>写入自定义日志  
 写入自定义日志是类似于写入应用程序日志，必须先创建自定义日志的异常。 若要创建自定义日志的代码非常简单：  
  
```  
// Create the source, if it does not already exist. if(!EventLog.SourceExists("MySource"))   
{   
  //An event log source should not be created and immediately used.  
  //There is a latency time to enable the source, it should be created  
  //prior to executing the application that uses the source.  
  EventLog.CreateEventSource("MySource", "MyNewLog");  
}  
```  
  
 但是，不应假定，将创建一个新的事件日志的安全特权的帐户下运行你的代码。 创建事件日志需要管理员权限，并应在单独的实用程序或完成，理想情况下，作为.msi 安装的一部分。 有关使用导出的.msi 安装使用自定义脚本的详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。