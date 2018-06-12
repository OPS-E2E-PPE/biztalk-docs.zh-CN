---
title: 使用事件中心适配器 |Microsoft 文档
description: 发送和接收消息 BizTalk Server 中使用 Azure 事件中心适配器
ms.custom: ''
ms.date: 11/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: plarsen
manager: anneta
ms.openlocfilehash: cb9bbe26f07d87d7cccc084b6842b6d0974fdbb3
ms.sourcegitcommit: 3371ffd8ceca02e2b3715d53a1e0c0a59045912e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2018
ms.locfileid: "34848917"
---
# <a name="event-hub-adapter-in-biztalk"></a>BizTalk 中的事件中心适配器

## <a name="overview"></a>概述
**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**，可以发送和接收 BizTalk Server 和 Azure 事件中心之间的消息。 

Azure 事件中心是高度可伸缩的数据流平台，并可以接收和处理数百万个每秒的事件。 [什么是事件中心？](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)提供更多详细信息。

## <a name="prerequisites"></a>必要條件

* 创建[Azure 事件中心命名空间和事件中心](https://docs.microsoft.com/azure/event-hubs/event-hubs-create)
* 创建[与容器的 Azure blob 存储帐户](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)
* 安装[功能包 2](https://aka.ms/bts2016fp2) BizTalk 服务器上

现在创建事件中心，并且你有连接字符串需要发送和接收事件。

## <a name="send-messages-to-event-hubs"></a>将消息发送到事件中心

1.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，选择**新建**，然后选择**静态单向发送端口**。

    [创建发送端口](../core/how-to-create-a-send-port2.md)提供了一些指导。

2. 输入**名称**。 在**传输**，将其设置**类型**到**EventHub**，然后选择**配置**。 

3. 配置**Azure 帐户**属性： 

    |使用此选项|执行的操作|  
    |---|---|  
    | **登录** | 登录到你的 Azure 帐户 |
    | **订阅** | 选择具有 EventHubs 命名空间的订阅 |
    | **资源组** | 选择你具有 EventHubs 命名空间的资源组 |

4. 配置**终结点**属性： 

    |使用此选项|执行的操作|  
    |---|---|  
    | **Namespace** | 选择事件中心命名空间，这是类似于 sb: / /*youreventhubnamespace*.servicebus.windows.net/ |
    | **名称** | 选择你的事件中心名称 （这在你的事件中心命名空间内创建） |
    | **默认分区键** | 可选。 [事件中心编程指南](https://docs.microsoft.com/azure/event-hubs/event-hubs-programming-guide)对此项提供更多详细信息。 |
    | **身份验证** | **Namespace 访问签名**是默认设置，并自动使用你创建事件中心命名空间时，创建 RootManageSharedAccessKey。<br/><br/>**实体访问签名**是可以在事件中心的级别 （不是事件中心命名空间的级别） 创建的 SAS 策略。 <br/><br/>[事件中心功能概述](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)说明的详细信息。 |

    完成后，你的属性类似于以下： 

    ![终结点属性](../core/media/event-hub-endpoint-properties.png)


5. 可选。 配置**消息**属性。 **用户定义的消息属性的 Namespace**值表示 BizTalk 消息架构映射到事件中心消息属性。

6. 选择**确定**以保存所做的更改。 


### <a name="test-your-send-port"></a>测试发送端口

你可以使用简单文件接收端口和将消息发送到 Azure 事件中心的位置。 

1. 创建使用文件适配器接收端口。 在你接收位置，请将设置**接收文件夹**到 **C:\Temp\In\**，并将文件掩码设置为 **\*.xml**。
2. 在你的事件中心发送端口属性，设置**筛选器**到`BTS.ReceivePortName == FileReceivePort`。
3. 将以下内容粘贴到文本编辑器，并将文件作为**EventHubMessage.xml**。 这是示例消息。 

    ```xml
    <Data>
      <DataID>DataID_0</DataID>
      <DataDetails>DataDetails_0</DataDetails>
    </Data>
    ```

4. 启动文件接收位置和事件中心发送端口。
5. 复制**EventHubMessage.xml**到接收文件夹的示例消息 (C:\Temp\In\)。 发送端口将发送到事件中心的 XML 文件。

## <a name="receive-messages-from-event-hubs"></a>从事件中心接收消息

1. 在 BizTalk Server 管理控制台中，右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**。 

    [创建接收端口](../core/how-to-create-a-receive-port.md)提供了一些指导。

2. 输入一个名称，并选择**接收位置**。 

3. 选择**新建**，和**名称**接收位置。 在**传输**，选择**EventHub**从**类型**下拉列表，然后选择**配置**。 

4. 配置**Azure 帐户**属性： 

    |使用此选项|执行的操作|  
    |---|---|  
    | **登录** | 登录到你的 Azure 帐户 |
    | **订阅** | 选择具有 EventHubs 命名空间的订阅 |
    | **资源组** | 选择你具有 EventHubs 命名空间的资源组 |

4. 配置**终结点**属性： 

    |使用此选项|执行的操作|  
    |---|---|  
    | **Namespace** | 选择事件中心命名空间，这是类似于 sb: / /*youreventhubnamespace*.servicebus.windows.net/ |
    | **名称** | 选择你的事件中心名称 （这在你的事件中心命名空间内创建） |
    | **使用者组** | 选择在事件中心内的使用者组。 自动创建默认组。 <br/><br/>[事件中心功能概述](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)提供更多详细信息。 |
    | **身份验证** | **Namespace 访问签名**是默认设置，并自动使用你创建事件中心命名空间时，创建 RootManageSharedAccessKey。<br/><br/>**实体访问签名**是可以在事件中心的级别 （不是事件中心命名空间的级别） 创建的 SAS 策略。 <br/><br/>[事件中心功能概述](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)说明的详细信息。 |

    完成后，你的属性类似于以下： 

    ![终结点属性](../core/media/event-hub-endpoint-receive-properties.png)

5. 配置**检查点**属性。 此适配器使用的 Azure blob 存储帐户可靠地读取事件使用检查点，并从中重新启动恢复。 

    **存储身份验证**   
    选择一个身份验证方法。 通常情况下，它具有建议使用共享访问签名。 以下链接提供了良好的资源来帮助你决定哪种适合你的方案：<br/><br/>[有关 Azure 存储帐户](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account)<br/>[使用共享的访问签名 (SAS)](https://docs.microsoft.com/azure/storage/common/storage-dotnet-shared-access-signature-part-1)

    完成后，你的属性类似于以下： 

    ![检查点属性](../core/media/event-hub-receive-checkpoint.png)

6. 配置**消息**属性： 

    |使用此选项|执行的操作|  
    |---|---|  
    | **Namespace 为用户定义消息属性** | http://schemas.microsoft.com/BizTalk/EventHubAdapter/EventData/User 是默认架构，但您可以输入另一个架构。 此值表示 BizTalk 消息架构映射到事件中心消息属性。 |
    | **升级用户定义的属性** | 可选。 如果你愿意，你可以升级这些属性。 <br/><br/>**注意**<br/>需要提升的属性应具有部署的 porperty 架构*之前*接收事件。|

7. 选择**确定**以保存所做的更改。 

### <a name="test-your-receive-settings"></a>测试你接收设置

可以使用简单的文件发送端口从 Azure 事件中心接收消息。 

1. 创建使用文件适配器发送端口。 在你发送端口属性内, 设置**目标文件夹**到 **C:\Temp\Out\**，并将设置和**文件名**到 **%MessageID%.xml**.
2. 在你的文件发送端口属性，设置**筛选器**到`BTS.ReceivePortName == EHReceivePort`。
3. 开始事件中心接收位置和文件发送端口。
4. 查找目标文件夹 (c:\temp\out) 中的消息。

## <a name="do-more"></a>执行更多操作
事件中心被视为"前门"大量其他 Azure 服务，包括 Azure Data Lake、 HD Insight 和的详细信息。 它旨在处理的消息，并快速进行处理。 有关事件中心和其功能的更多信息： 

[事件中心功能概述](https://docs.microsoft.com/azure/event-hubs/event-hubs-features)  
[什么是事件中心？](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)