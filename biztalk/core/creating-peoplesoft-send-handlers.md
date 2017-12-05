---
title: "创建 PeopleSoft 适配器发送项目 |Microsoft 文档"
description: "创建发送端口、 发送传输属性和更新最大并发调用，以将消息发送到 BizTalk Server 中使用 PeopleSoft Enterprise 适配器 PeopleSoft"
ms.custom: 
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce67da59-26a6-44a2-929c-ed3acb21d407
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bc559f4e3c25560540a171b3f47ff25e6f34e89
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="create-peoplesoft-send-artifacts"></a>创建 PeopleSoft 发送项目
适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器用于访问 PeopleSoft，以及浏览可用组件或处理 SOAP 请求。 本主题演示如何在 BizTalk Server 管理来使用 PeopleSoft 适配器中创建的发送项目。


## <a name="create-the-send-port"></a>创建发送端口

1.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。  
  
2.  右键单击**发送端口**，选择**新建**，然后选择**静态请求-响应发送端口**。  
  
3.  在**发送端口属性**，执行以下操作：  
  
    1.  输入发送端口的名称。 例如，输入`SSOSendToPeopleSoft`。  
  
    2.  从**类型**下拉列表中，选择**PeopleSoft**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
    5.  从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
    6.  选择**配置**配置发送端口。  
  
4.  在**PeopleSoft 传输属性**，执行以下操作：  
  
    1.  展开**适配器所需属性**，并输入**应用程序服务器路径**， **JAVA_HOME**，**用户名**， **密码**，和连接到 Peoplesoft 系统的 Jar 文件。  
  
         您不必设置登录信息。  
  
    2.  在列表中选择为表示 PeopleSoft 系统所创建的 SSO 关联应用程序。  
  
    3.  有关**使用 SSO**，选择**是**。  
  
    4.  选择“确定”。  
  
5.  选择“确定”。

## <a name="set-the-transport-properties"></a>设置传输属性
PeopleSoft 传输属性用于运行时和设计时。 在**传输属性**对话框中，你设置的连接和凭据参数特定于服务器系统和你尝试访问的对象。  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
1.  展开“适配器必需属性”，然后填写连接到 PeopleSoft 服务器所需的各项信息。  
  
     必须设置配置参数才能将适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器连接到 PeopleSoft Enterprise。 此数据是区分大小写。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |`Application Server Path`|此字符串代表 PeopleSoft 应用程序服务器运行的计算机和侦听的端口。 PeopleSoft 8 应用程序的 URL 路径的语法是 / / < 计算机名 >:\<端口\>。 向你 PeopleSoft 管理员请求\<端口\>值。 \<端口\>值是震动协议侦听器端口，不是应用程序服务器端口。 默认 JOLT 端口为 9000。|  
    |`JAVA_HOME`|设置 JAVA_HOME 变量以指向你 JDK 的安装，例如： **C:\j2sdk1.4.2_08**。|  
    |`Password`|如果你未选择**使用 SSO**，必须设置为 BizTalk 适配器 PeopleSoft 企业访问服务器系统的凭据参数。<br /><br /> 表示用户密码的字符串，用于登录到 PeopleSoft 系统。 不会显示密码中的字符，而是以星号 (*) 表示这些字符。|  
    |`PeopleSoft 8.x Jar Files`|若要使用组件接口（仅限 PeopleSoft 8），则必须更新 CLASSPATH 以包含 PeopleSoft 组件接口 jar 文件。 例如： **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**。|  
    |`User Name`|如果你未选择**使用 SSO**，必须设置为 BizTalk 适配器 PeopleSoft 企业访问服务器系统的凭据参数。<br /><br /> 表示用户名的字符串，用于登录到 PeopleSoft 系统。|  
  
2.  输入**其他参数**时日期用作键的值; 它具有不同的格式。 YYYY-月-日是默认格式。  
  
3.  输入**并发控制**值在表示的调用，例如 200、 数**最大并发调用**如有必要。  
  
     **最大并发调用**参数激活过载保护，如果后端服务器无法处理的数据量。 并行调用是适配器尚未进行回复的请求。 设置**最大并发调用**其中吞吐量超过后端处理功能的实例中。  
  
     此字段的默认值为 -1，意味着未进行任何保护。  
  
     如果 BizTalk Server 将请求提交到传输适配器，并且调用等于或超过为设置的值的并发数**最大并发调用**，提交请求被保存，直到并发调用数量的线程为降低到低于设置的值。  

## <a name="update-max-concurrent-calls"></a>更新最大并发调用

`Max Concurrent Calls` 参数是一种用来优化配置的功能。 在吞吐量超过了后端处理能力的情况下，可以使用此参数。 你可以将参数添加到中的适配器**发送端口传输属性**对话框中，若要激活消息重载保护。 默认值为 -1，表示不限制调用数量。  
  
当 BizTalk Server 将消息提交到传输适配器时，它首先接收来自适配器的一个批并对批调用 `TransmitMessage()` 以传输每个消息。 完成上述操作后，BizTalk Server 对批调用 `Done()`，然后适配器开始将消息传输到后端。 如果 BizTalk Server 在调用 `Done` 之前获得了多个批，`Done` 命令可能永远不会发生。 通过设置批中的最大消息数量，可以控制传输到后端的消息。 对此参数的更改会在一分钟后生效。 BizTalk Server 必须检索保存在 SQL 数据库中的适配器配置的更改。  
  
### <a name="change-the-max-concurrent-calls-parameter"></a>更改最大并发调用参数  
  
1.  在**发送端口传输属性**对话框框中，输入**连接**值。  
  
     默认值为 40 个会话。 如果您使用一个较小的值，可能会出现运行时性能下降。 反之亦然，使用较大的值，则会超出服务器的能力并导致运行时错误。  
  
2.  选择**是**为**刷新代理**强制 runtimeagent.exe 以及要在需要时自动重新启动 browsingagent.exe 过程。  
  
     例如，您希望进程在出现以下情况时自动重新启动：丢失了与服务器的连接；或者向服务器中添加了内容，但是由于它没有显示在 Microsoft 适配器向导中而无法选择它。  
  
     **刷新代理**参数刷新浏览和运行时代理。 runtimeagent.exe 在一分钟延迟后或在下一次发送呼叫时更新。  
  
3.  提供凭据以访问 PeopleSoft 系统。  
  
     您可以使用两种方法来访问系统：  
  
    -   登录凭据（传输属性登录参数）  
  
    -   单一登录  
  
4.  选择**是**为**使用 SSO**用于单一登录。  
  
    > [!NOTE]
    >  有关详细信息，请参阅[安全适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)。 
  
5.  在列表中选择一个关联应用程序。  
  
     由企业单一登录工具创建的关联应用程序，表示一个应用程序，如 PeopleSoft。 适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。 凭据是启动 BizTalk 项目的用户（应用程序用户）的凭据。  
  
    > [!NOTE]
    >  有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications2.md)，或 Microsoft BizTalk Server 联机帮助。  
  
6.  提供所有所需的信息，以接受连接信息后，单击**应用**，然后单击**确定**。  
  
     您必须为适用于 PeopleSoft Enterprise 的 BizTalk 适配器设置连接参数，以访问 PeopleSoft。  
  

## <a name="next"></a>Next
  
[将 PeopleSoft 架构导入到 BizTalk Server 项目](../core/importing-peoplesoft-schemas-into-biztalk-server-projects.md)  
[从 PeopleSoft 接收](../core/receiving-from-peoplesoft.md)