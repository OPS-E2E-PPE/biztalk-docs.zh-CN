---
title: "启用接收位置 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enabling
- examples, receive locations
ms.assetid: dd04b38a-634d-4c9a-b31a-2f226fa91d19
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd2df85f051285e999660dc3765855d22c708939
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="enable-receive-location-biztalk-server-sample"></a>启用接收位置 （BizTalk Server 示例）
启用接收位置示例演示如何启用接收位置和 （可选） 设置对该接收位置的入站传输 URL。  
  
> [!WARNING]
>  部署后，如果不再需要部署脚本，则应将其删除。 应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 Microsoft Visual Basic Scripting Edition (VBScript) 脚本中的脚本文件的构成此示例演示如何执行以下操作使用 BizTalk Server WMI 提供程序：  
  
-   给定接收端口名称和接收位置，查询匹配的接收位置的列表。  
  
-   设置为接收位置 （相对于的安装路径） 的入站传输 URL。  
  
-   启用接收位置。  
  
-   处理所有错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例位于以下 SDK 位置中：  
  
 \<*示例路径*\>\Admin\WMI\Enable 接收位置 \  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的内容：<br /><br /> EnableRecLoc.vbs|采用参数的 VBScript 文件指定接收位置启用，并 （可选） 与该接收位置关联的入站传输 url 的新值。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 启用接收位置示例包含一个 VBScript 文件不需要生成或初始化。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*\>\Admin\WMI\Enable 接收 Location\VBScript\  
  
2.  运行该文件使用 cscript 程序传递以下命令行自变量，而第三个是可选的 EnableRecLoc.vbs:  
  
    -   **\<** ***ReceivePortName* \>。** 包含要启用的接收位置的接收端口的名称。 如果接收端口名称包含空格，请将名称括在引号中。  
  
    -   **\<** ***ReceiveLocationName* \>。** 位于要启用的指定接收端口中的接收位置的名称。 如果接收位置名称包含空格，则将该名称置于引号中。  
  
    -   **\<** ***InboundTransportURI* \>。** 接收适配器 URI，相对于产品安装位置的主传输地址，通过指定该参数，您可以更改此地址。 如果入站的适配器 URI 包含空格，括起来的 URI。  
  
         例如：  
  
        ```  
        cscript EnableRecLoc.vbs "My Business Receive Port" MyBusinessReceiveLocation  
        ```  
  
         -或者-  
  
        ```  
        cscript EnableRecLoc.vbs MyBusinessReceivePort "My Business Receive Location" SDK\Samples\HelloWorld\In\*.xml  
        ```  
  
## <a name="comments"></a>注释  
 你可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过访问 Windows WMI 对象模型的脚本都执行。  
  
 脚本文件 EnableRecLoc.vbs 包含详细的注释，使用更多有关它执行的操作的说明。  
  
 有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>另请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)