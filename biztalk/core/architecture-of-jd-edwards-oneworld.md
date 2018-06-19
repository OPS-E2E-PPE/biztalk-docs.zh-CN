---
title: 博士 Edwards OneWorld 的体系结构 |Microsoft 文档
description: 在设计时和在 BizTalk 博士 Edwards OneWorld 适配器中的运行的时在设计时和运行的时和出站事件描述的入站的服务
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9200a090-a587-4b60-9447-d281580f2078
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f866e5d72e392136d19c155785aaf6b71db2ce3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014788"
---
# <a name="architecture-of-jd-edwards-oneworld"></a>JD Edwards OneWorld 的体系结构
用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供了对 JD Edwards OneWorld 业务功能的访问。 JD Edwards OneWorld 使用名为 JDENet 的专用消息体系结构在客户端和服务器计算机之间进行通信。 JDENet 由 Connector.jar 和 Kernel.jar JAR 文件中找到的博士 Edwards OneWorld 连接器类实现。 使用 TCP/IP 作为传输协议，使用默认端口的 6009 或 6010 实现通信。 此值设置有关位置的说明，请参阅[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)。  
  
 **用于博士 Edwards OneWorld 的 BizTalk Adapter 的体系结构**  
  
 ![](../core/media/jdedadapter-01-architecture.gif "JDEdAdapter_01_Architecture")  
  
 对 JD Edwards OneWorld 业务功能的调用需要两条消息：  
  
-   第一条消息息响应处理业务功能的服务器的位置。 这通过一组表调用中执行查找实现*对象配置映射 (OCM)*。  
  
-   第二条消息发送格式化的消息缓冲区，其中包含要传递的参数或从 JD Edwards OneWorld 传递到相应服务器的参数，然后等待回复。 根据基础 C++ 结构的 typedef 对缓冲区进行格式化。  
  
## <a name="inbound-services-at-design-time"></a>设计时的入站服务  
  
-   在设计时，您创建端口、选择适配器并提供凭据信息以连接到目标 JD Edwards OneWorld 服务器。 Visual Studio 开发环境调用适配器框架，以请求此端口的设计时信息。 用于 JD Edwards OneWorld 的 BizTalk 适配器使用此端口的 Browsingagent。  
  
-   在设计时，BizTalk Server 通过调用适配器来请求信息。  
  
-   Browsingagent 将请求转换成本地 JD Edwards OneWorld 代码，然后通过 ThinNet API 连接（在连接器和 Kernel.jar 中建立）将请求传输给 JD Edwards OneWorld。  
  
-   通过 BTSREL 安装安装自定义业务函数： 它公开的主业务功能。  
  
-   最初返回 JD Edwards OneWorld 的模块列表，并将其传输到 Visual Studio，填充适配器向导。  
  
-   您可以展开层次结构显示库名称和模块名称。  
  
-   选择特定模块时，您将看到模块中所有功能的架构。 适配器从 JD Edwards OneWorld 获取所需的信息，而 browsingagent 创建架构。  
  
-   架构添加到 BizTalk Server 项目业务流程。  
  
## <a name="inbound-services-at-run-time"></a>运行时的入站服务  
  
-   BizTalk Server 在特定端口上调用用于 JD Edwards OneWorld 的 BizTalk 适配器来发送消息。  
  
-   运行代理将 XML 转换为本地 JD Edwards 代码。  
  
-   运行时代理通过 ThinNet 将请求提交给在发送端口的传输属性中指定的 JD Edwards 企业系统。  
  
-   主业务功能在 JD Edwards 系统上执行，随后生成一个表示成功或失败的响应文档及业务功能返回的数据参数。  
  
-   发送到 JD Edwards OneWorld 的消息是一种单消息、单回复结构。 不能同时处理多个消息。  
  
-   响应文档通过 ThinNet 发回，转换为 XML，然后传输回 BizTalk Server。  
  
## <a name="outbound-events-at-design-time"></a>设计时的出站事件  
  
-   事件元数据的系统创建不可用。  
  
-   必须为 Visual Studio 提供事件文档的传真，以便生成架构并与目标命名空间一起合并到项目中。  
  
## <a name="outbound-events-at-run-time"></a>运行时的出站事件  
  
-   在 JD Edwards 企业服务器中建立文件传输机制，以将事件完成触发的 XML 结果文档传输到该服务器的目标目录。  
  
-   BizTalk Server 计算机拥有一个到企业服务器上目录的映射驱动器。  
  
-   已经为映射的驱动器配置了接收端口传输属性。 接收端口接收企业服务器发布到目录的消息。  
  
-   目标名称空间标识确保将正确的消息路由到配置的接收端口。  
  
-   接收端口将 XML 文档提交到 BizTalk Server。  
  
## <a name="see-also"></a>另请参阅  
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [规划和体系结构](../core/planning-and-architecture17.md)