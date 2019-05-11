---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: f4b67492efd40f8759c3cc2c490e4427b0272fb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383860"
---
# <a name="how-to-set-tibco-rendezvous-transport-properties"></a>如何设置 TIBCO Rendezvous 传输属性
TIBCO Rendezvous 传输属性用于运行时。 在中**传输属性**屏幕中，设置标识你想要发布生成的消息的 TIBCO Rendezvous 域的连接参数。  
  
## <a name="enter-tibco-rendezvous-transport-properties"></a>输入 TIBCO Rendezvous 传输属性  
  
1.  上**TIBCO Rendezvous 传输属性**屏幕上，展开**已认证发送方属性**并输入以下信息。  
  
     ![](../core/media/sadp-tibcoren-transs.gif "SAdp_TibcoRen_Transs")  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**分类帐名称**|默认值为空。 要用于持久性认证的消息传递的分类帐文件名称。 使用仅限于本地驱动器。|  
    |**可重复使用名称**|默认值为空。 若要使用认证的消息传递的可重用通信名称。 名称必须是唯一的而在网络上的所有认证的消息通信名称。|  
  
2.  展开**凭据**并输入以下信息以连接到服务器。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**密码**|默认值为空。 登录到 Tibco Rendezvous 后台程序的密码。|  
    |**用户名**|默认值为空。 Tibco Rendezvous 后台程序的用户名。|  
  
3.  展开**常规设置**并输入以下信息以连接到 TIBCO Rendezvous 服务器。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**代码页编号**|默认值是 65001 （代码页 utf-8 编码）。 这是 TIBCO Rendezvous SDK 用于字符串编码的代码页。|  
    |**默认使用者名称**|默认值为空。 在业务流程中设置的使用者名称。 如果一个端口用于一种消息类型，您可以提供默认使用者名称，并通过删除需要设置 name 属性的使用者来简化业务流程。|  
    |**启用时间批处理**|默认值为 False。 启用/禁用 TIBCO Rendezvous 时间批处理功能。|  
    |**将不受支持的类型映射到字符串**|默认值为 True。 如果为 true，它是否可以不受支持的类型将映射到字符串中。 如果为 False，则会生成运行时错误。|  
    |**二进制文件，如 TIBCO Rendezvous 程序集路径**|如果尚不在路径环境变量，提供此信息。|  
    |**保留订单**|默认值为 True。 使逻辑将消息发送到 TIBCO Rendezvous 从 BizTalk Server 接收的顺序相同。 此参数强制按相同顺序; 的发布它并不意味着订阅服务器的相同顺序接收它们。|  
    |**发送端口标识符**|此标识符出现在与此端口相关联的日志消息。 它作为方便提供。|  
  
4.  展开**Rendezvous 传输**并输入到 TIBCO Rendezvous 服务器的连接的信息，请单击**应用**，然后单击**确定**。  
  
     必须设置为用于 TIBCO Rendezvous 以访问 TIBCO Rendezvous 的 Microsoft BizTalk 适配器的连接参数。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**守护程序**|默认值为空。<br /><br /> Rendezvous 传输后台程序参数。|  
    |**Network**|默认值为空。<br /><br /> Rendezvous 传输网络参数。|  
    |**服务**|默认值为空。<br /><br /> Rendezvous 传输服务参数。|  
  
5.  提供使用单一登录 (SSO) 的凭据。  
  
     有两种方法可用于访问 TIBCO Rendezvous 系统。 您可以使用凭据 （用户名和密码参数） 或单一登录。  
  
    1.  选择**是**中**使用 SSO**若要使用单一登录。  
  
        > [!NOTE]
        >  请参阅[安全](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)了解如何设置 SSO。  
  
    2.  从列表中选择关联应用程序。  
  
         企业单一登录工具创建的关联应用程序表示诸如 TIBCO Rendezvous 等的应用程序。 用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 从指定的关联应用程序的服务器系统的 SSO 数据库检索这些凭据。  
  
        > [!NOTE]
        >  有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。  
  
6.  单击**Apply**，然后单击**确定**提供接受连接信息所需的所有信息后。  
  
     必须设置为用于 TIBCO Rendezvous 以访问 TIBCO Rendezvous 的 BizTalk 适配器的连接参数。  
  
## <a name="see-also"></a>请参阅  
 [创建 TIBCO Rendezvous 发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)