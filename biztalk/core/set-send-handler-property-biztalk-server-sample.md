---
title: 设置发送处理程序属性 （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, examples
- examples, SMTP adapters
- send handlers, properties
ms.assetid: eb6ae2f2-528f-44ec-bca4-f37006893ff2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f783f465feff207ae1759ea358b0b848ccc0f4c3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974579"
---
# <a name="set-send-handler-property-biztalk-server-sample"></a>设置发送处理程序属性 （BizTalk Server 示例）
“设置发送处理程序属性”示例演示如何为简单邮件传输协议 (SMTP) 发送处理程序设置 XML 配置信息。  
  
> [!WARNING]
>  部署后，如果不再需要部署脚本，则应将其删除。 应通过 ACL 确保必须保留的管理脚本和其他脚本的安全并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何使用 BizTalk Server WMI 提供程序执行下列操作：  
  
-   根据给定的发送处理程序名称，查询匹配的发送处理程序的列表。  
  
-   设置 SMTP 发送处理程序的 XML 配置信息。  
  
-   处理所有错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例文件位于以下 SDK 位置：  
  
 \<*示例路径*\>\Admin\WMI\Set 发送处理程序 Property\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的内容：<br /><br /> ConfigureSMTP.vbs|VBScript 文件，其参数指定了 SMTP 发送处理程序和发件人电子邮件地址。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 “设置发送处理程序属性”示例仅由一个 VBScript 文件组成，您无需生成或初始化此文件。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-set-send-handler-property-sample"></a>运行“设置发送处理程序属性”示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*\>\Admin\WMI\Set 发送处理程序 Property\VBScript\  
  
2.  使用 cscript 程序运行文件 ConfigureSMTP.vbs，并传递以下命令行参数：  
  
    -   **\<** ***SMTPServerName* \>。** 将用于发送邮件的 SMTP 服务器的名称。  
  
    -   **\<** ***FromEmailAddress* \>。** 将用作发件人地址的电子邮件地址。  
  
         例如：  
  
        ```  
        cscript ConfigureSMTP.vbs MyBusinessSMTPServer someone@example.com  
        ```  
  
## <a name="comments"></a>注释  
 你可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过访问 Windows WMI 对象模型的脚本都执行。  
  
 ConfigureSMTP.vbs 脚本文件包含详细注释，对其执行的操作做了进一步说明。 有关详细信息，请参阅在 Windows Management Instrumentation [http://go.microsoft.com/fwlink/?LinkId=21102](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>另请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)