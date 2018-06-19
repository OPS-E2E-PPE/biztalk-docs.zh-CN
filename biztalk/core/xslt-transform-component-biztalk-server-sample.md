---
title: XSLT 转换组件 （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
- XSLT, examples
- examples, XSLT
ms.assetid: 9152e897-4db9-4924-b37e-fd9e908dbef1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1879cb4d748e974454f929bde2018c24b5d276f2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974923"
---
# <a name="xslt-transform-component-biztalk-server-sample"></a>XSLT 转换组件（BizTalk Server 示例）
XSLT 转换组件示例演示如何编写自定义管道组件以使用 XSLT 转换 XML 消息。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例通过下列步骤来实现转换：  
  
1.  从文件夹检索 XML 文档。  
  
2.  该管道使用 Transform.xsl 将 XML 文档转换为电子邮件消息的 HTML 正文。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径\>* \Pipelines\XslTransformComponent\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|AssemblyInfo.cs|C# 程序集文件。|  
|Cleanup.bat|示例清理文件。|  
|Confirmation.xsd|示例架构文件。|  
|DocInstance.xml|要转换的示例 .xml 文件。|  
|SendHtmlMessage.btproj|BizTalk 项目。|  
|Setup.bat|配置批处理文件。|  
|Xml2HtmlSendPipeline.btp|BizTalk Server 管道文件。|  
|XslTransform.csproj|C# 项目。|  
|XslTransformComponent.sln|示例解决方案文件。|  
|XslTransformComponentBinding.XML|XML 绑定文件。|  
|XslTransformer.cs|C# 源代码。|  
|Transform.xsl|用于转换 DocInstance.xml 的 XSLT 文件。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 请按下面的过程生成并初始化 XSLT 转换组件示例。  
  
#### <a name="to-build-and-initialize-this-sample"></a>构建和初始化此示例  
  
1.  在命令窗口中，将目录更改 (**cd)** 的以下文件夹：  
  
     *\<示例路径\>* \Pipelines\XslTransformComponent  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   创建本示例中使用的输入 (\In) 和输出 (\Out) 文件夹。  
  
    -   生成新的密钥文件。  
  
    -   生成并部署 XSLT 转换组件管道。  
  
    -   将复制到生成的管道组件\<安装路径\>\Pipeline 组件文件夹。  
  
    -   创建发送端口和接收端口。  
  
    > [!NOTE]
    >  在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。  
  
    > [!NOTE]
    >  若要撤消 Setup.bat 所做的更改，必须首先从 BizTalk Server 管理 MMC 控制台停止并重新启动主机实例。 然后运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行 XSLT 转换组件示例。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  将 DocInstance.xml 复制到 \In 文件夹。  
  
2.  查看 \Out 文件夹中的结果（输出文件名为 guid.htm）。  
  
## <a name="configuring-this-sample-using-smtp"></a>配置此示例使用 SMTP  
 使用以下过程可以将 XSLT 转换组件示例配置为在 SMTP 服务器上运行。  
  
#### <a name="to-configure-this-sample-using-smtp"></a>使用 SMTP 配置本示例  
  
1.  将 XSLT 转换组件发送端口重新配置为使用 SMTP 传输类型。  
  
2.  通过更改地址 (URI) 参数来配置 SMTP 设置，使其与您的 SMTP 配置匹配。  
  
## <a name="running-this-sample-with-output-to-an-smtp-port"></a>运行本示例，并输出到 SMTP 端口  
 使用以下过程可以运行 XSLT 转换组件示例，并输出到 SMTP 端口。  
  
#### <a name="to-run-this-sample-with-output-to-an-smtp-port"></a>与输出到的 SMTP 端口运行此示例  
  
1.  将 DocInstance.xml 复制到 \In 文件夹。  
  
2.  查看配置为接收 SMTP 的收件人的邮件客户端中的结果。  
  
## <a name="see-also"></a>另请参阅  
 [管道（BizTalk Server 示例文件夹）](../core/pipelines-biztalk-server-samples-folder.md)