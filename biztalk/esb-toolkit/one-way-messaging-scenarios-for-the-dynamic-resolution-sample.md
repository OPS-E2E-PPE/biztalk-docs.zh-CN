---
title: 动态解析示例的单向消息传送方案 |Microsoft Docs
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
ms.openlocfilehash: 359b91a1a5da9ce435d3d9aa5884d6928d0e0a9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987534"
---
# <a name="one-way-messaging-scenarios-for-the-dynamic-resolution-sample"></a>动态解析示例的单向消息传送方案
本主题演示如何运行的单向消息传送方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态解析示例。  

 **若要运行动态解析示例的单向消息传送方案**  

1. 第一次运行此示例之前，请确保接收位置 URL 指向相应的目录。 指定源的子文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\In DynamicResolution_FILE 接收位置。 此外，请确保存在名为 DynamicResolutionOneWay 的动态发送端口。  

   > [!NOTE]
   >  动态解析示例使用动态解析机制将消息发送到输出文件夹、 FTP 站点或 MQSeries 队列。 这就是原因本示例未定义静态发送端口。 动态解析组件解决方法从检索输出 URL 和适配器提供程序框架时调用的 ESBReceiveXml 管道，在 DynamicResolution_FILE 中配置接收位置。  

2. 如果尚未运行 GlobalBank.ESB 应用程序，使用 Microsoft BizTalk 管理控制台来启动它。  

3. 决定你想要执行的示例。 所有单向消息传送 （只使用 XPATH 解析程序） 的示例使用 NAOrderDoc.xml \Source\Samples\DynamicResolution\Test\Data 的文件夹中的文件输入到名为 DynamicResolution_FILE 接收位置。 有七个单向消息传送示例，每个唯一绑定文件表示。 下表列出了这些示例中，使用其关联的绑定文件和说明。  

   |文件的入站到出站使用静态的冲突解决程序的文件|  
   |-------------------------------------------------------------|  
   |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
   |在接收端口以静态方式设置这些映射。|  
   |使用 ESB 调度程序在接收位置的终结点解析。|  

   |文件的入站到出站使用 UDDI 解析程序的文件|  
   |-----------------------------------------------------------|  
   |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
   |在接收端口以静态方式设置这些映射。|  
   |使用 ESB 调度程序在接收位置的终结点解析。|  

   |文件的入站到出站使用 UDDI 服务密钥通过 UDDI 解析程序的文件|  
   |----------------------------------------------------------------------------|  
   |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_UDDI_SERVICEKEY_ Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
   |在接收端口以静态方式设置这些映射。|  
   |使用 ESB 调度程序在接收位置的终结点解析。|  

   > [!NOTE]
   >  对于上述示例中，必须更改绑定文件中的服务密钥为其中一个目标 UDDI 服务器上存在。  

   |文件的入站到 FTP 出站使用静态的冲突解决程序|  
   |------------------------------------------------------------|  
   |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
   |在接收端口以静态方式设置这些映射。|  
   |使用 ESB 调度程序在接收位置的终结点解析。|  

   |文件的入站到 FTP 出站使用静态解析程序和 ENDPOINTCONFIG 参数|  
   |-----------------------------------------------------------------------------------------|  
   |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FTP_STATIC__ ENDPOINTCONFIG_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
   |在接收端口以静态方式设置这些映射。|  
   |使用 ESB 调度程序在接收位置的终结点解析。|  
   |将传递的其他名称/值对的适配器提供程序设置。|  

   |文件的入站到 MQS 出站使用静态的冲突解决程序|  
   |------------------------------------------------------------|  
   |使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_MQS_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。|  
   |在接收端口以静态方式设置这些映射。|  
   |使用 ESB 调度程序在接收位置的终结点解析。|  

   |                                                                             文件的入站到出站使用 XPATH 冲突解决程序的文件                                                                             |
   |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                        使用名为 GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_XPATH_STATIC_Bindings.xml 的绑定文件来设置接收位置和发送端口属性。                        |
   |                                                                                 在接收端口以静态方式设置这些映射。                                                                                  |
   |                                                                    使用 ESB 调度程序在接收位置的终结点解析。                                                                    |
   | 使用消息中的信息来确定适当的终结点。 可以使用此示例中使用的测试文件是 NAOrderDoc_XPATH_FILE.xml、 NAOrderDoc_XPATH_FTP.xml 和 NAOrderDoc_XPATH_MQS.xml。 |


4. 导入绑定文件对于您要执行到 GlobalBank.ESB 应用程序的消息传送示例。  

5. 在 Windows 资源管理器，打开文件夹 \Source\Samples\DynamicResolution\Test\Data 并将相应的输入的文件复制到文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\In。 使用的文件取决于您决定要执行的示例：  

   -   有关 XPATH 的示例中，使用以下文件之一： NAOrderDoc_XPATH_FILE.xml、 NAOrderDoc_XPATH_FTP.xml 或 NAOrderDoc_XPATH_MQS.xml。  

   -   对于所有其他示例，请使用文件 NAOrderDoc.xml。  

6. 查看已发送邮件的适当位置。 位置取决于您使用的绑定文件。 示例如下：  

   -   文件的入站与出站 FTP 示例的消息传递到名为 Out 的 FTP 虚拟目录创建时安装示例。  

   -   文件的入站与出站文件示例的消息传递到 \DynamicResolution\Test\Filedrop\Out 子文件夹。  

   -   文件的入站与出站 MQS 示例的消息传递到测试。队列时创建出安装示例。  

   -   对文件出使用 XPATH 冲突解决程序示例的文件入站的消息传递到消息中指定的位置。 示例文档包含目标位置和传输类型 （传输类型附加到消息文件名称; 例如，NAOrderDoc_XPATH_FTP.xml 消息包含 FTP 传输类型规范）。  

   若要了解此示例如何使用 ESB 调度程序和 ESB 调度程序反汇编程序管道组件，请参阅[动态解析示例的工作原理](../esb-toolkit/how-the-dynamic-resolution-sample-works.md)。