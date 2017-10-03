---
title: "如何配置一个 POP3 接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, POP3 adapters
- POP3 adapters, receive locations
- configuring [POP3 adapters], receive locations
ms.assetid: 259cd105-733a-4f87-be30-c02e6bd0f457
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e16577e8bb7e9d624b6ba38211cf04b84a234be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-pop3-receive-location"></a>如何配置一个 POP3 接收位置
您可以在 BizTalk Server 管理控制台中设置 POP3 接收位置适配器变量。 如果未设置接收位置的属性，则使用 BizTalk Server 管理控制台中设置的默认接收处理程序值。  
  
> [!NOTE]
>  在执行以下过程之前，您必须已添加接收端口。 有关详细信息，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
 **若要配置一个 POP3 变量接收位置**  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你想要创建中的接收位置的应用程序。  
  
2.  在 BizTalk Server 管理控制台中，在左窗格中，单击**接收端口**节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  
  
3.  在**接收端口属性**对话框中，在左侧的窗格中，选择**接收位置**，然后在右窗格中，双击现有接收位置或单击**新建**创建一个新接收位置。  
  
4.  在**接收位置属性**对话框中，在**传输**旁边部分**类型**，选择**POP3**从下拉列表中，然后单击**配置**。  
  
5.  在**POP3 传输属性**对话框框中，执行以下操作：  
  
    |**使用此方法**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**应用 MIME 解码**|指定是否将 MIME 解码应用于通过 POP3 适配器接收的消息。 MIME 解码用于对传入消息和多部分 BizTalk 消息中的所有附件进行解析。 **重要说明：**如果此值设置为`False`然后 POP3 适配器将提交完整的电子邮件正文包括消息标头给 BizTalk Server。 <br /><br /> 默认值：30`True`|  
    |**正文部分内容类型**|指定要提交到 BizTalk Server 的传入电子邮件的正文部分内容类型。 这是可选设置。 请参阅[POP3 适配器是什么？](../core/what-is-the-pop3-adapter.md)有关详细信息。|  
    |**正文部分索引**|指定要提交到 BizTalk Server 的传入电子邮件的正文部分。 请参阅[POP3 适配器是什么？](../core/what-is-the-pop3-adapter.md)有关详细信息。<br /><br /> 默认值： 0|  
    |**邮件服务器**|指定 POP3 适配器将要轮询的邮箱所在的 POP3 邮件服务器。 **注意：**对要发送的 URI 端口或接收位置不能超过 256 个字符。|  
    |**端口**|指定 POP3 邮件服务器的端口。<br /><br /> 有效值：1 到 65535（含）<br /><br /> 默认值： 0**注意：**值为 0 指示如果使用默认 POP3 端口 110**使用 SSL**是`False`或端口 995 如果**使用 SSL**是`True`。|  
    |**身份验证方案**|指定目标服务器使用的验证类型。<br /><br /> 有效选项为：<br /><br /> -   **基本**<br />-   **摘要**<br />-   **SPA** **注意：**时使用 SPA 身份验证，必须使用以下格式之一指定用户名： 域帐户，则必须输入使用语法：\<域名 >\\<用户名\>本地帐户，则必须输入使用语法：\<计算机名称 >\\< 用户名\>|  
    |**密码**|指定对 POP3 服务器进行验证所使用的用户密码。|  
    |**使用 SSL**|指定是否使用安全套接字层 (SSL) 与目标服务器进行通信。<br /><br /> 默认值：30`False`|  
    |**用户名**|指定对 POP3 服务器进行验证所使用的用户名。 需要为此属性输入值。 **注意：**指定用户名称属性必须具有能够登录到网络的功能的帐户。 POP3 适配器连接到与为“用户名”属性指定的帐户相关联的邮箱。 因此，无法使用 POP3 适配器连接到分配到指定帐户的邮箱以外的邮箱。 例如，即使多个帐户都对与特定帐户关联的邮箱具有“读取”权限，但也只能为“用户名”指定实际帐户名。|  
    |**错误阈值**|指定在关闭适配器前允许的最大网络错误或协议错误数。 指定为 0 以防止适配器关闭。<br /><br /> 默认值： 10|  
    |**轮询间隔**|指定尝试从 POP3 服务器检索消息的时间间隔。<br /><br /> 默认值： 5|  
    |**轮询间隔单位**|指定的度量单位，以用于**轮询间隔**。<br /><br /> 默认值：分钟|  
  
6.  单击 **“确定”**。  
  
7.  在**接收位置属性**对话框框中，输入适当的值，以完成接收位置的配置，然后单击**确定**以保存设置。 璝惠**接收位置属性**对话框中，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
> [!NOTE]
>  如果配置为从中进行读取的邮箱包含的电子邮件超过 2,147,483,647 条，则 POP3 适配器将生成错误且无法处理任何消息。 因为 POP3 适配器将配置为读取的邮箱的消息数存储在 Int32 变量中，而该 Int32 数据类型的最大值为 2,147,483,647。  
  
> [!IMPORTANT]
>  在 POP3 适配器已成功从目标邮箱检索到电子邮件后，将从该邮箱删除此电子邮件。 设计此行为有助于防止 POP3 适配器检索到电子邮件的多个副本。 如果不希望删除邮箱中的电子邮件，请不要将 POP3 接收位置配置为监视该邮箱。  
  
## <a name="see-also"></a>另请参阅  
 [配置 POP3 适配器](../core/configuring-the-pop3-adapter.md)