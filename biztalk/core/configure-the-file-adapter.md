---
title: "配置文件适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- File adapters, configuring
- configuring [File adapters], about configuring File adapters
- configuring [File adapters]
ms.assetid: 1e0c7e20-80f8-469b-b423-34a2b90f9ec3
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2f2de6a4c4cae93db90f0fb2cfc79321bfc7b3e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="configure-the-file-adapter"></a>配置文件适配器
如何配置文件适配器，阅读安全建议，并查看所需的权限。

你可以创建接收位置和发送端口使用[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，或以编程方式。 本主题重点[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]控制台。 有关以编程方式的步骤中，转到[创建接收位置或以编程方式发送端口](../core/create-the-receive-location-and-send-port-programmatically.md)。

> [!IMPORTANT]
> **从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，你可以连接到 Azure 文件共享使用文件适配器。 Azure 存储帐户必须装载在 BizTalk Server。 [要开始使用 Azure 文件存储在 Windows 上](https://docs.microsoft.com/azure/storage/storage-dotnet-how-to-use-files#mount-the-file-share)列出的安装步骤。

## <a name="security-recommendations"></a>安全建议

文件适配器用于在 BizTalk Server 与相应的目录之间相互传递文件。 建议您遵循这些准则以确保您的环境中的文件适配器的安全并对其进行部署。  
  
-   不打开端口以便连接到外围网络中的文件共享。 应当在诸如 Intranet 等信任级别较高的环境中使用文件适配器。 
  
-   设置强的自由访问控制列表 (DACL) 中接收位置的投递目录。 例如，您必须设置对文件接收位置从其中提取消息的目录的读取、写入、删除文件和删除子文件夹及文件的权限。  
  
-   在使用文件适配器提取关键数据时，建议使用 Internet 协议安全性 (IPSec)。  
  
## <a name="required-permissions"></a>所需的权限

在所选适配器处理程序的主机实例的安全上下文下运行适配器处理程序。 主机实例使用`Logon`中的属性***主机名*-主机实例属性**在 BizTalk 管理。 这`Logon`帐户必须具有到任何文件夹或文件适配器使用的共享的特定权限。

处理程序使用的主机实例用户帐户需要以下权限。 ✔ 意味着权限是必需的。 空白条目表示权限不是必需的。

| Permissions | 接收处理程序 | 发送处理程序 |
| --- | --- | --- |
| 完全控制 | ✔ <br/> 在共享级别 （如果访问文件共享） |  | 
| 遍历文件夹/执行文件 |  | ✔ <br/> 在文件级别 | 
| 列出文件夹/读取数据 | ✔ <br/> 在文件级别 | ✔ <br/> 在文件级别 | 
| 读取属性 | | ✔ <br/> 在文件级别 | 
| 读取扩展属性 | | ✔ <br/> 在文件级别 | 
| 创建文件/写入数据 | | ✔ <br/> 在文件级别 | 
| 创建文件夹/附加数据 | | ✔ <br/> 在文件级别 | 
| 删除子文件夹和文件 | ✔ <br/> 在文件级别 | ✔ <br/> 在文件级别 | 
| 读取权限 | | ✔ <br/> 在文件级别 | 
| 更改 | | ✔ <br/> 在共享级别 （如果访问文件共享） |

> [!TIP] 
> 在文件级别中，打开**高级权限**上的文件或文件夹以查看这些权限。

> [!NOTE] 
> 每个主机只能与一个接收处理程序相关联。  

## <a name="configure-the-receive-location"></a>配置接收位置
  
> [!NOTE]
>  之前完成以下过程，你必须已添加单向接收端口。 请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
1.  在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，展开**应用程序**，然后展开应用程序在你想要创建接收位置。  
  
2.  在左窗格中，单击**接收端口**节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  
  
3.  在左窗格中**接收端口属性**对话框中，选择**接收位置**，并在右窗格中双击现有接收位置或单击**新建**到创建一个新接收位置。  
  
4.  在**接收位置属性**对话框中，在**传输**部分中，选择**文件**从下拉列表中，键入，然后单击**配置**若要配置接收位置的传输属性。  
  
5.  在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**接收文件夹**|必需的。 在文件系统上，网络共享中，输入文件夹的路径或文件在其中接收处理程序的 Azure 文件共享读取文件。 你可以输入直接在路径**接收文件夹**文本框中，或选择从文件系统使用**浏览**按钮。 在浏览文件夹，你还可以创建新文件夹使用**新建文件夹**。<br /><br /> 如果使用 Azure 文件存储共享，则输入`\\yourfilestoragename.file.core.windows.net\yourfilesharename`。 <br /><br />**类型：**字符串 <br/><br/>**注意：**未设置**接收文件夹**NT 分布式文件系统使用的符号链接的文件夹的属性。 如果你使用的 NT 分布式文件系统，你可以仅使用文件夹中文件适配器的直网络路径接收位置。 <br /><br /> 有关此属性的限制，请参阅[限制在配置文件适配器](../core/restrictions-when-configuring-the-file-adapter.md)。 <br/><br/>**注意：**对要发送的 URI 端口或接收位置不能超过 256 个字符。|  
    |**文件掩码**|必需的。 指定文件的掩码。 此掩码均可包含的标准通配符值"\*"。<br /><br /> **默认值：** \*.xml<br /><br /> **类型：**字符串<br /><br /> 有关此属性的限制，请参阅[限制在配置文件适配器](../core/restrictions-when-configuring-the-file-adapter.md)。|  
    |**公共地址**|指定此位置的公用地址。 BizTalk Server 向外部合作伙伴公开此地址。<br /><br /> 如果未指定此属性，则运行时引擎会将其替换为：<br /><br /> file://\<*接收文件夹*\>/\<*文件掩码*\><br /><br /> 此属性的值要求包含一个适配器前缀。<br /><br /> **类型：**字符串<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256|  
    |**重试计数**|指定尝试访问网络共享上的接收位置（如果该位置暂时不可用）的次数。<br /><br /> **默认值：** 5<br /><br /> **类型：**长<br /><br /> **最小值：** 0<br /><br /> **最大值：** MAX_LONG|  
    |**重试间隔 （分钟）**|指定两次尝试访问网络共享上的接收位置（如果该位置暂时不可用）之间的重试间隔时间（分钟）。<br /><br /> **默认值：** 5 分钟<br /><br /> **类型：**长<br /><br /> **最小值：** 0<br /><br /> **最大值：** MAX_LONG|  
  
6.  上**身份验证**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**主机没有网络共享的访问权限时使用这些凭据**| 仅在使用网络共享或 Azure 文件共享时，才需要。 <br /><br /> **默认值：** False<br /><br /> **类型：**布尔|  
    |**用户名**|如果使用网络共享，请输入有权访问共享的用户名称。 <br /><br />  如果使用 Azure 文件存储共享，输入你的存储帐户的名称。<br/><br/>**类型：**字符串 <br /><br />**注意：**如果映射到同一网络共享的多个接收位置配置了备用凭据，则相同的凭据必须用于所有接收位置。 如果试图使用多组凭据，Windows 将不允许建立从同一计算机到共享网络服务器的多个连接。|  
    |**密码**|如果使用的网络共享，请输入有权访问网络共享的帐户的密码。<br /><br />  如果使用 Azure 文件存储共享，输入存储帐户访问密钥;在 Azure 门户中列出。<br /><br /> **类型：**字符串|  
  
7.  在**批处理**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**在批处理中的消息数**|指定可在一批中提交的最多消息数。<br /><br /> **默认值：** 5<br /><br /> **类型：** Int<br /><br /> **最小值：** 1<br /><br /> **最大值：** 256|  
    |**最大批处理大小 （以字节为单位）**|指定批的最大总字节数。<br /><br /> **默认值：** 102400<br /><br /> **类型：** Int<br /><br /> **最小值：** 1024年<br /><br /> **最大值：** MAX_LONG|  
  
     文件适配器将批限制为最多消息数或最大允许字节数中首先达到的那个值。  
  
9. 选择“确定”。  
  
10. 输入中的相应值**接收位置属性**对话框中，完成接收位置的配置并单击**确定**以保存设置。 璝惠**接收位置属性**对话框中，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  

## <a name="configure-the-send-port"></a>配置发送端口

1.  在 BizTalk Server 管理控制台中，创建新的发送端口或双击现有的发送端口来对其进行修改。 请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项并指定**文件**为**类型**选项**传输**部分**常规**选项卡。  
  
2.  选择**配置**按钮旁边**类型**。  
  
3.  在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**目标位置**|必需的。 在文件系统、 公共共享或 Azure 文件共享将输出消息写入到的位置输入的路径。 你可以输入直接在路径**目标位置**，或选择从文件系统使用**浏览**按钮。 在为的文件夹中浏览时**浏览文件夹**对话框中，你还可以创建一个新文件夹通过单击**新建文件夹**。<br /><br /> 如果使用 Azure 文件存储共享，则输入`\\yourfilestoragename.file.core.windows.net\yourfilesharename`。<br /><br /> **类型：**字符串 <br /><br />**注意：**对要发送的 URI 端口或接收位置不能超过 256 个字符。|  
    |**文件名**|指定文件发送处理程序将向其中写入消息的文件的名称。<br /><br /> 有关此属性的限制，包括使用宏中的文件名称，请参阅[限制在配置文件适配器](../core/restrictions-when-configuring-the-file-adapter.md)。|  
    |**副本模式**|定义要在一条消息写入到文件时使用的复制模式。 有效值为<br /><br /> **追加。** 文件发送处理程序打开一个文件（如果该文件存在）并在该文件末尾附加一个消息。 如果文件不存在，则文件发送处理程序将创建一个新文件。<br /><br /> **覆盖**。 文件发送处理程序打开一个文件（如果该文件存在）并覆盖其内容。 如果文件不存在，则文件发送处理程序将创建一个新文件。<br /><br /> **创建新**。 如果文件不存在，则文件发送处理程序将创建一个新文件，并在该文件中写入消息。 如果该文件已存在，则文件发送处理程序将报告错误，然后按照发送端口的通用适配器重试逻辑操作。 此模式为文件发送处理程序的默认复制模式。|  
    |**允许写入缓存**|定义向文件中写入消息时是否使用文件系统缓存。<br /><br /> 有效选项为：<br /><br /> **False**不使用文件系统缓存。<br /><br /> **True**使用文件系统缓存。<br /><br /> **默认值：** False**重要说明：**将此属性设置为**True**断电时，可以提高潜在的数据丢失的风险的文件适配器性能而不所有数据都写入到磁盘。|  
    |**在写入时使用临时文件**|定义是否先将输出文件写入到一个临时文件，然后在写入操作完成后重命名该文件。 如果启用此选项，则将创建临时文件，使用扩展**BTS WIP**。<br /><br /> 有效选项为<br /><br /> **True**文件适配器创建的临时文件写入到目标文件夹时。<br /><br /> **False**写入到目标文件夹时，文件适配器将不会创建临时文件。<br /><br /> **默认值：** False**注意：**时，此选项才可用**CopyMode**属性设置为值为**新建**|  
  
4.  上**身份验证**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**主机没有网络共享的访问权限时使用这些凭据**| 仅在使用网络共享或 Azure 文件共享时，才需要。 <br /><br /> **默认值：** False<br /><br /> **类型：**布尔|  
    |**用户名**|如果使用网络共享，请输入有权访问共享的用户名称。 <br /><br />  如果使用 Azure 文件存储共享，输入你的存储帐户的名称。<br /><br /> **类型：**字符串|  
    |**密码**|如果使用的网络共享，请输入有权访问网络共享的帐户的密码。<br /><br />  如果使用 Azure 文件存储共享，输入存储帐户访问密钥;在 Azure 门户中列出。<br /><br /> **类型：**字符串|  
  
5.  选择**确定**以保存设置。  

## <a name="set-the-properties-for-a-dynamic-send-port"></a>设置动态发送端口的属性
  
 动态发送端口在 BizTalk Server 管理控制台中不提供任何传输配置选项，因为这些属性将与消息关联的上下文属性一起提供。 这些属性可以在自定义管道或在业务流程中设置。 若要设置业务流程中的消息配置属性，请执行以下操作：  
  
-   添加**构造消息**形状上与您的业务流程。  
  
-   配置**构造消息**形状构造新消息。 （例如，Message_2）  
  
-   添加**消息分配**形状变为**构造消息**形状。  
  
-   将代码添加到**消息分配**形状初始化你构造的消息以及用于设置消息的相应的配置属性。 下面的代码初始化名为 Message_2 使用构造一条消息**构造消息**形状，然后将设置为消息的两个配置属性。 在此方案中，Message_1 最初由业务流程接收：  
  
    ```  
    Message_2=Message_1;  
    Message_2(FILE.CopyMode)= 0; //0=Append  
    Message_2(FILE.AllowCacheOnWrite)= true;  
    Message_2(FILE.UseTempFileOnWrite)= true;  
    ```  
 
  
## <a name="configure-the-receive-or-send-handler"></a>配置接收或发送处理程序
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**适配器**。  
  
2.  在展开的列表的适配器，单击**文件**、 在右窗格中，右键单击接收或发送你想要配置的处理程序。 选择**属性**。  
  
3.  在**主机名**列表中，选择要运行的处理程序的主机。  
  
4.  单击 **“确定”**。  

## <a name="more-topics-in-this-section"></a>本部分中的更多主题

[创建文件接收位置或以编程方式发送端口](../core/create-the-receive-location-and-send-port-programmatically.md)

[文件适配器属性架构和属性](../core/file-adapter-property-schema-and-properties.md)

[配置文件适配器时的限制](../core/restrictions-when-configuring-the-file-adapter.md)

## <a name="see-also"></a>另请参阅

 [用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)