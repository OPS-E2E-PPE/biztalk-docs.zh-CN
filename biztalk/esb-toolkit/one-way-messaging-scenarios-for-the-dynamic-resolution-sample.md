---
title: 动态解析示例的单向消息传递方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 38237840-e957-4298-84c9-700ec72f2bc5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8296c46561a8afa928033ae6002e3de621170234
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296669"
---
# <a name="one-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a>动态解析示例的单向消息传递方案
本主题演示如何能够运行的单向消息传递方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态解析示例。  
  
 **若要运行动态解析示例的单向消息传递方案**  
  
1.  首次运行此示例之前，请确保接收位置 URL 指向相应的目录。 指定源子文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\In DynamicResolution_FILE 接收位置。 此外，请确保存在名为 DynamicResolutionOneWay 动态发送端口。  
  
    > [!NOTE]
    >  动态解析示例使用动态解决机制将消息发送到输出文件夹，FTP 站点或 MQSeries 队列。 这是此示例未定义静态发送端口的原因。 动态解析组件解析检索的输出 URL 和适配器提供程序框架调用 ESBReceiveXml 管道中，在 DynamicResolution_FILE 配置时接收位置。  
  
2.  如果 GlobalBank.ESB 应用程序尚未运行，使用 Microsoft BizTalk 管理控制台来启动它。  
  
3.  决定你想要执行的示例。 所有单向消息传送 （除了使用 XPATH 解析程序的一个） 的示例使用 NAOrderDoc.xml 位于 \Source\Samples\DynamicResolution\Test\Data 的文件夹中的文件输入到名为 DynamicResolution_FILE 接收位置。 有七个单向消息传送示例，每个由唯一绑定文件。 下表列出了这些示例中，与其关联的绑定文件和说明。  
  
    |文件入站到出站使用静态冲突解决程序的文件|  
    |-------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |将地图静态处接收端口设置。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
  
    |文件入站到出站使用 UDDI 冲突解决程序的文件|  
    |-----------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |将地图静态处接收端口设置。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
  
    |文件入站到出站使用 UDDI 冲突解决程序通过 UDDI 服务密钥的文件|  
    |----------------------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |将地图静态处接收端口设置。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
  
    > [!NOTE]
    >  对于前面的示例中，你必须将绑定文件中的服务密钥更改为一个目标 UDDI 服务器上存在。  
  
    |文件的入站到 FTP 出站使用静态冲突解决程序|  
    |------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |将地图静态处接收端口设置。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
  
    |文件的入站到 FTP 出站使用静态解析程序和 ENDPOINTCONFIG 参数|  
    |-----------------------------------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |将地图静态处接收端口设置。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
    |将传递要设置的适配器提供程序的其他名称/值对。|  
  
    |文件的入站到 MQS 出站使用静态冲突解决程序|  
    |------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |将地图静态处接收端口设置。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
  
    |文件入站到出站使用 XPATH 冲突解决程序的文件|  
    |------------------------------------------------------------|  
    |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
    |将地图静态处接收端口设置。|  
    |终结点解析时，在接收位置使用 ESB 调度程序。|  
    |使用消息中的信息来确定相应的终结点。 你可以使用此示例中的测试文件是 NAOrderDoc_XPATH_FILE.xml、 NAOrderDoc_XPATH_FTP.xml 和 NAOrderDoc_XPATH_MQS.xml。|  
  
4.  导入你想要执行到 GlobalBank.ESB 应用程序的消息传送示例的绑定文件。  
  
5.  在 Windows 资源管理器，打开文件夹 \Source\Samples\DynamicResolution\Test\Data，并将相应的输入的文件复制到文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\In。 你使用的文件取决于您决定要执行的示例：  
  
    -   对于 XPATH 示例中，使用以下文件之一： NAOrderDoc_XPATH_FILE.xml、 NAOrderDoc_XPATH_FTP.xml 或 NAOrderDoc_XPATH_MQS.xml。  
  
    -   对于所有其他示例，请使用文件 NAOrderDoc.xml。  
  
6.  查看已发送邮件的适当位置。 位置取决于你使用的绑定文件。 示例如下：  
  
    -   与 FTP 出站示例的文件入站消息传送到名为 Out 的 FTP 虚拟目录创建时安装示例。  
  
    -   与出站文件示例的文件入站消息传送至 \DynamicResolution\Test\Filedrop\Out 子文件夹。  
  
    -   与出站 MQS 示例的文件入站消息传送到测试。OUT 时创建的队列安装示例。  
  
    -   为文件出站使用 XPATH Resolver 示例的文件入站将邮件传递到消息中指定的位置。 示例文档包含的目标位置和传输类型 （传输类型追加到消息文件的扩展名; 例如，NAOrderDoc_XPATH_FTP.xml 消息包含 FTP 传输类型规范）。  
  
 若要了解该示例的 ESB 调度程序和 ESB 调度程序反汇编程序管道组件的使用，请参阅[动态解析示例的工作原理](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)。