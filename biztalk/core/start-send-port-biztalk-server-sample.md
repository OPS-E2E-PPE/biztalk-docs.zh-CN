---
title: 启动发送端口 （BizTalk Server 示例） |Microsoft Docs
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
- send ports, starting
ms.assetid: 84e54c9e-e9e8-4bb2-a191-20c29e127dae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ca8ab34acb7fb49164a3e0cd0ff99f765e41912
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393058"
---
# <a name="start-send-port-biztalk-server-sample"></a>启动发送端口 （BizTalk Server 示例）
启动发送端口示例演示如何启动发送端口并使用文件适配器时可以选择设置主传输地址。  
  
> [!WARNING]
>  如果不需要应在部署后删除的部署脚本。 管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何执行以下操作，使用 BizTalk Server WMI 提供程序：  
  
-   给定的发送端口名称，查询匹配的发送端口的列表。  
  
    > [!NOTE]
    >  通常情况下，将仅有一个与给定名称匹配的发送端口。  
  
-   设置主传输地址为这些发送端口 （相对于的安装路径）。  
  
-   启动这些发送端口。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 示例文件位于以下 SDK 位置：  
  
 \<*示例路径*\>\Admin\WMI\Start 发送 Port\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的位置：<br /><br /> StartSendPort.vbs|VBScript 文件，采用参数指定的发送端口，若要开始，并 （可选） 与该端口相关联的主传输地址的新值。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 启动发送端口示例由一个不需要生成或初始化的 VBScript 文件组成。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  在命令窗口中，导航到以下文件夹：  
  
     \<*Samples Path*\>\Admin\WMI\Start Send Port\VBScript\  
  
2.  运行的 StartSendPort.vbs 文件使用 cscript 程序中，传递下列命令行参数，第二个是可选的：  
  
    -   **\<** ***SendPortName* \>。** 要启动的发送端口的名称。 如果发送端口名称包含空格，将名称括起来。  
  
    -   **\<** ***PrimaryTransportAddress* \>。** 主传输地址，相对于的产品安装位置，你可以通过指定此参数。 如果主适配器地址包含空格，将名称括起来。  
  
         例如：  
  
        ```  
        cscript StartSendPort.vbs "My Business Send Port" SDK\Samples\HelloWorld\Out\%MessageID%.xml  
        ```  
  
## <a name="comments"></a>注释  
 可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过使用访问 Windows WMI 对象模型的脚本都执行。  
  
 StartSendPort.vbs 脚本文件包含详细的注释了进一步说明，它执行的操作。 有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)