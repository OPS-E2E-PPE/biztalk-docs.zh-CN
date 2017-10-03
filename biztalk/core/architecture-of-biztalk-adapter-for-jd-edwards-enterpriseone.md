---
title: "体系结构的 BizTalk Adapter for 博士 Edwards EnterpriseOne |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: architecture
ms.assetid: 0441c5d2-6a46-45b6-8ab5-0bdac3590f56
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 828d0ed6affc44edbf49beb204cd4afe21196747
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone"></a>JD Edwards EnterpriseOne 的  BizTalk 适配器的体系结构
JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器提供对 JD Edwards EnterpriseOne 业务功能的访问。 JD Edwards EnterpriseOne 使用称为 JDENet 的专用消息体系结构在客户端和服务器计算机之间进行通信。 JDENet 由 Connector.jar 和 Kernel.jar JAR 文件中找到的博士 Edwards EnterpriseOne 连接器类实现。 使用 TCP/IP 作为传输协议，使用默认端口的 6009 或 6010 实现通信。 此值设置有关位置的说明，请参阅[如何设置博士 Edwards OneWorld 传输属性](../core/how-to-set-jd-edwards-oneworld-transport-properties.md)。  
  
 下图显示 JD Edwards EnterpriseOne 的 BizTalk 适配器的架构。  
  
 ![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")  
  
## <a name="inbound-services-at-design-time"></a>设计时的入站服务  
  
-   在设计时，您将创建一个端口，选择一个适配器，并提供用于连接到目标 JD Edwards EnterpriseOne 服务器的凭据信息。 Visual Studio 开发环境调用适配器框架，以请求此端口的设计时信息。 适配器使用此端口的 Browsingagent。  
  
-   在设计时，BizTalk Server 通过调用适配器来请求信息。  
  
-   Browsingagent 将请求转换为本机 JD Edwards EnterpriseOne 代码，并通过 ThinNet API 连接（在 Connector.jar 和 Kernel.jar 中建立）将请求传输到 JD Edwards EnterpriseOne。  
  
-   首先返回 JD Edwards EnterpriseOne 中的模块的列表，并将其传输到填充适配器向导的 Visual Studio 开发环境。  
  
-   您可以通过先显示库名称，然后显示模块名称来扩展层次结构。  
  
-   选择特定模块时，您将看到模块中所有功能的架构。 适配器从 JD Edwards EnterpriseOne 获取所需信息，browsingagent 创建架构。  
  
-   架构添加到 BizTalk Server 项目业务流程。  
  
## <a name="inbound-services-at-run-time"></a>运行时的入站服务  
  
-   BizTalk Server 调用适配器以在特定端口上发送消息。  
  
-   运行时代理将 XML 转换为本机 JDE 代码。  
  
-   运行时代理通过 ThinNet 将请求提交到发送端口的传输属性中指定的 JD Edwards EnterpriseOne 系统。  
  
-   在 JD Edwards EnterpriseOne 系统上执行主业务功能，然后生成一个响应文档，指示成功或失败以及业务功能返回的数据参数。  
  
-   发送到 JD Edwards EnterpriseOne 的消息是一种单消息、单回复结构。 不能同时处理多个消息。  
  
-   响应文档通过 ThinNet 发回，转换为 XML，然后传输回 BizTalk Server。  
  
## <a name="outbound-events-at-design-time"></a>设计时的出站事件  
  
-   事件元数据的系统创建不可用。  
  
-   必须为 Visual Studio 提供事件文档的传真，以便生成架构并与目标命名空间一起合并到项目中。  
  
## <a name="outbound-events-at-run-time"></a>运行时的出站事件  
  
-   在 JD Edwards EnterpriseOne 服务器中建立文件传输机制，以便将事件完成触发的结果 XML 文档传输到该计算机的目标目录。  
  
-   BizTalk Server 计算机已将驱动器映射到 EnterpriseOne 服务器上的目录。  
  
-   已经为映射的驱动器配置了接收端口传输属性。 该接收端口接收 EnterpriseOne 服务器发布到目录的消息。  
  
-   目标命名空间标识确保路由到已配置的接收端口的消息正确。  
  
-   接收端口提交 BizTalk Server 中的 XML 文档。  
  
## <a name="see-also"></a>另请参阅  
 [规划和体系结构](../core/planning-and-architecture8.md)