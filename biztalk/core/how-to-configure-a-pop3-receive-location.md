---
title: 如何配置 POP3 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, POP3 adapters
- POP3 adapters, receive locations
- configuring [POP3 adapters], receive locations
ms.assetid: 259cd105-733a-4f87-be30-c02e6bd0f457
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcf68b8b360e14857e1167b8d4a846b9f2665abe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386965"
---
# <a name="how-to-configure-a-pop3-receive-location"></a>如何配置 POP3 接收位置
您可以设置 POP3 BizTalk Server 管理控制台中的接收位置适配器变量。 如果属性未设置接收位置中，使用 BizTalk Server 管理控制台中设置的默认接收处理程序值。  
  
> [!NOTE]
>  在执行以下过程之前，必须已添加接收端口。 有关详细信息，请参阅 [如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
 **若要配置 pop3 接收位置的变量**  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你想要在其中创建接收位置的应用程序。  
  
2.  在 BizTalk Server 管理控制台中，在左窗格中，单击**接收端口**节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  
  
3.  在中**接收端口属性**对话框中，在左窗格中，选择**接收位置**，然后在右窗格中，双击现有接收位置或单击**新建**以创建新的接收位置。  
  
4.  在中**接收位置属性**对话框中**传输**部分旁边**类型**，选择**POP3**从下拉列表中，然后单击**配置**。  
  
5.  在中**POP3 传输属性**对话框框中，执行以下操作：  
  
    |**使用此**|**若要执行此操作**|  
    |------------------|--------------------|  
    |**应用 MIME 解码**|指定是否要应用 MIME 解码通过 POP3 适配器接收到消息。 MIME 解码用于分析传入的消息和多部分 BizTalk 消息的所有附件。 **重要提示：** 如果此值设置为`False`则 POP3 适配器将提交完整的电子邮件正文包括到 BizTalk Server 消息标头。 <br /><br /> 默认值：30`True`|  
    |**正文部分内容类型**|指定要提交到 BizTalk Server 的传入电子邮件的正文部分内容类型。 这是一项可选设置。 请参阅[POP3 适配器？](../core/what-is-the-pop3-adapter.md)有关详细信息。|  
    |**正文部分索引**|指定要提交到 BizTalk Server 的传入电子邮件的正文部分。 请参阅[POP3 适配器？](../core/what-is-the-pop3-adapter.md)有关详细信息。<br /><br /> 默认值：0|  
    |**Mail Server**|指定 POP3 适配器将要轮询的邮箱所在的 POP3 邮件服务器。 **注意：** URI 发送端口或接收位置不能超过 256 个字符。|  
    |**端口**|指定 POP3 邮件服务器的端口。<br /><br /> 有效的值：1 到 65535 （含)。<br /><br /> 默认值：0**注意：** 值为 0 指示如果使用默认 POP3 端口 110**使用 SSL**是`False`或者端口 995**使用 SSL**是`True`。|  
    |**身份验证方案**|指定要对目标服务器使用身份验证的类型。<br /><br /> 有效选项为：<br /><br /> -   **基本**<br />-   **摘要**<br />-   **SPA** **注意：** 使用 SPA 验证时，必须使用以下格式之一指定用户名：必须使用语法输入域帐户：\<域名\>\\< 用户名\>必须使用语法输入本地帐户：\<计算机名称\>\\<用户名\>|  
    |**密码**|指定要用于 POP3 服务器的身份验证的用户密码。|  
    |**使用 SSL**|指定是否使用安全套接字层 (SSL) 与目标服务器进行通信。<br /><br /> 默认值：30`False`|  
    |**用户名**|指定要用于 POP3 服务器的身份验证的用户名。 此属性需要一个值。 **注意：** 为用户名属性指定的帐户必须具有能够登录到网络。 POP3 适配器连接到指定的用户名属性的帐户相关联的邮箱。 因此不能使用 POP3 适配器连接到邮箱以外分配给指定的帐户的邮箱。 例如，即使多个帐户具有读取权限与特定帐户相关联的邮箱，可以为用户名指定仅实际帐户名。|  
    |**错误阈值**|指定的最大网络或协议错误，关闭适配器前等待数。 指定值 0 可以防止适配器关闭。<br /><br /> 默认值：10|  
    |**轮询间隔**|指定两次尝试从 POP3 服务器检索消息之间的间隔。<br /><br /> 默认值：5|  
    |**轮询间隔单位**|指定要用于度量单位**轮询间隔**。<br /><br /> 默认值：Minutes|  
  
6.  单击“确定” 。  
  
7.  在中**接收位置属性**对话框框中，输入适当的值以完成配置该接收位置，然后单击**确定**以保存设置。 有关“接收位置属性”  对话框的信息，请参阅 [如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
> [!NOTE]
>  POP3 适配器将生成错误且无法处理任何消息，如果邮箱，因此，并配置从读取包含多个 2,147,483,647 电子邮件消息。 POP3 适配器将存储其配置为在 Int32 变量读取和 Int32 数据类型的最大值为 2,147,483,647 的邮箱的消息计数。  
  
> [!IMPORTANT]
>  POP3 适配器从目标邮箱已成功检索电子邮件后将从该邮箱删除此电子邮件。 此行为被设计为帮助防止 POP3 适配器检索电子邮件的多个副本。 未配置 POP3 接收位置监视的邮箱，如果不希望删除邮箱中的电子邮件。  
  
## <a name="see-also"></a>请参阅  
 [配置 POP3 适配器](../core/configuring-the-pop3-adapter.md)