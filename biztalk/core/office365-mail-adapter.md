---
title: 使用 Office 365 Outlook 电子邮件适配器 |Microsoft Docs
description: 发送和接收电子邮件消息在 BizTalk Server 中使用 Office 365 Outlook 电子邮件适配器。 若要执行此操作，创建接收端口和发送端口使用的电子邮件适配器，和使用示例消息来测试你的端口。
ms.custom: ''
ms.date: 06/25/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: ribarua
manager: dougeby
ms.openlocfilehash: 58183ce30236ccca39b9c8345959c4785de46ae9
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752629"
---
# <a name="send-and-receive-email-with-office-365-outlook-email-adapter---biztalk-server"></a>发送和接收电子邮件与 Office 365 Outlook 电子邮件适配器的 BizTalk Server

Office 365 Outlook 电子邮件适配器可以发送和接收邮件从 Office 365 Outlook 电子邮件从 BizTalk。

## <a name="send-mail-using-a-send-port"></a>使用发送端口发送邮件

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，选择**新建**，然后选择**静态单向发送端口**。

    [创建发送端口](../core/how-to-create-a-send-port2.md)提供一些指导。

2. 输入**名称**。 在**传输**，请设置**类型**到**Office 365 Outlook 电子邮件**，然后选择**配置**。

3. 选择**登录...**，并登录到你的 Office 365 帐户。 该帐户是使用你的电子邮件地址自动填充。

4. 允许 BizTalk Server 的访问权限的审批请求：

    ![Office 365 电子邮件权限](../core/media/office365-mail-permissions.png)

5. 配置您 Office 365 Outlook 电子邮件的默认属性：

    |使用此选项|执行的操作|  
    |---|---|  
    | **若要** | 指定将默认为分隔的邮件地址 ';'（最多 256 个字符）|
    | CC | 指定由分隔您默认抄送邮件地址 ';'（最多 256 个字符）|
    | **主题** | 提到你默认邮件主题。 （最多 256 个字符） |
    | **重要性** | 选择你的重要性的值。 下拉列表中包含值**低**，**正常**并**高**与**正常**默认值。 |

    完成后，您的属性类似于以下：

    ![终结点属性](../core/media/office365-mail-send-properties.png)

6. 选择**确定**以保存所做的更改。

### <a name="important-details"></a>重要详细信息

1. 你只能发送纯文本消息使用的发送适配器。
2. 此外可能使用升级的属性会更新默认属性：

|“属性”|升级的属性|
|---|---|
| **若要** | OfficeMail.To |
| CC | OfficeMail.CC |
| **主题** | OfficeMail.Subject |
| **重要性** | OfficeMail.Importance |

### <a name="test-your-send-port"></a>测试您的发送端口

可以使用简单文件接收端口和位置将消息发送到 Office 365 Outlook 电子邮件。

1. 创建使用文件适配器的接收端口。 在你接收位置，则设置**接收文件夹**到**c:\\Temp\\中\\**，并将文件掩码设置为 **\*.xml**.
2. 在您的 Office 365 Outlook 电子邮件适配器发送端口属性，设置**筛选器**到`BTS.ReceivePortName == <Receive Port Name>`。
3. 将以下粘贴到文本编辑器中，并将该文件作为**Office365Mail.xml**。 这是您的示例消息。

    ```xml
    <ns0:Root xmlns:ns0="http://BizTalk_Server_Project1.Schema1"> 
        <Record> 
            <Name>BizTalk User</Name> 
            <ID>001</ID> 
        </Record> 
    </ns0:Root> 
    ```

4. 启动文件接收位置和 Office 365 Outlook 电子邮件适配器发送端口。
5. 复制**Office365Mail.xml**到接收文件夹的示例消息 (c:\\Temp\\中\\)。 发送端口将 XML 文件作为邮件正文发送到 Office 365 Outlook 电子邮件。

## <a name="receive-email-using-a-receive-port"></a>接收电子邮件使用接收端口

1. 在 BizTalk Server 管理控制台中，右键单击**接收端口**，选择**新建**，然后选择**单向接收端口**。

    [创建接收端口](../core/how-to-create-a-receive-port.md)提供一些指导。

2. 输入一个名称，并选择**接收位置**。

3. 选择**新建**，并**名称**接收位置。 在中**传输**，选择**Office 365 Outlook 电子邮件**从**类型**下拉列表，然后选择**配置**。

4. 选择 **[登录...**，并登录到你的 Office 365 帐户。 该帐户是使用你的电子邮件地址自动填充。

5. 允许 BizTalk Server 的访问权限的审批请求：

    ![Office 365 电子邮件权限](../core/media/office365-mail-permissions.png)

6. 配置**终结点**属性：

    |使用此选项|执行的操作|  
    |---|---|  
    | **文件夹** | 选择要获取电子邮件的文件夹。 默认文件夹是收件箱。 请注意文件夹不是递归性质。 例如，从子文件夹的电子邮件不是检索。 |
    | **从启动** | 输入如何从 Office 365 接收电子邮件。 此值指示 receivedTimeStamp 在 Office 365 Outlook 中的电子邮件。 不是，将接收输入的值较新的电子邮件。  |
    | **仅未读的邮件** | 勾选此项以读取仅未读电子邮件。 保留未选中状态，以读取所有的电子邮件。 |
    | **Post 操作** | 选择要读取一封电子邮件后执行 post 操作。 **无**是默认设置，并通过 BizTalk 接收到电子邮件之后不执行任何操作。 **标记为已读**所示，BizTalk 收到一封电子邮件后，你的邮箱中的电子邮件被标记为已读。 **删除**所示，通过 BizTalk 收到一封电子邮件后，会删除您邮箱中的电子邮件。 最大程度地执行 post 操作。|

    完成后，您的属性类似于以下：

    ![终结点属性](../core/media/office365-mail-receive-properties.png)

7. 选择**确定**以保存所做的更改。

### <a name="test-your-receive-settings"></a>测试在接收设置

可以使用简单的 File 发送端口以接收来自你的 Office 365 Outlook 电子邮件消息。

1. 创建使用文件适配器的发送端口。 在发送端口的属性，设置**目标文件夹**到**c:\\Temp\\出\\**，并将设置和**文件名**到 **%MessageID%.xml**。
2. 在你的文件将发送端口属性，设置**筛选器**到`BTS.ReceivePortName == <Receive Port Name>`。
3. 启动 Office 365 Outlook 电子邮件接收位置和 File 发送端口。
4. 查找目标文件夹 (c:\temp\out) 中的消息。

### <a name="promoted-properties-from-receive-pipeline"></a>接收管道中的升级的属性

默认情况下提升在接收管道的以下属性：

|属性名称| 升级的属性|
|---|---|
| **重要性** | OfficeMail.ReceivedMailImportance |
| **主题** | OfficeMail.ReceivedMailSubject |
| **SenderName** | OfficeMail.SenderName |
| **输入** | OfficeMail.SenderAddress |
| **HasAttachments**| OfficeMail.HasAttachments |

> [!NOTE]
> 电子邮件的正文内容传递到该消息。

## <a name="next-steps"></a>后续步骤
查看所有[Office 365 适配器](office365-adapters.md)，或安装[功能包 3](https://aka.ms/bts2016fp3)。