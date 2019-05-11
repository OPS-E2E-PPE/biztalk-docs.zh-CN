---
title: 删除接收端口 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports, examples
- deleting, receive ports
- examples, receive ports
- receive ports, deleting
ms.assetid: de97d914-b8e8-4365-8041-3b455c351f86
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f39d8264e00b239eaffbb24fb53e3a0f99998720
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397940"
---
# <a name="remove-receive-port-biztalk-server-sample"></a>删除接收端口 （BizTalk Server 示例）
删除接收端口示例演示如何删除一个或多个接收端口。  
  
> [!WARNING]
>  如果不需要应在部署后删除的部署脚本。 管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何执行以下操作，使用 BizTalk Server WMI 提供程序：  
  
-   指定接收端口名称，查询匹配的接收端口的列表。  
  
    > [!NOTE]
    >  通常情况下，仅有一个接收与给定名称匹配的端口。  
  
-   删除这些接收端口。  
  
-   处理任何错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 这些示例位于以下 SDK 位置：  
  
 \<*示例路径*\>\Admin\WMI\Remove 接收 Port\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的位置：<br /><br /> RemoveReceivePort.vbs|VBScript 文件，采用一个参数，指定一个或多个接收端口，以删除。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 删除接收端口示例由一个不需要生成或初始化的 VBScript 文件组成。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  在命令窗口中，导航到以下文件夹：  
  
     \<*Samples Path*\>\Admin\WMI\Remove Receive Port\VBScript\  
  
2.  运行文件 RemoveReceivePort.vbs 使用 cscript 程序，并传递以下命令行参数：  
  
     **\<** ***ReceivePortName* \>** 。 若要删除的接收端口的名称。 如果接收端口名称包含空格，将名称括起来。  
  
     例如：  
  
    ```  
    cscript RemoveReceivePort.vbs "My Business Receive Port"  
    ```  
  
## <a name="comments"></a>注释  
 可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过使用访问 Windows WMI 对象模型的脚本都执行。  
  
 脚本文件 RemoveReceivePort.vbs 包含详细的注释了进一步说明，它执行的操作。 有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)