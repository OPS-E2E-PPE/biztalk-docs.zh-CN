---
title: "删除接收端口 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, examples
- deleting, receive ports
- examples, receive ports
- receive ports, deleting
ms.assetid: de97d914-b8e8-4365-8041-3b455c351f86
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d15442da8afd4829245b742bdd45af8f7d1f832
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="remove-receive-port-biztalk-server-sample"></a>删除接收端口 （BizTalk Server 示例）
删除接收端口示例演示了如何删除一个或多个接收端口。  
  
> [!WARNING]
>  部署后，如果不再需要部署脚本，则应将其删除。 应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何使用 BizTalk Server WMI 提供程序执行下列操作：  
  
-   给定接收端口名称，有关匹配接收端口的列表的查询。  
  
    > [!NOTE]
    >  通常情况下，将仅有一个接收与给定名称匹配的端口。  
  
-   删除那些接收端口。  
  
-   处理所有错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 这些示例位于以下 SDK 的位置：  
  
 \<*示例路径*\>\Admin\WMI\Remove 接收 Port\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的内容：<br /><br /> RemoveReceivePort.vbs|VBScript 文件采用一个参数，指定一个或多个接收删除的端口。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 删除接收端口示例包含一个 VBScript 文件不需要生成或初始化。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*\>\Admin\WMI\Remove 接收 Port\VBScript\  
  
2.  运行文件 RemoveReceivePort.vbs 使用 cscript 程序中，将以下命令行自变量传递：  
  
     **\<** ***ReceivePortName* \>** 。 接收端口，若要删除的名称。 如果接收端口名称包含空格，请将名称括在引号中。  
  
     例如：  
  
    ```  
    cscript RemoveReceivePort.vbs "My Business Receive Port"  
    ```  
  
## <a name="comments"></a>注释  
 你可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过访问 Windows WMI 对象模型的脚本都执行。  
  
 脚本文件 RemoveReceivePort.vbs 包含详细的注释，使用更多有关它执行的操作的说明。 有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>另请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)