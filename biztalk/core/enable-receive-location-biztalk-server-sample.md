---
title: 启用接收位置 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, examples
- receive locations, enabling
- examples, receive locations
ms.assetid: dd04b38a-634d-4c9a-b31a-2f226fa91d19
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f41353b17a3e393d865c381a5f6b6b15cb676cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349719"
---
# <a name="enable-receive-location-biztalk-server-sample"></a>启用接收位置 （BizTalk Server 示例）
启用接收位置示例演示如何启用接收位置和 （可选） 设置该接收位置的入站传输 URL。  
  
> [!WARNING]
>  如果不需要应在部署后删除的部署脚本。 管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 构成本示例的脚本文件中的 Microsoft Visual Basic Scripting Edition (VBScript) 脚本演示如何执行以下操作，使用 BizTalk Server WMI 提供程序：  
  
-   在给定接收端口名称和接收位置，查询匹配的接收位置的列表。  
  
-   设置接收位置 （相对于的安装路径） 的入站传输 URL。  
  
-   启用接收位置。  
  
-   处理任何错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例位于以下 SDK 位置中：  
  
 \<*示例路径*\>\Admin\WMI\Enable 接收位置 \  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的位置：<br /><br /> EnableRecLoc.vbs|VBScript 文件，采用参数指定接收位置，若要启用，并 （可选） 与该接收位置相关联的入站传输 URL 的新值。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 启用接收位置示例包含一个 VBScript 文件，不需生成或初始化文件。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  在命令窗口中，导航到以下文件夹：  
  
     \<*示例路径*\>\Admin\WMI\Enable 接收 Location\VBScript\  
  
2.  运行文件 EnableRecLoc.vbs 使用 cscript 程序中，传递下列命令行参数，第三个是可选的：  
  
    -   **\<** ***ReceivePortName* \>.** 包含要启用的接收位置的接收端口的名称。 如果接收端口名称包含空格，将名称括起来。  
  
    -   **\<** ***ReceiveLocationName* \>.** 中指定的接收端口启用的接收位置的名称。 如果接收位置名称包含空格，将名称括起来。  
  
    -   **\<** ***InboundTransportURI* \>.** 接收适配器 URI，相对于的产品安装位置，你可以通过指定此参数。 如果入站的适配器 URI 包含空格，则 URI 将置于引号中。  
  
         例如：  
  
        ```  
        cscript EnableRecLoc.vbs "My Business Receive Port" MyBusinessReceiveLocation  
        ```  
  
         -或-  
  
        ```  
        cscript EnableRecLoc.vbs MyBusinessReceivePort "My Business Receive Location" SDK\Samples\HelloWorld\In\*.xml  
        ```  
  
## <a name="comments"></a>注释  
 可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过使用访问 Windows WMI 对象模型的脚本都执行。  
  
 脚本文件 EnableRecLoc.vbs 包含详细的注释了进一步说明，它执行的操作。  
  
 有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)