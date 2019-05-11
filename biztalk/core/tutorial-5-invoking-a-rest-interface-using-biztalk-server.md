---
title: 教程 5:调用 REST 接口使用 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 73871ca3-abd0-45ae-b379-6df76a967a80
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4688f550c78a561a85c4ca8288ab8ef6e6d264f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399175"
---
# <a name="tutorial-5-invoking-a-rest-interface-using-biztalk-server"></a>教程 5:调用 REST 接口使用 BizTalk Server
本部分提供有关如何调用 REST 终结点使用的分步演练[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在本教程中调用 REST 终结点可从[!INCLUDE[winazure](../includes/winazure-md.md)]返回航班的延误空气情况的 Marketplace。 本教程使用的新**Wcf-webhttp**适配器中引入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来调用 REST 终结点。  
  
##  <a name="BKMK_Scenario"></a> 本教程中使用的方案  
 [!INCLUDE[winazure](../includes/winazure-md.md)] 市场提供了以下 REST 资源 URL 来检索美国航空公司航班的延误情况：  
  
```  
https://api.datamarket.azure.com/oakleaf/US_Air_Carrier_Flight_Delays_Incr/On_Time_Performance  
```  
  
 如果在 Web 浏览器的地址栏中输入此 URL，系统会提示你输入访问资源的凭据。 登录到之后[Windows Azure Marketplace](http://go.microsoft.com/fwlink/p/?LinkId=257913)，你可以获取从凭据**我的帐户**web 页的选项卡。 对列出这些凭据**Customer ID** （用户名） 和**主帐户密钥**（密码） 标签。  
  
 在本教程中，将使用的资源 URL 和凭据来配置一个双向**Wcf-webhttp**发送端口。 双向发送端口的接收管道将接收包含航班详细信息的响应消息并将发布到消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]messagebox 数据库。 配置 FILE 发送端口订阅由 Wcf-webhttp 发送端口发布的所有消息的。 FILE 发送端口将使用从消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并将其复制到某个文件位置。  
  
 在现实世界的业务方案中，可以通过将它与更大的业务流程，如从业务应用程序中获取消息的接收位置相关联触发的 Wcf-webhttp 发送端口。 但是，在本教程中，由于重点是演示如何调用 REST 接口，您可以使用简单的文件位置的接收虚拟消息来触发该发送端口。  
  
 因此，若要汇总，必须执行以下步骤来配置此解决方案：  
  
1.  配置一个 FILE 接收位置来提取虚拟请求消息。  
  
2.  配置双向 Wcf-webhttp 发送端口来调用 REST 资源 URL 并接收响应。  
  
3.  配置单向 FILE 发送端口以使用包含航班详细信息的响应消息并将其复制到某个文件位置。  
  
## <a name="set-up-your-includewinazureincludeswinazure-mdmd-marketplace-account"></a>设置你[!INCLUDE[winazure](../includes/winazure-md.md)]Marketplace 帐户  
 若要访问通过 REST 终结点公开的航班延迟数据，必须首先订阅美国美国航空公司航班延误示例数据源。 执行以下步骤来执行此操作：  
  
#### <a name="to-subscribe-to-the-data-feed"></a>若要订阅的数据馈送  
  
1. 登录到[!INCLUDE[winazure](../includes/winazure-md.md)]Marketplace 使用你的 Microsoft 帐户。  
  
2. 在中**数据**选项卡上，找到并单击**美国美国航空公司航班延误**服务。  
  
3. 在数据服务页面上单击**注册**。 在注册页上，接受协议的条款，然后单击**注册**试。  
  
4. 在中**我的帐户**选项卡上，检索用于访问数据服务的凭据。 对列出这些凭据**Customer ID** （用户名） 和**主帐户密钥**（密码） 标签。 配置时，将需要这些凭据**Wcf-webhttp**发送端口。  
  
## <a name="set-up-your-computer"></a>设置计算机  
 若要配置必须具有本教程中使用的方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]您的计算机上安装和配置。 如果想要预配[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机上 Windows Azure VM，请遵循的说明[Azure VM 上配置 BizTalk Server](http://msdn.microsoft.com/library/azure/jj248689.aspx)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：配置一个 FILE 接收位置](../core/step-1-configure-a-file-receive-location.md)  
  
-   [步骤 2：配置双向 Wcf-webhttp 发送端口](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md)  
  
-   [步骤 3：配置单向 FILE 发送端口](../core/step-3-configure-a-one-way-file-send-port.md)  
  
-   [步骤 4：测试解决方案](../core/step-4-test-the-solution.md)