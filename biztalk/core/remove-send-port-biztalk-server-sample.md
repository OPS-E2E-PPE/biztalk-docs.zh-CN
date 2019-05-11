---
title: 删除发送端口 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, examples
- examples, send ports
- send ports, deleting
- deleting, send ports
ms.assetid: e6643525-fa9f-4d39-880f-314749a68471
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4edb148d1627d596f98684b09d18da111b4e435c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397934"
---
# <a name="remove-send-port-biztalk-server-sample"></a>删除发送端口 （BizTalk Server 示例）
删除发送端口示例演示如何取消登记和删除一个或多个发送端口。  
  
> [!WARNING]
>  如果不需要应在部署后删除的部署脚本。 管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何执行以下操作，使用 BizTalk Server WMI 提供程序：  
  
-   给定的发送端口名称，查询匹配的发送端口的列表。  
  
    > [!NOTE]
    >  通常情况下，将仅有一个与给定名称匹配的发送端口。  
  
-   取消登记这些发送端口。  
  
-   删除这些发送端口。  
  
-   处理任何错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例位于以下 SDK 位置中：  
  
 \<*示例路径*\>\Admin\WMI\Remove 发送 Port\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的位置：<br /><br /> RemoveSendPort.vbs|VBScript 文件，采用一个参数，指定一个或多个发送端口将取消登记和删除。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 删除发送端口示例由一个 VBScript 文件，不需要生成或初始化组成。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-remove-send-port-sample"></a>若要运行删除发送端口示例  
  
1.  在命令窗口中，导航到以下文件夹：  
  
     \<*Samples Path*\>\Admin\WMI\Remove Receive Port\VBScript\  
  
2.  运行文件 RemoveSendPort.vbs 使用 cscript 程序，并传递以下命令行参数：  
  
     **\<** ***SendPortName* \>。** 若要删除的发送端口的名称。 如果发送端口名称包含空格，将名称括起来。  
  
     例如：  
  
    ```  
    cscript RemoveSendPort.vbs "My Business Send Port"  
    ```  
  
## <a name="comments"></a>注释  
 可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过使用访问 Windows WMI 对象模型的脚本都执行。  
  
 脚本文件 RemoveSendPort.vbs 包含详细的注释了进一步说明，它执行的操作。 有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)