---
title: JD Edwards OneWorld 的体系结构 |Microsoft Docs
description: 在设计时和运行的时和出站事件在设计时和运行的时在 BizTalk 中的 JD Edwards OneWorld 适配器中描述的入站的服务
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
ms.openlocfilehash: 0e98b7196077d0754ef067d01a51b49b96dc8f9e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358990"
---
# <a name="architecture-of-jd-edwards-oneworld"></a>JD Edwards OneWorld 的体系结构
用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供了对 JD Edwards OneWorld 业务功能的访问。 JD Edwards OneWorld 使用消息传递体系结构称为 JDENet 的专用的客户端和服务器计算机之间进行通信。 JDENet 由 JAR 文件，Connector.jar 和 Kernel.jar 中找到的 JD Edwards OneWorld 连接器类实现。 使用 TCP/IP 作为传输协议，默认端口为 6009 或 6010 实现通信。 此值设置的位置的说明，请参阅[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)。  
  
 **用于 JD Edwards OneWorld 的 BizTalk 适配器的体系结构**  
  
 ![](../core/media/jdedadapter-01-architecture.gif "JDEdAdapter_01_Architecture")  
  
 对 JD Edwards OneWorld 业务函数的调用需要两条消息：  
  
-   第一条消息息响应处理业务功能的服务器的位置。 这通过一系列名为的表中执行查找来实现*对象配置映射 (OCM)*。  
  
-   第二条消息将发送包含要传递到相应的服务器，到或从 JD Edwards OneWorld 的参数的格式的消息缓冲区，并等待回复。 对缓冲区进行格式化的基础类型定义根据C++结构。  
  
## <a name="inbound-services-at-design-time"></a>在设计时的入站服务  
  
-   在设计时，创建你的端口、 选择适配器，并提供凭据信息连接到目标 JD Edwards OneWorld 服务器。 在 Visual Studio 开发环境调用适配器框架，以请求为此端口的设计时信息。 用于 JD Edwards OneWorld 的 BizTalk 适配器使用此端口的 Browsingagent。  
  
-   在设计时，BizTalk Server 通过调用适配器来请求信息。  
  
-   Browsingagent 将请求转换为本机 JD Edwards OneWorld 代码，然后将请求传输到 JD Edwards OneWorld 通过 ThinNet API 连接 （连接器和 Kernel.jar 中建立）。  
  
-   通过 BTSREL 安装安装自定义业务函数： 它公开了主业务功能。  
  
-   最初返回 JD Edwards OneWorld 中的模块的列表并将其传输到 Visual Studio 中，填充适配器向导。  
  
-   您可以展开层次结构显示库名称和模块名称。  
  
-   选择特定模块时，可以看到该模块中的所有函数的架构。 适配器从 JD Edwards OneWorld 获取所需的信息，browsingagent 创建架构。  
  
-   架构将添加到 BizTalk Server 项目业务流程。  
  
## <a name="inbound-services-at-run-time"></a>在运行时的入站服务  
  
-   BizTalk Server 调用用于 JD Edwards OneWorld 特定端口上发送消息的 BizTalk 适配器。  
  
-   运行时代理将 XML 转换为本机 JD Edwards 代码。  
  
-   运行时代理通过 ThinNet 到发送端口的传输属性中指定的 JD Edwards 企业系统将请求提交。  
  
-   在 JD Edwards 系统上，然后生成一个，该值指示成功或失败，以及数据的响应文档执行主业务函数返回的业务函数的参数。  
  
-   发送到 JD Edwards OneWorld 的消息是单消息、 单回复结构。 不能同时处理多条消息。  
  
-   响应文档通过 ThinNet 发回，转换为 XML，并传输回 BizTalk Server。  
  
## <a name="outbound-events-at-design-time"></a>在设计时的出站事件  
  
-   提供的事件元数据系统创建。  
  
-   必须为 Visual Studio 提供事件文档的传真，以便可以生成一个架构，并将其合并到一个项目，以及目标命名空间。  
  
## <a name="outbound-events-at-run-time"></a>在运行时的出站事件  
  
-   要传输生成的 XML 文档中，触发的事件完成时，到该服务器上的目标目录的 JD Edwards 企业服务器中建立文件传输机制。  
  
-   BizTalk Server 计算机具有企业服务器上的目录映射的驱动器。  
  
-   接收端口传输属性配置为映射的驱动器。 接收端口接收企业服务器发布到目录的消息。  
  
-   目标命名空间标识确保将正确的消息路由到配置的接收端口。  
  
-   接收端口将提交到 BizTalk Server 的 XML 文档。  
  
## <a name="see-also"></a>请参阅  
 [将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [规划和体系结构](../core/planning-and-architecture17.md)