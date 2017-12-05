---
title: "开始发送端口 （BizTalk Server 示例） |Microsoft 文档"
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
- send ports, starting
ms.assetid: 84e54c9e-e9e8-4bb2-a191-20c29e127dae
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f293d00848c32f6b519349543c8a39824d9bca8c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="start-send-port-biztalk-server-sample"></a>开始发送端口 （BizTalk Server 示例）
启动发送端口示例演示如何在使用 FILE 适配器时启动发送端口和选择设置主传输地址。  
  
> [!WARNING]
>  部署后，如果不再需要部署脚本，则应将其删除。 应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何使用 BizTalk Server WMI 提供程序执行下列操作：  
  
-   根据给定的发送端口名称，查询匹配的发送端口的列表。  
  
    > [!NOTE]
    >  通常，只有一个发送端口与给定名称匹配。  
  
-   为这些发送端口设置主传输地址（相对于安装路径）。  
  
-   启动这些发送端口。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例文件位于以下 SDK 位置：  
  
 \<*示例路径*\>\Admin\WMI\Start 发送 Port\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的内容：<br /><br /> StartSendPort.vbs|VBScript 文件，采用指定要启动的发送端口以及与此端口关联的主传输地址的新值（可选）的参数。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 启动发送端口示例由一个 VBScript 文件组成，您无需生成或初始化此文件。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*\>\Admin\WMI\Start 发送 Port\VBScript\  
  
2.  使用 cscript 程序运行 StartSendPort.vbs 文件，传递下列命令行参数，其中第二个参数是可选的：  
  
    -   **\<** ***SendPortName* \>。** 要启动的发送端口的名称。 如果发送端口名称包含空格，则将该名称置于引号中。  
  
    -   **\<** ***PrimaryTransportAddress* \>。** 相对于产品安装位置的主传输地址，通过指定此参数，您可以更改此地址。 如果主适配器地址包含空格，则将该名称置于引号中。  
  
         例如：  
  
        ```  
        cscript StartSendPort.vbs "My Business Send Port" SDK\Samples\HelloWorld\Out\%MessageID%.xml  
        ```  
  
## <a name="comments"></a>注释  
 你可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过访问 Windows WMI 对象模型的脚本都执行。  
  
 StartSendPort.vbs 脚本文件包含详细注释，对其执行的操作做了进一步说明。 有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>另请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)