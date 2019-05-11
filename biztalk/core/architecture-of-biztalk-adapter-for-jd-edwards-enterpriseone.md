---
title: 用于 JD Edwards EnterpriseOne 的 BizTalk 适配器的体系结构 |Microsoft Docs
description: 在设计时和运行的时和出站事件在设计时和运行的时在 BizTalk 中的 JD Edwards EnterpriseOne 适配器中描述的入站的服务
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0441c5d2-6a46-45b6-8ab5-0bdac3590f56
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dc7992262731532f2c9df6b29896f48f5f74e5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359365"
---
# <a name="architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone"></a>用于 JD Edwards EnterpriseOne 的 BizTalk 适配器的体系结构
用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器提供了对 JD Edwards EnterpriseOne 业务功能的访问。 JD Edwards EnterpriseOne 使用消息传递体系结构称为 JDENet 的专用的客户端和服务器计算机之间进行通信。 JDENet 由 JAR 文件，Connector.jar 和 Kernel.jar 中找到的 JD Edwards EnterpriseOne 连接器类实现。 使用 TCP/IP 作为传输协议，默认端口为 6009 或 6010 实现通信。 此值设置的位置的说明，请参阅[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)。  
  
 下图显示有关用于 JD Edwards EnterpriseOne 的 BizTalk 适配器体系结构。  
  
 ![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")  
  
## <a name="inbound-services-at-design-time"></a>在设计时的入站服务  
  
-   在设计时创建的端口、 选择一个适配器，并提供凭据信息连接到目标 JD Edwards EnterpriseOne 服务器。 在 Visual Studio 开发环境调用适配器框架，以请求为此端口的设计时信息。 适配器使用此端口的 Browsingagent。  
  
-   在设计时，BizTalk Server 通过调用适配器来请求信息。  
  
-   Browsingagent 将请求转换为本机 JD Edwards EnterpriseOne 代码，并将请求传输到 JD Edwards EnterpriseOne 通过 ThinNet API 连接 （在 Connector.jar 和 Kernel.jar 中建立）。  
  
-   最初返回 JD Edwards EnterpriseOne 中的模块的列表并将其传输到 Visual Studio 开发环境，其中它将填充适配器向导。  
  
-   通过显示库名称，然后选择模块名称，可以展开层次结构。  
  
-   选择特定模块时，可以看到该模块中的所有函数的架构。 适配器从 JD Edwards EnterpriseOne 获取所需的信息，browsingagent 创建架构。  
  
-   架构将添加到 BizTalk Server 项目业务流程。  
  
## <a name="inbound-services-at-run-time"></a>在运行时的入站服务  
  
-   BizTalk Server 调用适配器的特定端口上发送消息。  
  
-   运行时代理将 XML 转换为本机 JDE 代码。  
  
-   运行时代理通过 ThinNet 到发送端口的传输属性中指定的 JD Edwards EnterpriseOne 系统将请求提交。  
  
-   JD Edwards EnterpriseOne 系统，然后生成一个，该值指示成功或失败，以及数据的响应文档上执行主业务功能返回的业务函数的参数。  
  
-   发送到 JD Edwards EnterpriseOne 的消息是单消息、 单回复结构。 不能同时处理多条消息。  
  
-   响应文档通过 ThinNet 发回，转换为 XML，并传输回 BizTalk Server。  
  
## <a name="outbound-events-at-design-time"></a>在设计时的出站事件  
  
-   提供的事件元数据系统创建。  
  
-   必须为 Visual Studio 提供事件文档的传真，以便可以生成一个架构，并将其合并到一个项目，以及目标命名空间。  
  
## <a name="outbound-events-at-run-time"></a>在运行时的出站事件  
  
-   要传输生成的 XML 文档中，触发的事件完成时，到该计算机上的目标目录的 JD Edwards EnterpriseOne 服务器中建立文件传输机制。  
  
-   BizTalk Server 计算机已经 EnterpriseOne 服务器上的目录映射的驱动器。  
  
-   接收端口传输属性配置为映射的驱动器。 接收端口接收 EnterpriseOne 服务器发布到目录的消息。  
  
-   目标命名空间标识确保将正确的消息路由到配置的接收端口  
  
-   接收端口提交 BizTalk Server 中的 XML 文档。  
  
## <a name="more-good-stuff"></a>更多有用资料
[用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[创建应用程序项目](../core/developing-applications2.md)  
[导入 JD Edwards EnterpriseOne 应用程序](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[使用 BizTalk Server 异常处理](../core/using-biztalk-server-exception-handling3.md)  
[故障排除](../core/troubleshooting-jd-edwards-enterpriseone.md)  
