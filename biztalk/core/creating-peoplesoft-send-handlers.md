---
title: 创建 PeopleSoft 适配器发送项目 |Microsoft Docs
description: 创建发送端口、 发送传输属性和更新最大并发调用将消息发送到 PeopleSoft 在 BizTalk Server 中使用 PeopleSoft Enterprise 适配器
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce67da59-26a6-44a2-929c-ed3acb21d407
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4857bf6444f30da0162cf7ffbeb8572042ba762
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390427"
---
# <a name="create-peoplesoft-send-artifacts"></a>创建 PeopleSoft 发送项目
用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器访问 PeopleSoft 和浏览可用组件或处理 SOAP 请求。 本主题演示如何在 BizTalk Server 管理为使用 PeopleSoft 适配器创建发送项目。


## <a name="create-the-send-port"></a>创建发送端口

1.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开所需的应用程序。  
  
2.  右键单击**发送端口**，选择**新建**，然后选择**静态要求响应发送端口**。  
  
3.  在中**发送端口属性**，执行以下操作：  
  
    1.  输入发送端口的名称。 例如，输入 `SSOSendToPeopleSoft`。  
  
    2.  从**类型**下拉列表中，选择**PeopleSoft**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从发送管道下拉列表，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
    5.  从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
    6.  选择**配置**可配置的发送端口。  
  
4.  在中**PeopleSoft 传输属性**，执行以下操作：  
  
    1.  展开**适配器所需的属性**，并输入**应用程序服务器路径**， **JAVA_HOME**，**用户名**， **密码**，和用于连接到 Peoplesoft 系统的 Jar 文件。  
  
         不需要设置的登录信息。  
  
    2.  在列表中，选择创建为表示 PeopleSoft 系统的 SSO 关联应用程序。  
  
    3.  有关**使用 SSO**，选择**是**。  
  
    4.  选择 **确定**。  
  
5.  选择 **确定**。

## <a name="set-the-transport-properties"></a>设置传输属性
PeopleSoft 传输属性用于设计和运行时。 在中**传输属性**对话框中，您设置的连接和凭据参数特定于服务器系统和你尝试访问的对象。  
  
 ![](../core/media/peop-peoplesofttransportpropertiess.gif "Peop_PeopleSoftTransportPropertiess")  
  
1.  展开适配器必需属性，填写连接到 PeopleSoft 服务器的所有所需信息。  
  
     必须设置连接到 PeopleSoft Enterprise 的 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器的配置参数。 此数据是区分大小写。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |`Application Server Path`|表示的计算机和 PeopleSoft 应用程序服务器是运行和侦听的端口的字符串。 PeopleSoft 8 应用程序的 URL 路径的语法是 / / < 计算机名 >:\<端口\>。 询问有关 PeopleSoft 管理员\<端口\>值。 \<端口\>值指的是 JOLT 协议侦听程序端口，不是应用程序服务器端口。 默认 JOLT 端口为 9000。|  
    |`JAVA_HOME`|设置 JAVA_HOME 变量以指向您的 JDK 安装，例如：**C:\j2sdk1.4.2_08**.|  
    |`Password`|如果未选中**使用 SSO**，必须设置凭据参数以便用于访问服务器系统的 PeopleSoft Enterprise 的 BizTalk 适配器。<br /><br /> 表示用户的密码登录到 PeopleSoft 系统的字符串。 字符不会出现，但由星号 （*） 表示。|  
    |`PeopleSoft 8.x Jar Files`|若要使用组件接口 (仅适用于 PeopleSoft 8)，则必须更新 CLASSPATH 以包含 PeopleSoft 组件接口 jar 文件。 例如： **< PeopleSoft_Home > \web\PSJOA\psjoa.jar**。|  
    |`User Name`|如果未选中**使用 SSO**，必须设置凭据参数以便用于访问服务器系统的 PeopleSoft Enterprise 的 BizTalk 适配器。<br /><br /> 表示用于登录到 PeopleSoft 系统的用户名称的字符串。|  
  
2.  输入**其他参数**时日期用作键的值; 它具有不同的格式。 年-月-日是默认格式。  
  
3.  输入**并发控制**值，该值表示在调用，例如 200 数**最大并发调用**如有必要。  
  
     **最大并发调用**参数激活过载保护，如果后端服务器无法处理的数据量。 并行调用是为其适配器还没有回复的请求。 设置**最大并发调用**中在吞吐量超过了后端处理能力。  
  
     默认值为此字段为-1，这意味着无保护时发生。  
  
     如果 BizTalk Server 将提交到传输适配器的请求和调用等于或超过设置的值的并发数**最大并发调用**、 提交直到并发调用数，已保存请求的线程为降低到低于设置的值。  

## <a name="update-max-concurrent-calls"></a>更新最大并发调用数

`Max Concurrent Calls`参数是一项功能，可用于优化您的配置。 在吞吐量超过了后端处理能力的实例中使用此参数。 可以将参数添加到中的适配器**发送端口传输属性**对话框以激活消息重载保护。 默认值为-1，这意味着不限制调用数量。  
  
当 BizTalk Server 将消息提交到传输适配器时，它首先接收来自适配器的批处理并调用`TransmitMessage()`对批，将每个消息传送。 完成后，BizTalk Server 调用`Done()`批处理，然后适配器开始将消息传输到后端上。 如果 BizTalk Server 之前获得了多个批`Done`调用时，`Done`命令可能永远不会发生。 通过在批处理中设置的最大消息数，可以控制到后端的消息。 更改此参数在一分钟内将生效。 BizTalk Server 必须检索保存在 SQL 数据库中的适配器配置的更改。  
  
### <a name="change-the-max-concurrent-calls-parameter"></a>更改最大并发调用参数  
  
1.  在中**发送端口传输属性**对话框框中，输入**连接**值。  
  
     默认值为 40 个会话。 如果使用较小的值，可能会遇到运行时性能下降。 相反也是如此;较大的值可能会超过服务器和在运行时错误的结果的能力。  
  
2.  选择**是**有关**刷新代理**以强迫 runtimeagent.exe 和 browsingagent.exe 进程在需要时自动重新启动。  
  
     例如，您希望自动重新启动它将失去与服务器的连接，或者如果将内容添加到服务器并且不会出现在 Microsoft 适配器向导中选择的过程。  
  
     **刷新代理**参数刷新浏览和运行时代理。 Runtimeagent.exe 在延迟一分钟或在下一步后的更新发送调用。  
  
3.  提供凭据以访问 PeopleSoft 系统。  
  
     可以使用两种方法来访问系统：  
  
    -   登录凭据 （传输属性登录参数）  
  
    -   单一登录  
  
4.  选择**是**有关**使用 SSO**若要使用单一登录。  
  
    > [!NOTE]
    >  有关详细信息，请参阅[保护适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)。 
  
5.  在列表中选择关联应用程序。  
  
     企业单一登录工具创建的关联应用程序代表诸如 PeopleSoft 之类的应用程序。 用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 从指定的关联应用程序的服务器系统的 SSO 数据库检索这些凭据。 凭据是启动 BizTalk 项目的用户 （应用程序用户）。  
  
    > [!NOTE]
    >  有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications2.md)，或 Microsoft BizTalk Server 联机帮助。  
  
6.  提供所需的所有信息，以接受连接信息后，单击**Apply**，然后单击**确定**。  
  
     必须设置用于访问 PeopleSoft 的 PeopleSoft Enterprise 的 BizTalk 适配器的连接参数。  
  

## <a name="next"></a>Next
  
[PeopleSoft 架构导入到 BizTalk Server 项目](../core/importing-peoplesoft-schemas-into-biztalk-server-projects.md)  
[从 PeopleSoft 接收](../core/receiving-from-peoplesoft.md)