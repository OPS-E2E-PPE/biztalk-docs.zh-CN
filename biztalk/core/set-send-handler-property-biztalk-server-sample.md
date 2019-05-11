---
title: 设置发送处理程序属性 （BizTalk Server 示例） |Microsoft Docs
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
ms.openlocfilehash: b8d1abddd497ad1f6d20c18bf7e5ff580b1ddc1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393272"
---
# <a name="set-send-handler-property-biztalk-server-sample"></a>设置发送处理程序属性 （BizTalk Server 示例）
设置发送处理程序属性示例演示如何设置简单邮件传输协议 (SMTP) 发送处理程序的 XML 配置信息。  
  
> [!WARNING]
>  如果不需要应在部署后删除的部署脚本。 管理脚本和其他必须保持的脚本应受 ACL 并加以密切监视。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 构成本示例的脚本文件中的 Visual Basic Scripting Edition (VBScript) 脚本演示如何执行以下操作，使用 BizTalk Server WMI 提供程序：  
  
-   给定的发送处理程序名称，查询匹配的发送处理程序的列表。  
  
-   设置 SMTP 发送处理程序的 XML 配置信息。  
  
-   处理任何错误，以便向用户返回有意义的信息。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 示例文件位于以下 SDK 位置：  
  
 \<*示例路径*\>\Admin\WMI\Set Send Handler Property\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|\VBScript 文件夹的位置：<br /><br /> ConfigureSMTP.vbs|VBScript 文件，采用参数指定了 SMTP 发送处理程序和 From 电子邮件地址。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 设置发送处理程序属性示例包含一个 VBScript 文件，不需生成或初始化文件。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-set-send-handler-property-sample"></a>若要运行设置发送处理程序属性示例  
  
1.  在命令窗口中，导航到以下文件夹：  
  
     \<*示例路径*\>\Admin\WMI\Set Send Handler Property\VBScript\  
  
2.  运行文件 ConfigureSMTP.vbs 使用 cscript 程序，并传递以下命令行参数：  
  
    -   **\<** ***SMTPServerName* \>.** 将用于发送邮件的 SMTP 服务器的名称。  
  
    -   **\<** ***FromEmailAddress* \>。** 电子邮件地址将用作发件人地址。  
  
         例如：  
  
        ```  
        cscript ConfigureSMTP.vbs MyBusinessSMTPServer someone@example.com  
        ```  
  
## <a name="comments"></a>注释  
 可以在 BizTalk Server 管理控制台中执行的所有任务也可以通过使用访问 Windows WMI 对象模型的脚本都执行。  
  
 ConfigureSMTP.vbs 脚本文件包含详细的注释了进一步说明，它执行的操作。 有关详细信息，请参阅在 Windows Management Instrumentation [ http://go.microsoft.com/fwlink/?LinkId=21102 ](http://go.microsoft.com/fwlink/?LinkId=21102)。  
  
## <a name="see-also"></a>请参阅  
 [Admin-WMI（BizTalk Server 示例文件夹）](../core/admin-wmi-biztalk-server-samples-folder.md)