---
title: "删除发送端口 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, examples
- examples, send ports
- send ports, deleting
- deleting, send ports
ms.assetid: e6643525-fa9f-4d39-880f-314749a68471
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2bb37ae93b45ac1721da582cc0092bda5d67999
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="remove-send-port-biztalk-server-sample"></a>删除发送端口 （BizTalk Server 示例）
删除发送端口示例演示如何取消登记，并删除其中一个或多个发送端口。  
  
> [!WARNING]
>  部署后，如果不再需要部署脚本，则应将其删除。 应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何使用 BizTalk Server WMI 提供程序执行下列操作：  
  
-   根据给定的发送端口名称，查询匹配的发送端口的列表。  
  
    > [!NOTE]
    >  通常，只有一个发送端口与给定名称匹配。  
  
-   取消登记那些发送端口。  
  
-   删除那些发送端口。  
  
-   处理所有错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例位于以下 SDK 位置中：  
  
 \<*示例路径*> \Admin\WMI\Remove 发送 Port\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的内容：<br /><br /> RemoveSendPort.vbs|VBScript 文件采用一个参数，指定一个或多个发送端口中取消和删除。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 删除发送端口示例包含你不需要生成或初始化单个 VBScript 文件。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-remove-send-port-sample"></a>若要运行删除发送端口示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*> \Admin\WMI\Remove 接收 Port\VBScript\  
  
2.  运行文件 RemoveSendPort.vbs 使用 cscript 程序中，将以下命令行自变量传递：  
  
     **\<**   
     ***SendPortName* >。** 要删除的发送端口的名称。 如果发送端口名称包含空格，则将该名称置于引号中。  
  
     例如：  
  
    ```  
    cscript RemoveSendPort.vbs "My Business Send Port"  
    ```  
  
## <a name="comments"></a>注释  
 你可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过访问 Windows WMI 对象模型的脚本都执行。  
  
 脚本文件 RemoveSendPort.vbs 包含详细的注释，使用更多有关它执行的操作的说明。 有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>另请参阅  
 [管理员-WMI （BizTalk Server 示例文件夹中）](../core/admin-wmi-biztalk-server-samples-folder.md)